<!-- Update this file before each tagged release. -->
<!-- The workflow appends auto-generated commit notes below this body. -->

## Highlights

<!-- Replace with the key changes for this release -->
- **Project renamed to comply with the [COSMIC trademark policy](https://github.com/pop-os/cosmic-epoch/blob/master/TRADEMARK.md)** (#5):
  - Package: `cosmic-flux` → `cosmic-ext-flux`
  - Binaries: `cosmic-ext-flux-daemon`, `cosmic-ext-applet-flux`
  - App ID / D-Bus: `com.system76.*` → `io.github.franz_net.*`
  - Display name: **Flux** — live video wallpapers for the COSMIC™ desktop
- Installing this package automatically removes the old `cosmic-flux` package and its systemd service
- Existing settings are migrated automatically on first start — no reconfiguration needed

## Install

```sh
sudo apt-get install -y gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-vaapi
sudo dpkg -i cosmic-ext-flux_<version>_amd64.deb
```

Add the **Flux** applet to your panel via Settings > Desktop > Panel > Applets.

## Uninstall

```sh
systemctl --user disable --now cosmic-ext-flux-daemon
sudo dpkg -r cosmic-ext-flux
```

## Requirements

- COSMIC desktop environment
- GStreamer 1.x with video decode plugins
- VA-API drivers recommended for hardware decode
