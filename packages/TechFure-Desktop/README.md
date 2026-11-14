# TechFure UI-only build

This build is derived from the original `TechFure3.0-Beta1.01.sb3`. It keeps
the original TechFure wallpaper, desktop, dock, icons, and UI roles. The
original SB3 is not modified.

The UI starts directly at the desktop. Onboarding, lock screen, kernel,
external-app importing, external network requests, file pickers, video
playback, runtime/system controls, and project-asset mutation are removed.
Remaining UI controls only navigate or animate the existing interface.

## Build

From the project root:

```sh
node TechFure-UI-Only/build.mjs
```

The build produces `TechFure3.0-UI-Only.sb3` for standalone preview and
`TechFure-Desktop.dso` with a DeepSO GUI-app manifest and the original UI
roles. The controller uses the `techfure-desktop`
start/acknowledge/stop/exit handshake. Escape closes the application.

The standalone SB3 passed archive and block-graph validation, but was not
launched in a Scratch-compatible runtime in this workspace. The DSO archive
and role names are validated, but installation inside a running DeepSO host
could not be exercised; the original desktop roles share Stage-level state, so
confirm that the host importer preserves those shared variables before
relying on the DSO package.
