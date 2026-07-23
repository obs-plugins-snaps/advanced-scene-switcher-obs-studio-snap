# Advanced Scene Switcher Snap for OBS Studio

This snap delivers [Advanced Scene Switcher](https://github.com/WarmUpTill/SceneSwitcher) to the [OBS Studio snap](https://snapcraft.io/obs-studio). Advanced Scene Switcher enables automatic scene switching based on application focus, audio volume, time, file content, and many other conditions.

## Installation

### Install from the Store

```shell
sudo snap install advanced-scene-switcher-obs-studio
```

### Connect to the OBS Studio snap

```shell
sudo snap connect obs-studio:obs-plugins advanced-scene-switcher-obs-studio:obs-plugins
```

Once connected, Advanced Scene Switcher will appear in OBS Studio under **Tools → Advanced Scene Switcher**.
