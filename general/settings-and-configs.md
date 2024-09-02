# Settings & Configs

IDCamPro works with global (computer wide) settings and local (loadable) configs.&#x20;

## Configs

Configs are loadable environments that hold the following settings:

* Cameras
* Timing systems
* RACE RESULT integration
* Other, undocumented settings

Configs can be loaded and stored away for future use. E.g. you can have a config for cross-country events and running events in case you use different cameras or timing systems for these events.&#x20;

Config settings can be accessed via `Config` - `Settings`. Config files are plain JSON files having a `.IDCamProConfig` extension.

## Global Settings

These usually do **not** need to be changed and contain the following settings:

* Theme (dark, light, off)
* Prevent system from sleep when app is active
* Many other, usually undocumented settings

Global settings can be accessed via `?` - `Extended Settings`. The single setting file is a plain JSON called `Settings.json`.

## Location

You can access the folder containing the global settings file and - usually - also the competitions themselves and config files by clicvking on `?` - `Open Settings Folder`

Location: `%localappdata%\dbnetsoft\IDCamPro`

