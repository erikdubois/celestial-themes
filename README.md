# celestial-themes

A large family of ready-to-install GTK desktop themes — **65 named colours ×
3 modes × 3 DPI tiers = 585 themes** — covering every common Linux desktop
surface: GTK 2/3/4, GNOME Shell, Cinnamon, Unity, xfwm4, Metacity, Openbox,
labwc and Plank.

These are the **built themes**, ready to drop into `~/.themes`. They are
generated from the
[Celestial GTK theme](https://github.com/zquestz/celestial-gtk-theme) by
expanding its stock 4 colours with the named
[Arc palette](https://github.com/kirodubes/kiro-arc-themes), then compiling and
rendering every variant. The tooling that produces them lives separately in
`celestial-theme-forge`; this repo is just the output.

## What's in a theme

Each colour ships in three modes and three DPI tiers:

| | standard | `-hdpi` | `-xhdpi` |
|---|---|---|---|
| **standard** (dark) | `Celestial-Aqua` | `Celestial-Aqua-hdpi` | `Celestial-Aqua-xhdpi` |
| **Dark** | `Celestial-Aqua-Dark` | `Celestial-Aqua-Dark-hdpi` | `Celestial-Aqua-Dark-xhdpi` |
| **Light** | `Celestial-Aqua-Light` | `Celestial-Aqua-Light-hdpi` | `Celestial-Aqua-Light-xhdpi` |

Every theme folder contains the surfaces for that variant:

```
cinnamon/  gnome-shell/  gtk-2.0/  gtk-3.0/  gtk-4.0/
labwc/  metacity-1/  openbox-3/  plank/  unity/  xfwm4/
index.theme
```

## Install

Pick whichever colours you want (the repo is large — you don't need all 585).

```bash
# all of them
mkdir -p ~/.themes
cp -r Celestial-* ~/.themes/

# or just a few variants
cp -r Celestial-Emerald Celestial-Emerald-Dark Celestial-Crimson-Light ~/.themes/
```

For a system-wide install, copy into `/usr/share/themes/` instead (needs root).

Then select the theme — e.g. with GNOME Tweaks, `lxappearance`, your DE's
appearance settings, or:

```bash
gsettings set org.gnome.desktop.interface gtk-theme "Celestial-Emerald-Dark"
gsettings set org.gnome.desktop.wm.preferences theme "Celestial-Emerald-Dark"
```

Use a `-hdpi` or `-xhdpi` variant on HiDPI / 4K displays where the standard
assets look too small.

## Colours

65 named accents:

```
Aliz              Aqua              Archlinux-blue    Arcolinux-blue
Azul              Azure             Azure-dodger-blue Blood
Blueberry         Blue-sky          Botticelli        Bright-lilac
Carnation         Carolina-blue     Casablanca        Cornflower-blue
Crimson           Darkish           Dawn              Denim
Dodger-blue       Dracul            Emerald           Evopop
Fern              Fire              Froly             Havelock
Hibiscus          Jasmine           Light-blue-grey   Light-blue-surfn
Light-salmon      Mandarin          Mandy             Mantis
Medium-blue       Neon-blue         Niagara           Nice-blue
Night-owl         Numix             Orchid            Pale-grey
Paper             Pink              Polo              Pueril
Punch             Purpley           Red-orange        Red-violet
Rusty-orange      Sea               Sky-blue          Slateblue
Slate-grey        Smoke             Soft-blue         Tacao
Tangerine         Tory              Twilight          Vampire
Warm-pink
```

## Icons

The themes reference **Papirus** icons (`Papirus-Dark` for the dark/standard
variants). Install Papirus separately for the intended look:

```bash
sudo pacman -S papirus-icon-theme        # Arch
```

## Credits

- Upstream theme: [Celestial GTK theme](https://github.com/zquestz/celestial-gtk-theme)
- Colour palette: [kiro-arc-themes](https://github.com/kirodubes/kiro-arc-themes)
- Built and maintained by Erik Dubois — <https://www.erikdubois.be>
