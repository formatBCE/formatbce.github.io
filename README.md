# formatbce.github.io

This repository is the GitHub Pages user site of formatBCE. It holds no firmware source. The firmware is in
[formatBCE/Respeaker-ESPHome-integration](https://github.com/formatBCE/Respeaker-ESPHome-integration).

## Content

| Path | Function |
| --- | --- |
| `index.html` | Sends visitors to the [web installer](https://formatbce.github.io/Respeaker-ESPHome-integration/). |
| `Respeaker-Lite-ESPHome-integration/` | Bridge for Respeaker Lite factory devices. |
| `Respeaker-XVF3800-ESPHome-integration/` | Bridge for Respeaker XVF3800 factory devices. |
| `Koala-Satellite/` | Bridge for Koala Satellite factory devices. |
| `.nojekyll` | Stops Jekyll, so that GitHub Pages serves the files as they are. |

## The bridges

A factory device gets updates from the manifest URL in its firmware. Devices from before the monorepo migration use
the Pages paths of the three old repositories. Those project sites do not exist any more, so GitHub serves these
folders at the same paths.

Each folder holds a copy of release 2026.11.1 of one device: `manifest.json`, the factory image, and the OTA image. The
firmware of that release reads the new manifest URL. So a device installs the bridge one time and then gets updates
from the monorepo. The `index.html` of each folder sends visitors to the new installer of the device.

## Rules

- Do not change or delete the bridge folders. A device that is offline for a long time still needs them.
- Do not update the bridges for a new release. The devices find new releases at the new URL.
- Do not turn on Pages in a repository with the name of a bridge folder. A project site has priority over a folder of
  the user site, so it hides the bridge.
- Do not create a repository with the name `Respeaker-Lite-ESPHome-integration`. GitHub then stops the redirect of the
  renamed repository.

Written to ASD-STE100 rules.
