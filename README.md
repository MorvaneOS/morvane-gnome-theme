# morvane-gnome-theme

Makes the MorvaneOS look GNOME's default: dark style, pink accent, the
`MorvaneOS-Dark` GTK theme, candy-icons, the Sandrone cursor, the Twilight
wallpaper on the desktop and Minimal on the lock screen.

The look itself is in [morvane-gtk-theme](https://github.com/MorvaneOS/morvane-gtk-theme)
(the GTK themes and libadwaita colours) and
[morvane-wallpapers](https://github.com/MorvaneOS/morvane-wallpapers); this package
installs a GSettings override
(`/usr/share/glib-2.0/schemas/90_morvane-gnome-theme.gschema.override`) that
makes them GNOME's defaults. Overrides only change defaults, so anything set in
GNOME Settings still wins. The MorvaneOS installer installs this package with
GNOME.

## Light mode

Choosing **Light** in Settings → Appearance switches libadwaita apps (most GNOME
apps) to MorvaneOS Light straight away. Older GTK 3 apps stay on the GTK theme,
MorvaneOS-Dark; for them, also run:

```
gsettings set org.gnome.desktop.interface gtk-theme MorvaneOS-Light
```

GNOME Shell's accent comes from GNOME's fixed set of accent colours, so it's
GNOME's pink, the nearest to Pastel Pink. Apps use the exact MorvaneOS colours.

## Changing it

Edit `tools/build.py`, then:

```
python tools/build.py
```

Needs only Python. Commit the output, bump `pkgver`, build and publish.

## License

LGPL-2.1-or-later.
