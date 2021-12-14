# Magento 2 Upgrade GUI

This is an Electron app to make it easier for you to read and process the output files of the [Ampersand Magento2 Upgrade Patch Helper](https://github.com/AmpersandHQ/ampersand-magento2-upgrade-patch-helper).

To use this app, you will need the following files in your Magento 2 directory;
- `vendor` (regular composer directory)
- `vendor.patch` (generated by the upgrade patch helper)
- `vendor_files_to_check.patch` (generated by the upgrade patch helper)
- `patch-helper-output.txt` (the output generated by the upgrade patch helper, directed from stdout to a file)
- `classmap.json` (see below)

You will need to generate the `classmap.json` file yourself. This is needed because the tool needs to map PSR-4 classnames to actual filenames, which Composer can do for us. Run this command to generate the file;

```bash
php -r "\$classmap=require_once('vendor/composer/autoload_classmap.php'); echo json_encode(\$classmap);" > classmap.json
```

## Project setup

We don't have a built binary yet since this is definitely a work in progress.

Clone this repo and run this command to install all necessary dependencies:

```
yarn install
```

## Start

To start (developing) the app, you can run:

```
yarn electron:serve
```
