ESPNOW library for Moongoose OS

Peers JSON format


    [
        {
            "name": "",
            "mac": "xx:xx:xx:xx:xx:xx",
            "channel": 6,
            "softap": true
        }
    ]


    config_schema:

      - ["wifi.sta.enable", true]
      - ["wifi.sta.ssid", "xxxxxx"]
      - ["wifi.sta.pass", "xxxxxx"]
      - ["wifi.sta_ps_mode", 0]

      - ["wifi.ap.ssid", "xxxxxx"]
      - ["wifi.ap.pass", "xxxxxx"]
      - ["wifi.ap.channel", 1]
      - ["wifi.ap.keep_enabled", true]
      - ["wifi.ap.hidden", true] 

      - ["espnow.enable", true]
      - ["espnow.peers_filename", "espnow_peers.json"]
      - ["espnow.enable_broadcast", true]
      - ["espnow.debug_level", 1]

conds:
  - when: config_schema.espnow.enable_broadcast == "true"
    apply:
      config_schema:
        - ["espnow.enable_encrypt_test", false]
  - when: config_schema.espnow.enable_broadcast == "false"
    apply:
      config_schema:
        - ["espnow.enable_encrypt_test", true]

cdefs:
MGOS_WIFI_ENABLE_AP_STA: 1



#Power save mode for station: 0 - none, 1 - min, 2 - max
