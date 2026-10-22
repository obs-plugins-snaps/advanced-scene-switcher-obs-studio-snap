# Advanced Scene Switcher Snap for OBS Studio

[![advanced-scene-switcher-obs-studio](https://snapcraft.io/advanced-scene-switcher-obs-studio/badge.svg)](https://snapcraft.io/advanced-scene-switcher-obs-studio)

This snap delivers [advanced-scene-switcher](https://github.com/WarmUpTill/SceneSwitcher) to the
[OBS Studio snap](https://snapcraft.io/obs-studio).

Advanced Scene Switcher is a plugin for OBS Studio that offers automatic
scene switching based on various conditions including application focus,
audio volume, time, file content, and much more.

## Installation

### Install from the Store

Once the snap is published in the store:

```shell
sudo snap install advanced-scene-switcher-obs-studio
```

### Connect to the OBS Studio snap

```shell
sudo snap connect obs-studio:obs-plugins advanced-scene-switcher-obs-studio:obs-plugins
```

Once connected, the plugin will be available in OBS Studio after restarting it.

## Development

```shell
snapcraft
```

The plugin is built against the libobs headers shipped in the
`obs-studio` snap, so no local OBS build is required.

The snap starts in `devel` grade; flip it to `stable` in
`snap/snapcraft.yaml` once the packaged plugin is verified to work.
