# Hello App

Hello App is a minimal command-line package used to verify the DeepSO package
installation and executor handshake.

The `.dso` archive at `packages/hello-app.dso` contains:

- `manifest.json`: package and application metadata.
- `roles/HelloApp.sprite3`: the importable Scratch process role.
- `icons/hello.svg`: the application icon.

The source at `source/main.fractch` starts its listener on the executor's
`DSO_PROCESS_WAKE` broadcast, waits for `_DSO_START_REQUEST` to equal
`hello-app`, appends a greeting to `_DSO_OUTPUT_BUFFER`, acknowledges startup,
and signals that the one-shot process has exited.
