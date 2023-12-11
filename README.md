# Frontier Smart Firmware Binaries

This repository is an updated version of [frontier-silicon-firmwares](https://github.com/cweiske/frontier-silicon-firmwares) by cweiske and stores at least 35 more binaries.

* Blog post: https://cweiske.de/tagebuch/frontier-firmware-dl.htm
* Firmware Analysis: https://matrixeditor.github.io/fsapi-tools/firmware-structure.html
* Known radios: see [this](KNOWN-RADIOS.md) file

## Repository Structure

The respository stores all firmware binaries according to their file name in different sub-directories. By now, the following directories have been added:

    frontier-smart-firmwares/
        ├───ir/
        │   ├───cui/
        │   │   └───FS2340/
        │   ├───fsccp/
        │   │   └───FS2026/
        │   ├───mmi/
        │   │   ├───FS2026/
        │   │   ├───FS2028/
        │   │   └───FS2340/
        │   └───ser/
        │       └───FS2026/
        └───ns/
            └───mmi/
                └───FS5332/

## Download Templates

For older products with Venice modules, the URL consists of the following:

```bash
URL="https://update.wifiradiofrontier.com/Update.aspx?f=/updates/$FILE_NAME.isu.bin"
```

* **Important**: The `$FILE_NAME` must replace the `"_V"` string with a simple dot (`"."`).
* This URL template can be applied all modules except from `FS2340` and `FS5332`.

### FS5332

URL template for firmware binaries of radios with the Minuet module:

```bash
URL="https://nuv-isu-cdn.azureedge.net/nsupdates/nsupdates/$CUSTOMISATION/$FILE_NAME.ota.bin
```

* The customisation can be retrieved by splitting the file name on `"_"`.


### FS2340

URL template for firmware binaries of radios with the Venice X module:

```bash
URL="https://nuv-isu-cdn.azureedge.net/srupdates/srupdates/$CUSTOMISATION/$FILE_NAME.ota.bin
```

* The customisation can be retrieved by splitting the file name on `"_V"`.

## Updates

Known firmware versions are listed in ``known-versions.txt``. To search for updates or download them, you can use the `fsapi` module presented in the [fsapi-tools](https://github.com/MatrixEditor/fsapi-tools) repository