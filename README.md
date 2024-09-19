# EMS-ESP Web Installer

Code and concept is based off [squeezelite-esp32-installer](https://github.com/sle118/squeezelite-esp32-installer) and uses [emsesp-web-tools](https://www.npmjs.com/package/emsesp-web-tools) which is a modified version of ESPHome's [esp-web-tools](https://github.com/esphome/esp-web-tools).

## Updating Firmware

When a new EMS-ESP Stable firmware is released the steps to follow are:

- Copy the firmware as `firmware.bin` to the `docs/artifacts/<mcu>` folder.
- Update `docs/artifacts/manifest.json` updating the version and the idf (optional) in the `release_details` section.
- Update each `docs/artifacts/manifest-<mcu>.json` file with the new `version` as well, making sure it does not starts with the letter `v`.
- Test locally with `yarn dev` on <http://localhost:9090/>
- Check-in the code. The project is built automatically by Cloudflare pages and hosted on <https://install.emsesp.org>

## Development Notes

- Because of the incompatibility we need keep the `saas` library fixed at version 1.77.6 in `package.json` so don't update it!
- Bootstrap web theme is from <https://bootswatch.com/cerulean/>. It's not easy to adjust the styling and colors mind you.
