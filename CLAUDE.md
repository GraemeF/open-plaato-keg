# open-plaato-keg

A local replacement for the Plaato cloud, for Plaato Keg scales. It decodes the Blynk protocol the keg speaks, so a keg can report to a server its owner runs instead of the vendor's cloud.

## What open-plaato-keg owns

- Accepting keg connections and decoding the Blynk protocol.
- Keeping the latest keg readings, and the beer details a user enters, in a local database file.
- Publishing readings over WebSocket, MQTT and the REST API.
- Sending commands to a connected keg: tare, calibration, units, scale sensitivity and the like.
- The web pages that show kegs and configure them.
- The Docker image and its release pipeline.

## What it does not own

- A user's deployment: where it runs, how it is exposed, and its network and reverse proxy.
- A user's configuration: environment variables, MQTT broker details, keg auth tokens and keg WiFi setup.
- A user's data: the database file and everything published to their broker. Whoever runs an instance owns and backs up its data.
- The MQTT broker, and whatever consumes the published readings, such as dashboards or home automation.
- The keg firmware and hardware. The server only speaks to them.
- Plaato's cloud, which this project exists to replace.

This is a fork of `sklopivo/open-plaato-keg`.
