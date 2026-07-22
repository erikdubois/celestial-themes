# Changelog

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
