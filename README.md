# Export Tabs URLs

https://github.com/clach04/export-tabs-urls/ is a fork of alct's (Andre Loconte) export-tabs-urls

Features that the original did not have:

  * Google Chrome, Microsoft Edge, and Mozilla Firefox support - thanks to https://github.com/skend/export-tabs-urls/tree/chrome-release (tested Chrome Version 119.0.6045.200 (Official Build) (64-bit), Firefox 120.0.1 (64-bit), Edge Version 119.0.2151.93 (Official build) (64-bit))

## Dev notes

### Chrome

  * open More tools, then Extensions (open chrome://extensions/ )
  * then toggle Developer mode.
  * "Load unpack", select checkout directory

See http://blog.glavin.org/BurntChrome/docs/ for screenshots.

Use `chrome.extension.getBackgroundPage().console.log()` and then click on "Inspect views background page" to see console.

  * https://developer.chrome.com/extensions/extension
  * https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/extension/getBackgroundPage
  * https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getBackgroundPage


### Firefox

  * open about:debugging#/runtime/this-firefox
  * "Load Temporary Add-on.."
  * select checkout directory, and open `manifest.json`

https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension

    npm install  web-ext
    web-ext lint
    web-ext build
    web-ext sign --api-key=$AMO_JWT_ISSUER --api-secret=$AMO_JWT_SECRET
    web-ext sign --api-key=%AMO_JWT_ISSUER% --api-secret=%AMO_JWT_SECRET%

Uploading an **unlisted** extension will allow download of xpi for selt-hosted distribution but can never be made public.
Mozilla requires a new version to be uploaded and made public at upload time (i.e. version bump required).


### Edge

Similar to Chrome (same engine under the covers).

  * open edge://extensions/
  * toggle Developer mode.
  * "Load unpack", select checkout directory

## Porting

  * https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension/
  * https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Chrome_incompatibilities

Original readme below from https://github.com/alct/export-tabs-urls

---------

[Export Tabs URLs](https://addons.mozilla.org/en-US/firefox/addon/export-tabs-urls-and-titles/) (ETU) is a Web browser extension that allows to list the URLs of all the open tabs and copy that list to clipboard or export it to a timestamped file.

Consider this add-on done (except for bugfixes). I may or may not add new features depending on the fun (or lack of it).

## Features

- **Include titles** : ETU provides a default format which displays titles along tabs URLs ;
- **Custom format** : optionally, custom patterns can be defined instead of the default "include titles" one (e.g. markdown) ;
- **Filter tabs** : ETU provides a RegExp-enabled tabs filter ;
- **Limit to current window** : optionally, the list can be limited to the current window ;
- **List non-HTTP(s) URLs** : optionally, ETU can list each and every tab, including cases where the URL scheme isn't HTTP(s)

## Permissions

- **Access browser tabs** : required to list the tabs ;
- **Input data to the clipboard** : required to copy the list to the clipboard ;
- **Display notifications** : not required stricto sensu (as the extension could work without it) but it is used to improve the user experience by providing visual feedback about what is going on ;
- **Storage** : required to store settings.

## Screenshots

![screenshot-1](https://imgs.be/5cadf463-2668.png)
![screenshot-2](https://imgs.be/5cadf439-1411.png)
![screenshot-3](https://imgs.be/5cadf44d-1457.png)

## License

[GPLv3](LICENSE)
