# DeepSO Package Repository

This repository hosts installable DeepSO packages and their index.

## Add this repository to DeepSO

Enter these commands in the DeepSO terminal:

```text
pkg repo https://raw.githubusercontent.com/Deep-sea-lab/deepso-packages/main
pkg search
pkg install desk-clock
pkg install click-counter
pkg install welcome-center
pkg install techfure-desktop
run techfure-desktop
run desk-clock
```

Press Escape to close the graphical demo apps and return to terminal input.
The repository also includes `hello-app`, a command-line process example.

## Graphical demos

- `desk-clock` displays the current time.
- `click-counter` increments when its page is clicked.
- `welcome-center` shows common DeepSO commands.
- `techfure-desktop` packages the original TechFure desktop UI with system
  operations disabled.

These are single-stage GUI prototypes, not managed desktop windows.

## Repository layout

- `index.json` lists packages available to the in-system package manager.
- `packages/<id>.dso` is the package archive downloaded by `pkg install`.
- `packages/<id>/manifest.json`, `source/`, and `icons/` contain reviewable
  package metadata, Fractch source where available, and artwork.

The package uses DeepSO package format version 1. Its manifest declares the
app ID, imported role, icon, executor API, and process entry.

## Contributing

Fork this repository, add a validated `.dso` archive and its reviewable source,
update `index.json`, then open a pull request. Never include credentials or
executable JavaScript in a package.
