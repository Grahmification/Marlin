
<h1 align="center">Marlin 3D Printer Firmware</h1>

<p align="center">
    <a href="/LICENSE"><img alt="GPL-V3.0 License" src="https://img.shields.io/github/license/marlinfirmware/marlin.svg"></a>
    <a href="//github.com/MarlinFirmware/Marlin/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/marlinfirmware/marlin.svg"></a>
    <a href="//github.com/MarlinFirmware/Marlin/releases"><img alt="Last Release Date" src="https://img.shields.io/github/release-date/MarlinFirmware/Marlin"></a>
    <a href="//github.com/MarlinFirmware/Marlin/actions/workflows/ci-build-tests.yml"><img alt="CI Status" src="https://github.com/MarlinFirmware/Marlin/actions/workflows/ci-build-tests.yml/badge.svg"></a>
    <a href="//github.com/sponsors/thinkyhead"><img alt="GitHub Sponsors" src="https://img.shields.io/github/sponsors/thinkyhead?color=db61a2"></a>
    <br />
    <a href="//bsky.app/profile/marlinfw.org"><img alt="Follow marlinfw.org on Bluesky" src="https://img.shields.io/badge/Follow%20@marlinfw.org-0085ff?logo=bluesky&logoColor=white"></a>
    <a href="//fosstodon.org/@marlinfirmware"><img alt="Follow MarlinFirmware on Mastodon" src="https://img.shields.io/mastodon/follow/109450200866020466?domain=https%3A%2F%2Ffosstodon.org&logoColor=%2300B&style=social"></a>
</p>

This is a fork of Marlin Firmware V2.1 setup for the [BigTreeTech SKR Mini E3 V3.0](https://biqu.equipment/collections/control-board/products/btt-skr-mini-e3-v2-control-board) control board. It is based off the respective [Ender-3 Configuration](https://github.com/MarlinFirmware/Configurations/tree/import-2.1.x/config/examples/Creality/Ender-3/BigTreeTech%20SKR%20Mini%20E3%203.0).

Official documentation can be found at the [Marlin Home Page](//marlinfw.org/).


## Building Marlin 2.1

To build and upload Marlin you will use one of these tools:

- The free [Visual Studio Code](//code.visualstudio.com/download) using the [Auto Build Marlin](//marlinfw.org/docs/basics/auto_build_marlin.html) extension.
- Marlin is optimized to build with the [PlatformIO IDE](//platformio.org/) extension for Visual Studio Code.
- You can also use VSCode with devcontainer : See [Installing Marlin (VSCode devcontainer)](https://marlinfw.org/docs/basics/install_devcontainer_vscode.html).


## Board Setup and Testing

NOTE: Stepper motors don't have to be plugged into to test basic firmware functionality.

To test firmware functionality:
1. Format the microSD to FAT32.
2. Compile the firmware.
3. Copy the `.bin` file to the microSD card.
4. Insert the SD card into the control board.
5. If not using external power supply, jumper the two header pins on the board labelled `SW_USB` (next to microSD port).
   * **NOTE: THIS JUMPER MUST BE UNCONNECTED IF USING AN EXTERNAL POWER SUPPLY.** It will fry the computer's USB port.
6. Plug in the board via USB.
7. Connect to the board with [Pronterface](https://www.pronterface.com/).
8. Try sending an `M115` command to query firmware capabilities.


## Reference Info

Tutorials:
* [Marlin IDE Setup Guide](https://www.youtube.com/watch?v=eq_ygvHF29I)
* [Beginner guide to editing Marlin firmware](https://www.youtube.com/watch?v=J9vxJT5Tgh4)
* [SKR Mini E3 Firmware Config Tutorial](https://3dwork.io/en/skr-mini-e3-v3/)

SKR Mini E3 Board:
* [User Manual](https://cdn.shopify.com/s/files/1/1619/4791/files/BTT_SKR_MINI_E3_V3.0_user_manual_1.pdf?v=1709120881)
* Official Firmware: [Compiled](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/firmware/V3.0), [Source Code](https://github.com/bigtreetech/Marlin/tree/SKR-mini-E3-V3.0-G0B1)
* [Hardware Repo](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/hardware/BTT%20SKR%20MINI%20E3%20V3.0/Hardware)
  * [Pinouts](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/blob/master/hardware/BTT%20SKR%20MINI%20E3%20V3.0/Hardware/BTT%20E3%20SKR%20MINI%20V3.0_PIN.pdf)
  * [Electrical Schematic](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/blob/master/hardware/BTT%20SKR%20MINI%20E3%20V3.0/Hardware/BTT%20E3%20SKR%20MINI%20V3.0_SCH.pdf)

## License

*Copied from Marlin License*

Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on GitHub, perform your modifications, and direct users to your modified fork.
