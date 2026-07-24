# celestial-themes

A large family of ready-to-install desktop themes — **65 named colours ×
3 modes = 195 themes**, plus 390 companion folders carrying HiDPI xfwm4
decorations and 195 matching Kvantum themes for Qt apps. Each theme covers
every common Linux desktop surface: GTK 2/3/4, GNOME Shell, Cinnamon, Unity,
xfwm4, Metacity, Openbox, labwc, Plank and Qt — and, for KDE Plasma, a matching
colour scheme, global theme, desktop theme and Aurorae window decoration per
variant (see [KDE Plasma](#kde-plasma) below).

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

### The `Kvantum/` folder

`Kvantum/` holds a matching Qt theme for each of the 195 themes — same accent,
same three modes. Qt apps don't read GTK themes, so without these they stay on
whatever style Qt defaults to while everything else follows your colour.

They install to their own location, not into `~/.themes` (see below). There is
no `-hdpi` tier — Kvantum is vector-based and scales by itself.

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

### Qt apps

Copy the matching Kvantum theme into place, then select it once:

```bash
mkdir -p ~/.config/Kvantum
cp -r Kvantum/Celestial-Emerald-Dark ~/.config/Kvantum/

sudo pacman -S kvantum        # Arch
kvantummanager                # pick Celestial-Emerald-Dark, then Use this theme
```

System-wide the destination is `/usr/share/Kvantum/` instead. Qt apps then
follow the same accent as GTK.

## KDE Plasma

Every colour also ships native KDE Plasma theming, delivered from the repo's
`kde/` tree into the standard Plasma locations:

| Artifact | Repo source | Installed to |
|----------|-------------|--------------|
| Colour scheme | `kde/color-schemes/Celestial-<Colour>[-Dark\|-Light].colors` | `/usr/share/color-schemes/` |
| Global theme | `kde/look-and-feel/com.github.zquestz.Celestial-<Colour>…/` | `/usr/share/plasma/look-and-feel/` |
| Desktop theme | `kde/desktoptheme/Celestial-<Colour>…/` | `/usr/share/plasma/desktoptheme/` |
| Window decoration | `kde/aurorae/Celestial-<Colour>…/` | `/usr/share/aurorae/themes/` |

Pick a variant under **System Settings → Global Theme**; it sets the colour
scheme, Kvantum widget style, Celestial Aurorae decorations, Papirus icons and a
Celestial splash. The generated (non-stock) colours leave your current wallpaper
untouched, since they ship no per-colour wallpaper package. Qt widget styling
still comes from the matching `Kvantum/` theme — set it once in Kvantum Manager
(a global theme can select *Kvantum* but not *which* Celestial variant).

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
