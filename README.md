# FTMS-Rower

Web app for rowers with Bluetooth FTMS protocol support.  Displays live data from the rower and allows for exporting the data to a [TCX file](https://en.wikipedia.org/wiki/Training_Center_XML).

The web app can be accessed [via GitHub Pages here](https://adamgross42.github.io/FTMS-rower).  Or clone the repo and host it on your own web server.

Contributions are **very** welcome :)


## Supported browsers
Use Google Chrome on Android, Windows 10/11, Mac (M1 or Intel) and Ubuntu, but not iOS.

The web app is running directly in the browser and relies on some of the latest web technologies. Browsers like Firefox and Safari don't have support for them. On iOS, Safari is the only allowed browser, and even Chrome for iOS is just Safari with a Chrome skin. Browser support for the web version is the following:

| Chrome | Edge | Opera | Chrome Android | Samsung Internet | Firefox | Safari | Safari iOS | Chrome iOS |
|--------|------|-------|----------------|------------------|---------|--------|------------|------------|
| yes    | yes  | yes   | yes            | yes              | no      | no     | no         | no         |


### Browser configs
On Chrome, Edge and Opera for Linux you might need to turn on the experimental platforms feature flag at

- Chrome: `chrome://flags/#enable-experimental-web-platform-features`

- Edge: `edge://flags/#enable-experimental-web-platform-features`

- Opera: `opera://flags/#enable-experimental-web-platform-features`


## Project History

This was originally forked from a stale mirror https://github.com/manuelkamp/FTMS-rower with manual additions from the live app at https://www.kmpr.at/ftms/index.html.  That original project focuses on displaying a video while rowing, this fork focuses on collecting, displaying, and exporting the rowing data.


## About FTMS
The FTMS (FiTness Machine Service) protocol allows you to interact with many different fitness machines regardless of the brand.
It is a Bluetooth Low Energy (BLE) protocol that follows a [standard defined by Bluetooth Sig](https://www.bluetooth.com/specifications/specs/fitness-machine-service-1-0/).

You can read more about FTMS in this [blog post](https://medium.com/decathlondigital/take-control-of-your-fitness-machines-6588439aeeda).


## Resources
- [List of Bluetooth characteristic UUIDs](https://bitbucket.org/bluetooth-SIG/public/src/main/assigned_numbers/uuids/characteristic_uuids.yaml)
- [FTMS rower data characteristic documentation](https://bitbucket.org/bluetooth-SIG/public/src/main/gss/org.bluetooth.characteristic.rower_data.yaml)
- [TCX TrainingCenterDatabase XML Schema Definition](https://www8.garmin.com/xmlschemas/TrainingCenterDatabasev2.xsd)
- [TCX ActivityExtension XML Schema Definition](https://www8.garmin.com/xmlschemas/ActivityExtensionv2.xsd)
- [XML Validator](https://www.liquid-technologies.com/online-xsd-validator)