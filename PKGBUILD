# Maintainer: Erik Dubois <erik.dubois@gmail.com>
# Generated — one split package per colour family.

pkgbase=celestial-themes
pkgname=(
  celestial-aliz
  celestial-aqua
  celestial-archlinux-blue
  celestial-arcolinux-blue
  celestial-azul
  celestial-azure
  celestial-azure-dodger-blue
  celestial-blood
  celestial-blueberry
  celestial-blue-sky
  celestial-botticelli
  celestial-bright-lilac
  celestial-carnation
  celestial-carolina-blue
  celestial-casablanca
  celestial-cornflower-blue
  celestial-crimson
  celestial-darkish
  celestial-dawn
  celestial-denim
  celestial-dodger-blue
  celestial-dracul
  celestial-emerald
  celestial-evopop
  celestial-fern
  celestial-fire
  celestial-froly
  celestial-havelock
  celestial-hibiscus
  celestial-jasmine
  celestial-light-blue-grey
  celestial-light-blue-surfn
  celestial-light-salmon
  celestial-mandarin
  celestial-mandy
  celestial-mantis
  celestial-medium-blue
  celestial-neon-blue
  celestial-niagara
  celestial-nice-blue
  celestial-night-owl
  celestial-numix
  celestial-orchid
  celestial-pale-grey
  celestial-paper
  celestial-pink
  celestial-polo
  celestial-pueril
  celestial-punch
  celestial-purpley
  celestial-red-orange
  celestial-red-violet
  celestial-rusty-orange
  celestial-sea
  celestial-sky-blue
  celestial-slateblue
  celestial-slate-grey
  celestial-smoke
  celestial-soft-blue
  celestial-tacao
  celestial-tangerine
  celestial-tory
  celestial-twilight
  celestial-vampire
  celestial-warm-pink
)
pkgver=26.07
pkgrel=01
pkgdesc="Celestial GTK theme recoloured with the named Arc palette"
arch=('any')
url="https://github.com/erikdubois/celestial-themes"
license=('GPL3')
options=(!strip !emptydirs)
makedepends=('git')
optdepends=('papirus-icon-theme: icon theme referenced by the themes')
source=("${pkgbase}::git+https://github.com/erikdubois/celestial-themes.git")
sha256sums=('SKIP')

# Install the nine variant folders of one colour family: three modes
# (standard, Dark, Light) x three DPI tiers (standard, hdpi, xhdpi).
# Folder names are built exactly, so Azure never grabs Azure-dodger-blue.
_install_family() {
  local token="$1" mode dpi d src="${srcdir}/${pkgbase}"
  install -dm755 "${pkgdir}/usr/share/themes"
  for mode in "" "-Dark" "-Light"; do
    for dpi in "" "-hdpi" "-xhdpi"; do
      d="Celestial-${token}${mode}${dpi}"
      if [[ -d "${src}/${d}" ]]; then
        cp -r "${src}/${d}" "${pkgdir}/usr/share/themes/"
      fi
    done
  done
}

package_celestial-aliz() {
  pkgdesc="Celestial Aliz GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Aliz"
}

package_celestial-aqua() {
  pkgdesc="Celestial Aqua GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Aqua"
}

package_celestial-archlinux-blue() {
  pkgdesc="Celestial Archlinux blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Archlinux-blue"
}

package_celestial-arcolinux-blue() {
  pkgdesc="Celestial Arcolinux blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Arcolinux-blue"
}

package_celestial-azul() {
  pkgdesc="Celestial Azul GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Azul"
}

package_celestial-azure() {
  pkgdesc="Celestial Azure GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Azure"
}

package_celestial-azure-dodger-blue() {
  pkgdesc="Celestial Azure dodger blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Azure-dodger-blue"
}

package_celestial-blood() {
  pkgdesc="Celestial Blood GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Blood"
}

package_celestial-blueberry() {
  pkgdesc="Celestial Blueberry GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Blueberry"
}

package_celestial-blue-sky() {
  pkgdesc="Celestial Blue sky GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Blue-sky"
}

package_celestial-botticelli() {
  pkgdesc="Celestial Botticelli GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Botticelli"
}

package_celestial-bright-lilac() {
  pkgdesc="Celestial Bright lilac GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Bright-lilac"
}

package_celestial-carnation() {
  pkgdesc="Celestial Carnation GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Carnation"
}

package_celestial-carolina-blue() {
  pkgdesc="Celestial Carolina blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Carolina-blue"
}

package_celestial-casablanca() {
  pkgdesc="Celestial Casablanca GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Casablanca"
}

package_celestial-cornflower-blue() {
  pkgdesc="Celestial Cornflower blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Cornflower-blue"
}

package_celestial-crimson() {
  pkgdesc="Celestial Crimson GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Crimson"
}

