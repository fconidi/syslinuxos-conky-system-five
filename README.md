# SysLinuxOS Conky System Five

A transparent Conky desktop monitor inspired by [MX-Lua](https://github.com/MX-Linux/mx-conky-data/tree/master/themes/MX-Lua). Blue rings descend across the panel for CPU, RAM, swap, disk and network activity. The clock has three concentric rings; the distribution logo, battery, current network details and top processes complete the display.

The panel follows the monitor resolution and detects the active network interface, logical CPU count, distribution, battery and storage on the current computer. It works on desktops without a battery. Its own launcher and runtime directory let it run independently of other Conky themes.

## Install

With the SysLinuxOS APT repository configured:

```sh
sudo apt update
sudo apt install syslinuxos-conky-system-five
```

Or install the downloaded package with APT:

```sh
sudo apt install ./syslinuxos-conky-system-five_0.1.0_all.deb
```

The shared `syslinuxos-conky-menu` dependency supplies the Conky submenu and launcher icon.

## Use

Open **System Tools > Conky > Start Conky-System-Five** or **Stop Conky-System-Five**. The same labels appear in every locale.

```sh
syslinuxos-conky-system-five start
syslinuxos-conky-system-five stop
syslinuxos-conky-system-five status
```

The panel is centered at the right edge. All text, rings, spacing and dimensions scale together. Restart the theme after changing the screen resolution. An optional manual scale is available:

```sh
CONKY_SYSTEM_FIVE_SCALE=1.2 syslinuxos-conky-system-five start
```

The network panel follows the default route and shows local and external IPv4 addresses and ISP. To select an interface manually, set `CONKY_NET_INTERFACE=enp3s0`. Route changes are detected within ten seconds. External IPv4 comes from ipify every five minutes; ISP comes from IPinfo every hour. HTTPS lookups run in the background with a three-second timeout and cached results. An unavailable value is shown as `N/A`.

The editable template is `/etc/conky/syslinuxos-conky-system-five.conf`; dpkg preserves edits across upgrades. A compositing window manager provides full alpha transparency.

## Build

```sh
bash build-deb.sh
```

The package is produced in `dist/`.

## License

Copyright 2026 Franco Conidi. GPL-3.0-or-later; see [LICENSE](LICENSE). The layout is inspired by MX-Lua, distributed by MX Linux. No MX-Lua code or image is included.
