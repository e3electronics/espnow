#ESPNOW library for mOS

## Introduction

ESPNOW is a point to point communication protocol supported by the ESP32. It can send and receive 251 byte long messages from device to device.

## Features

* Loading peers from json file
* Subscribing to received messages from specific peers
* Subscribing to "broadcast" messages. Messages are considered broadcast when sent from peers not in memory. Broadcast needs to be enabled in config schema.
* Subscribing to messages sent from any registered peer
* Subscribing to sent message callbacks.
* Adding and removing peers from memory and json file
* Encryption is not supported.

## Config Schema

* enable: Enable the library
* peers_filename: Filename to load the ESPNOW peers.
* enable_broadcast: Enable registering an internal peer to receive broadcast messages
* debug_level: DBG level to print to console

## Peers JSON format

The peers json file will be parsed and loaded into memory. It will not report if the maximum peers limit has been reached.


    [
        {
            "name": "ESP1",  //Peer name. Required. Used to locate peer inside the library.
            "mac": "24:0a:c4:09:06:4d" //MAC Address. Required. Format as outlined before, with colons.
            "channel": 6 //Wireless channel peer is listening to. Optional. If missing the channel will be set the same in wifi.ap.channel
            "softap": true //Whether the peer is using the AP interface to receive messages. Optional. Will default to true
        }
    ]

## Stuff To do

* mJS bindings
* Encryption support
* esp8266 support

## Stuff to test

ESPNOW is not a very documented protocol, even broadcast is not really spoken about on the official docs. There might be edge cases not addressed by this library. Contributions are always welcome!