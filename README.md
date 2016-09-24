# pebble-timeline-js-node

Node.js module for pushing shared (topic) pins to app users.

## Installation

`npm install --save pebble-timeline-js-node`


## Example Usage

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
