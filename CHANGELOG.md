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

### Files Modified

- `PKGBUILD` (new)
- `CHANGELOG.md` (new)
