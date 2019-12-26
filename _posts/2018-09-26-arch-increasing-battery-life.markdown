---
layout: post
title: (Arch) Increasing battery life with powertop and TLP
date: 2018-09-16 11:23
post-link: https://wiki.archlinux.org/index.php/Powertop
---
There are two important tools for optimizing battery performance of Arch on laptops: TLP and powertop. This applies to most distros, not just Arch.

# TLP

Install using pacman or whatever package manager comes with your distro:

```
pacman -S tlp
```

Then enable the serviced:

```
systemctl enable tlp
systemctl start tlp
```

Now we can have a look at the system with `sudo tlp-stat` which will output a bunch of information about the system. `sudo tlp-stat -s` is the summarised version.

We can get data on usb ports with `sudo tlp-usblist`.

I suppose people smarter than me might know how to tweak every parameter of TLP's configuration to achieve optimum performance. The active configuration file can be found by `sudo tlp-stat -c` which will display the file's location and active parameters. To modify the configuration, modify the file and restart the service.

# powertop

As before:

```
pacman -S powertop
```

And enable the service.

To check out a detailed table of processes and their power consumptions simply `sudo powertop`. Hit tab to display other tabs.

powertop offers an auto-tune option: `powertop --auto-tune`. The [The ArchWiki entry](https://wiki.archlinux.org/index.php/Powertop) suggests running this at boot, hence modify the systemd service file at `/etc/systemd/system/powertop.service`:

```
[Unit]
Description=Powertop tunings

[Service]
Type=exec
ExecStart=/usr/bin/powertop --auto-tune
RemainAfterExit=true

[Install]
WantedBy=multi-user.target
```
