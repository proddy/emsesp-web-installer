# EMS-ESP Web Installer

Code and concept is based off [squeezelite-esp32-installer](https://github.com/sle118/squeezelite-esp32-installer) and uses ESPHome's [esp-web-tools](https://github.com/esphome/esp-web-tools/releases) which Home Assistant and Tasmota also use.

## Updating Firmware

When a new EMS-ESP Stable firmware is released the steps to follow are:

- copy the firmware as `firmware.bin` to the `docs/artifacts/<mcu>` folder.
- update `docs/artifacts/manifest.json` updating the version and the idf (optional) in the `release_details` section.
- update each `docs/artifacts/manifest-<mcu>.json` file with the new `version` as well, making sure it does not starts with the letter `v`.
- Test locally with `yarn dev` on <http://localhost:9090/>
- Check-in the code. The project is built automatically by Cloudflare pages and hosted on <https://install.emsesp.org>

## Development Notes

- Because of the incompatibility we need keep the `saas` library fixed at version 1.77.6 in `package.json` so don't update it!
- Theme is from <https://bootswatch.com/cerulean/>. It's not easy to adjust the styling.