package_celestial-darkish() {
  pkgdesc="Celestial Darkish GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Darkish"
}

package_celestial-dawn() {
  pkgdesc="Celestial Dawn GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Dawn"
}

package_celestial-denim() {
  pkgdesc="Celestial Denim GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Denim"
}

package_celestial-dodger-blue() {
  pkgdesc="Celestial Dodger blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Dodger-blue"
}

package_celestial-dracul() {
  pkgdesc="Celestial Dracul GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Dracul"
}

package_celestial-emerald() {
  pkgdesc="Celestial Emerald GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Emerald"
}

package_celestial-evopop() {
  pkgdesc="Celestial Evopop GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Evopop"
}

package_celestial-fern() {
  pkgdesc="Celestial Fern GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Fern"
}

package_celestial-fire() {
  pkgdesc="Celestial Fire GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Fire"
}

package_celestial-froly() {
  pkgdesc="Celestial Froly GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Froly"
}

package_celestial-havelock() {
  pkgdesc="Celestial Havelock GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Havelock"
}

package_celestial-hibiscus() {
  pkgdesc="Celestial Hibiscus GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Hibiscus"
}

package_celestial-jasmine() {
  pkgdesc="Celestial Jasmine GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Jasmine"
}

package_celestial-light-blue-grey() {
  pkgdesc="Celestial Light blue grey GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Light-blue-grey"
}

package_celestial-light-blue-surfn() {
  pkgdesc="Celestial Light blue surfn GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Light-blue-surfn"
}

package_celestial-light-salmon() {
  pkgdesc="Celestial Light salmon GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Light-salmon"
}

package_celestial-mandarin() {
  pkgdesc="Celestial Mandarin GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Mandarin"
}

package_celestial-mandy() {
  pkgdesc="Celestial Mandy GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Mandy"
}

package_celestial-mantis() {
  pkgdesc="Celestial Mantis GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Mantis"
}

package_celestial-medium-blue() {
  pkgdesc="Celestial Medium blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Medium-blue"
}

package_celestial-neon-blue() {
  pkgdesc="Celestial Neon blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Neon-blue"
}

package_celestial-niagara() {
  pkgdesc="Celestial Niagara GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Niagara"
}

package_celestial-nice-blue() {
  pkgdesc="Celestial Nice blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Nice-blue"
}

package_celestial-night-owl() {
  pkgdesc="Celestial Night owl GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Night-owl"
}

package_celestial-numix() {
  pkgdesc="Celestial Numix GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Numix"
}

package_celestial-orchid() {
  pkgdesc="Celestial Orchid GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Orchid"
}

package_celestial-pale-grey() {
  pkgdesc="Celestial Pale grey GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Pale-grey"
}

package_celestial-paper() {
  pkgdesc="Celestial Paper GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Paper"
}

package_celestial-pink() {
  pkgdesc="Celestial Pink GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Pink"
}

package_celestial-polo() {
  pkgdesc="Celestial Polo GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Polo"
}

package_celestial-pueril() {
  pkgdesc="Celestial Pueril GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Pueril"
}

package_celestial-punch() {
  pkgdesc="Celestial Punch GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Punch"
}

package_celestial-purpley() {
  pkgdesc="Celestial Purpley GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Purpley"
}

package_celestial-red-orange() {
  pkgdesc="Celestial Red orange GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Red-orange"
}

package_celestial-red-violet() {
  pkgdesc="Celestial Red violet GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Red-violet"
}

package_celestial-rusty-orange() {
  pkgdesc="Celestial Rusty orange GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Rusty-orange"
}

package_celestial-sea() {
  pkgdesc="Celestial Sea GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Sea"
}

package_celestial-sky-blue() {
  pkgdesc="Celestial Sky blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Sky-blue"
}

package_celestial-slateblue() {
  pkgdesc="Celestial Slateblue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Slateblue"
}

package_celestial-slate-grey() {
  pkgdesc="Celestial Slate grey GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Slate-grey"
}

package_celestial-smoke() {
  pkgdesc="Celestial Smoke GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Smoke"
}

package_celestial-soft-blue() {
  pkgdesc="Celestial Soft blue GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Soft-blue"
}

package_celestial-tacao() {
  pkgdesc="Celestial Tacao GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Tacao"
}

package_celestial-tangerine() {
  pkgdesc="Celestial Tangerine GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Tangerine"
}

package_celestial-tory() {
  pkgdesc="Celestial Tory GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Tory"
}

package_celestial-twilight() {
  pkgdesc="Celestial Twilight GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Twilight"
}

package_celestial-vampire() {
  pkgdesc="Celestial Vampire GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Vampire"
}

package_celestial-warm-pink() {
  pkgdesc="Celestial Warm pink GTK theme - dark, Dark and Light in three DPI tiers"
  _install_family "Warm-pink"
}
