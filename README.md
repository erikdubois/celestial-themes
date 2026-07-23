# celestial-themes

A large family of ready-to-install GTK desktop themes — **65 named colours ×
3 modes = 195 themes**, plus 390 companion folders carrying HiDPI xfwm4
decorations. Each theme covers every common Linux desktop surface: GTK 2/3/4,
GNOME Shell, Cinnamon, Unity, xfwm4, Metacity, Openbox, labwc and Plank.

These are the **built themes**, ready to drop into `~/.themes`. They are
generated from the
[Celestial GTK theme](https://github.com/zquestz/celestial-gtk-theme) by
expanding its stock 4 colours with the named
[Arc palette](https://github.com/kirodubes/kiro-arc-themes), then compiling and
rendering every variant. The tooling that produces them lives separately in
`celestial-theme-forge`; this repo is just the output.

## What's in a theme

Each colour ships in three modes — `Celestial-Aqua` (dark),
`Celestial-Aqua-Dark` and `Celestial-Aqua-Light`. Those are the folders you
select as your theme, and each one contains every surface:

```
cinnamon/  gnome-shell/  gtk-2.0/  gtk-3.0/  gtk-4.0/
labwc/  metacity-1/  openbox-3/  plank/  unity/  xfwm4/
index.theme
```

### The `-hdpi` and `-xhdpi` folders

Every mode also has `-hdpi` and `-xhdpi` companions
(`Celestial-Aqua-Dark-hdpi`, …). **These are not themes** — following the
upstream Celestial convention they contain nothing but an `xfwm4/` folder, and
no `index.theme`.

The reason: xfwm4 draws its window decorations from fixed-size PNGs, so they
have to be pre-rendered per display scale. Every other surface (GTK, GNOME
Shell, Cinnamon, Openbox, labwc) is CSS or vector and scales by itself.

So on a HiDPI / 4K display you don't switch to them — you keep the normal
theme and point **only the window manager style** at the companion folder. On
XFCE:

```bash
xfconf-query -c xfwm4 -p /general/theme -s "Celestial-Aqua-Dark-hdpi"
```

Selecting an `-hdpi` folder as your GTK theme would leave you with window
borders and no styling at all.

## Install

Pick whichever colours you want (the repo is large — you don't need all of it).

```bash
# all of them
mkdir -p ~/.themes
cp -r Celestial-* ~/.themes/

# or just a few variants
cp -r Celestial-Emerald Celestial-Emerald-Dark Celestial-Crimson-Light ~/.themes/
```

Copy the matching `-hdpi` / `-xhdpi` folder too if you run xfwm4 on a HiDPI
display.

For a system-wide install, copy into `/usr/share/themes/` instead (needs root).

Then select the theme — e.g. with GNOME Tweaks, `lxappearance`, your DE's
appearance settings, or:

```bash
gsettings set org.gnome.desktop.interface gtk-theme "Celestial-Emerald-Dark"
gsettings set org.gnome.desktop.wm.preferences theme "Celestial-Emerald-Dark"
```

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
