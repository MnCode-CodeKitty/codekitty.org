# Basic notes

WebSerialAPI is a browser API to connect the browser to a locally attached serial device (real or "virtual" via usb/bluetooth/etc).  [xterm.js](https://xtermjs.org/) is a javascript library thingy to create a terminal window in the browser to in this case interact with the WebSerial API.  Its what all the cool kids like vscode use.

## Useful links

- [List of xterms event triggers and methods](https://xtermjs.org/docs/api/terminal/classes/terminal/)
- [meat of using WebSerial](https://codelabs.developers.google.com/codelabs/web-serial#3)
- [super simple WebSerial example](https://github.com/svendahlstrand/web-serial-api)


super simple case:

````javascript
// Initialize xterm.js and attach it to the DOM
const xterm = new Terminal();
xterm.open(document.getElementById('xterm'));

// Setup communication
// xterm.onData is triggered when stuff typed into terminal window and passes that in 
// as "data" to webserial write stream
xterm.onData('data', (data) => {
  webserial.write(data);
});
// when webserial reads in data, it can write it to the terminal
// this is over simplified, see the above link on "meat of using webserial
webserial.read('data', function (data) {
  xterm.write(data);
});
````