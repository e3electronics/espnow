ESPNOW library for Moongoose OS

Peers JSON format


    [
        {
            "name": "ESP1",  //Peer name. Required. Used to locate peer inside the library.
            "mac": "24:0a:c4:09:06:4d", //MAC Address. Required. Format as outlined before, with colons.
            "channel": 6, //Wireless channel peer is listening to. Optional. If missing the channel will be set the same in wifi.ap.channel
            "softap": true //Whether the peer is using the AP interface to receive messages. Optional. Will default to true
        }
    ]

