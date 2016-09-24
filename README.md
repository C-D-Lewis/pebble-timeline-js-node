# pebble-timeline-js-node

Node.js module for pushing shared (topic) pins to app users.

## Installation

`npm install --save pebble-timeline-js-node`


## Methods

`insertSharedPin(pin, topics, apiKey, callback)` - insert a shared pin for the topics in the `topics` array.

`deleteSharedPin(pin, topics, apiKey, callback)` - delete a previously pushed pin.

`setAppGlances(slices, userToken, callback)` - set the current collection of AppGlance slice objects. Requires the user's timeline token, obtained using PebbleKit JS.


## Example Usage

**Push a shared pin**

```js
var timelinejs = require('pebble-timeline-js-node');

var pin = {
  id: 'example-pin-generic-d2sd3d5bdsd',
  time: new Date().toISOString(),
  layout: {
    type: 'genericPin',
    title: 'timelinejs shared pin test',
    tinyIcon: 'system://images/NOTIFICATION_FLAG'
  }
};
var topics = ['default'];
var apiKey = 'REDACTED';

timelinejs.insertSharedPin(pin, topics, apiKey, function(responseText) {
  console.log('Result: ' + responseText);
});
```

**Set an AppGlance**

```js
var slices = [
  {
    layout: {
      subtitleTemplateString: 'Hello from AppGlance REST!'
    }
  }
];
var userToken = 'REDACTED';

timelinejs.setAppGlances(slices, userToken, function(responseText) {
  console.log('AppGlance result: ' + responseText);
});
```


## TODO

Add methods for wrapping the
[AppGlance REST API](https://developer.pebble.com/guides/user-interfaces/appglance-rest).

