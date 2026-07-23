# Changelog

## 2026.07.23

### What Changed

- Corrected the README's description of the `-hdpi` / `-xhdpi` folders. They
  were documented as full theme variants ("585 themes", "use a `-hdpi` variant
  on HiDPI displays"), but they contain nothing except `xfwm4/` — no
  `index.theme`, no GTK. A user selecting one as their GTK theme would get
  window borders and no styling. Verified against upstream `install.sh`: this
  is the intended Celestial convention, not a broken render, so the fix belongs
  in the documentation.
- Reworded the 65 `pkgdesc` lines, which carried the same "three DPI tiers"
  implication.
- Added a `.gitignore` — the repo had none, so anything landing in `.claude/`
  would have been committed.

### Technical Details

- The count is now stated as 195 themes plus 390 companion folders, instead of
  585 themes. The README explains why the split exists: xfwm4 draws decorations
  from fixed-size PNGs that need a pre-render per display scale, while every
  other surface is CSS or vector and scales itself.
- The HiDPI section gives the actual usage — keep the normal theme, point only
  the window manager style at the companion folder
  (`xfconf-query -c xfwm4 -p /general/theme -s "…-hdpi"`).
- Verification run alongside the edit: the 65 `pkgname` entries, 65
  `package_*` functions and 65 `_install_family` tokens all agree, and all
  65 x 9 = 585 folders they name exist on disk with no folder left unclaimed by
  a package.
- `pkgver` / `pkgrel` deliberately untouched — documentation only, no rebuild
  needed.

- Added the Kvantum (Qt) themes — 195 of them, one per colour/mode, in a new
  top-level `Kvantum/` folder. Without these, Qt apps kept whatever style Qt
  defaults to while GTK, xfwm4 and plank all followed the picked accent. The
  forge learned to generate them on 2026.07.21; this repo's output predates
  that, so they simply had never been harvested.
- The four stock colours now declare `conflicts=('celestial-gtk-theme')`.

### Technical Details (Kvantum)

- Generated with `celestial-theme-forge/generate-arc-colors.sh` into a fresh
  `prepare-celestial.py` checkout. Only step 1 of the forge workflow is needed:
  `gen_kvantum()` writes `.kvconfig` + `.svg` directly, so neither `parse_sass.sh`
  nor the ~1h `render-all.sh` is on this path.
- Verified before committing: for all 195 themes the `highlight.color` in the
  generated `.kvconfig` equals the `selected_bg_color` already baked into that
  colour's `gtk-3.0/gtk.css`. Zero mismatches — the Qt accent provably matches
  the GTK accent rather than merely looking close.
- Five colours (`denim`, `jasmine`, `mandarin`, `night-owl`, `slateblue`) ship
  here but had dropped out of the forge's `COLORS` map, and the checkout that
  built them is gone. Their accents were recovered by reading `selected_bg_color`
  back out of the built CSS; that same read reproduces every other colour's
  known hex exactly, which is what makes the recovery trustworthy. Added back to
  the forge so the repo is reproducible again.
- `indigo` is in the forge but has no GTK theme here, so it was deliberately
  excluded — shipping a Qt theme for a colour with no GTK theme would be worse
  than shipping neither.
- `_install_family` installs them to `/usr/share/Kvantum`, matching celestial's
  own `install.sh`. They are a separate tree, not part of a GTK theme folder,
  and have no `-hdpi`/`-xhdpi` tier.
- The `conflicts` entry is on `celestial-aliz`, `-azul`, `-pueril` and `-sea`
  only. `celestial-gtk-theme` already owns the `/usr/share/themes` paths for
  those four stock colours, so they already failed to install alongside it —
  Kvantum only widened the overlap. Pacman now offers a swap instead of a hard
  file-conflict error; the other 61 packages remain installable alongside
  upstream.
- `kvantum` added to `optdepends`.

### Files Modified

- `README.md`
- `PKGBUILD`
- `.gitignore` (new)
- `CHANGELOG.md`
- `Kvantum/` (new — 195 theme folders)

## 2026.07.22

### What Changed

- Added a `PKGBUILD` that turns the repo into Arch packages, one split package
  per colour family: `celestial-aliz`, `celestial-aqua`, … 65 packages in total.
  Each package ships all nine variants of its family (standard/Dark/Light x
  standard/hdpi/xhdpi), so a user installs one package per colour instead of
  copying folders by hand.

### Technical Details

- `pkgbase=celestial-themes` with a 65-entry `pkgname` array; the package list
  is derived from the actual family directories in the repo, not hand-typed.
- `_install_family` builds the nine folder names exactly
  (`Celestial-${token}${mode}${dpi}`) rather than globbing, which is what keeps
  `Celestial-Azure` from swallowing `Celestial-Azure-dodger-blue` and
  `Celestial-Blue-sky` from matching `Celestial-Blueberry`.
- Package names are lowercased (`celestial-light-blue-grey`) while the install
  token keeps the original casing (`Light-blue-grey`) to match directory names.
- Themes install to `/usr/share/themes/`.
- `options=(!strip !emptydirs)`, `optdepends` on `papirus-icon-theme` since the
  themes reference Papirus icons.
- `source=` is a git clone of this repo, matching the kiro-arc-themes pattern —
  a build packages what is on GitHub `main`, so push before building.

- Adapted `build.sh` to the split PKGBUILD so a build actually lands all 65
  packages in `nemesis_repo/x86_64`.

### Technical Details (build.sh)

- The copy-out globbed `*celestial-themes*pkg.tar.zst`, which matches nothing —
  split packages are named `celestial-aliz-*`, `celestial-aqua-*`, … It now
  copies every `*.pkg.tar.zst` the build produced and aborts if there are none.
- The build dir got `cp -r <repo>/*`, i.e. ~900 MB of rendered themes into
  `/tmp` for a PKGBUILD that fetches its sources from git anyway. Only the
  PKGBUILD is copied now.
- `pkgname` extraction falls back to `pkgbase` (`pkgname` is an array here), so
  the version logs name the package instead of printing `(`.
- `/tmp/tempbuild` is removed after a successful build and kept after a failure,
  so the chroot logs survive when something breaks.

### Files Modified

- `PKGBUILD` (new)
- `CHANGELOG.md` (new)
- `build.sh`
