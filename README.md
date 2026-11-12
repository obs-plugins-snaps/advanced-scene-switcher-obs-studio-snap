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

## E2E tests

The repository ships a small pytest suite (`tests/e2e`) that starts a
headless Wayland session, drives OBS through the accessibility tree, and
checks that the plugin's module is actually loaded. CI runs it on every
pull request against the exact snap built in that run (non-blocking
while the suite soaks). Plugins extend the suite with tests for their
own UI surface.

To run it locally, install the snap and connect it as above, then run
the suite from the shared workflows checkout:

```shell
E2E_OBS_HOME="$PWD/e2e-home" \
  uv run --project /path/to/obs-plugins-snaps/workflows \
  pytest tests/e2e
```

Screenshots, logs and state are collected under `$E2E_OBS_HOME`
(`e2e-home/` above) for triage.
