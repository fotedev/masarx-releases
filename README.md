# Masar X — Release Artifacts

This repository hosts the public release artifacts for the Masar X project.
The source code lives in the private repo [otedev/Masar-x-next](https://github.com/fotedev/Masar-x-next).

## What's in here?

- **NSIS installer**: Masar X-Setup-<version>-x64.exe (recommended)
- **Portable executable**: Masar X-Portable-<version>-x64.exe
- **Auto-update metadata**: latest.yml, latest-mac.yml, latest-linux.yml
- **Differential download blocks**: *.blockmap files

## How updates work

The desktop app uses [electron-updater](https://www.electron.build/auto-update) to check this
repo for new releases. On startup, it fetches latest.yml over HTTPS, compares versions,
and silently downloads + installs the new version on the next quit.

## How artifacts get here

Every push of a * tag to otedev/Masar-x-next triggers a GitHub Actions workflow
that builds the desktop installer and publishes it here via
electron-builder --publish onTagOrDraft. See Masar-x-next/.github/workflows/release.yml.

## License

Source code: proprietary, see otedev/Masar-x-next.
Build artifacts: distributed under the project's end-user license agreement.