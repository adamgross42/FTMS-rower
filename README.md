# FTMS-Rower

Webapp for rowers with FTMS protocol support.
Main feature is auto adjusted video playback (based on your rowing performance) to be more motivated and enjoy your workout.


## Note

Currently this is a proof-of concept and any progress will be documented here: [PoC](https://git.kmpr.at/kamp/FTMS-Rower/src/branch/main/docs/PoC.md)

Contributions are very welcome :)


## Usage
1.) clone the repo into your webserver directory  
2.) put a video named "video.mp4" into the video-folder. Optionally edit the poster in video/posters folder  
3.) open page in your browser on your android based phone or tablet - see [the list of supported browsers](#supported-browsers)  
4.) connect your rowing machine with the "connect"-button  
5.) exercise and enjoy the video :)  


## Supported browsers
Use Google Chrome on Android, Windows 10, Mac (M1 or Intel) and Ubuntu, but not iOS.

The Webapp is running directly in the browser and relies on some of the latest web technologies. Browsers like Firefox and Safari don't have support for them. On iOS Safari is the only allowed browser, and even Chrome for iOS is just Safari with a Chrome skin. Browser support for the web version is the following:

| Chrome | Edge | Opera | Chrome Android | Samsung Internet | Firefox | Safari | Safari iOS | Chrome iOS |
|--------|------|-------|----------------|------------------|---------|--------|------------|------------|
| yes    | yes  | yes   | yes            | yes              | no      | no     | no         | no         |


### Browser configs
On Chrome, Edge and Opera for Linux you might need to turn on the experimental platforms feature flag at

- Chrome: `chrome://flags/#enable-experimental-web-platform-features`

- Edge: `edge://flags/#enable-experimental-web-platform-features`

- Opera: `opera://flags/#enable-experimental-web-platform-features`


## Demo
Use this link for a quick [DEMO](https://www.kmpr.at/ftms/index.html)


## About FTMS
The FTMS (FiTness Machine Service) protocol allows you to interact with many different fitness machines
regardless of the brand. 
It is a Bluetooth Low Energy (BLE) protocol that follows a [standard defined by Bluetooth Sig](https://www.bluetooth.com/specifications/specs/fitness-machine-service-1-0/).

You can read more about FTMS in this [blogpost](https://medium.com/decathlondigital/take-control-of-your-fitness-machines-6588439aeeda)


## Bluetooth resources to FTMS
- [List of characteristic UUIDs](https://bitbucket.org/bluetooth-SIG/public/src/main/assigned_numbers/uuids/characteristic_uuids.yaml)
- [Rower data characteristic documentation](https://bitbucket.org/bluetooth-SIG/public/src/main/gss/org.bluetooth.characteristic.rower_data.yaml)