# EMS-ESP Web Installer

Code and concept is based off squeezelite-esp32-installer <https://github.com/sle118/squeezelite-esp32-installer> and uses <https://github.com/esphome/esp-web-tools/releases>.

## Updating Firmware

When a new EMS-ESP Stable firmware is released the steps to follow are:

- copy the firmware as `firmware.bin` to the `docs/artifacts/<mcu>` folder.
- update `docs/artifacts/manifest.json` updating the version and the idf in the `release_details` section.
- update the `docs/artifacts/manifest-<mcu>.json` file with the new `version`, which starts with a `v`.
- Test locally with `yarn dev` and <http://localhost:9090/>
- Check-in the code. The project is built automatically by Cloudflare pages and hosted on <https://install.emsesp.org>

## Development Notes

- Because of the incompatibility we need keep the `saas` library fixed at version 1.77.6 in `package.json`.
- Theme is from <https://bootswatch.com/cerulean/>
