# EMS-ESP Web Installer

Code and concept is based off [squeezelite-esp32-installer](https://github.com/sle118/squeezelite-esp32-installer) and uses [emsesp-web-tools](https://www.npmjs.com/package/emsesp-web-tools) which is a modified version of ESPHome's [esp-web-tools](https://github.com/esphome/esp-web-tools).

## Updating Firmware

When a new EMS-ESP Stable firmware is released the steps to follow are:

- Copy the firmware as `firmware.bin` to the `docs/artifacts/<mcu>` folder. Easiest way is to download the zip file from the [releases page](https://github.com/emsesp/EMS-ESP32/releases) and download the firmware `.bin` file, rename to `firmware.bin` and place in the correct folder. For example
  - S3 is "*-ESP32S3-16MB+.bin"
  - E32V2 is "*-ESP32-16MB+.bin"
- Update `docs/artifacts/manifest.json` updating the version and the idf (optional) in the `release_details` section.
- Update each `docs/artifacts/manifest-<mcu>.json` file with the new `version`

## Updating libraries

```sh
pnpm update
```

- Test locally with `pnpm dev` on <http://localhost:9090/>

Important! Keep the `saas` library fixed at version 1.77.6 otherwise the build will break.

## Testing

```sh
pnpm build
```

## Deploying

Just commit and push to the repository. Cloudflare pages will automatically build and deploy the new version. This will take less than a minute to complete. The web installer will be available at <https://install.emsesp.org>.

## Customizing

- Bootstrap web theme is from <https://bootswatch.com/cerulean/>. It's not easy to adjust the styling and colors mind you.
