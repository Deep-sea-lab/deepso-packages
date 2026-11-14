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
run desk-clock
```

Press Escape to close the graphical demo apps and return to terminal input.
The repository also includes `hello-app`, a command-line process example.

## Graphical demos

- `desk-clock` displays the current time.
- `click-counter` increments when its page is clicked.
- `welcome-center` shows common DeepSO commands.

These are single-stage GUI prototypes, not managed desktop windows. Each role
waits for the executor's `DSO_PROCESS_WAKE` broadcast, checks its app ID in
`_DSO_START_REQUEST`, acknowledges with `_DSO_START_ACK`, and reports exit
through `_DSO_APP_EXITED`.

## Repository layout

- `index.json` lists packages available to the in-system package manager.
- `packages/<id>.dso` is the package archive downloaded by `pkg install`.
- `packages/<id>/manifest.json`, `source/`, and `icons/` contain reviewable
  package metadata, Fractch source, and artwork.

The package uses DeepSO package format version 1. Its manifest declares the
app ID, imported role, icon, executor API, and process entry.

## Contributing

Fork this repository, add a validated `.dso` archive and its reviewable source,
update `index.json`, then open a pull request. Never include credentials or
executable JavaScript in a package.
