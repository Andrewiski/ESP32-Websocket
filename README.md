## Websocket Client for ESP-32

This is a simple library that implements a Websocket client for an ESP-32.  This is based off of https://github.com/morrissinger/ESP8266-Websocket with some modifications to support ESP-32 and WiFiClientSecure.

Primary differences from ESP8266-Websocket:

* Removed MD5 library as this is provided by ESP32 core
* Changed WebSocketClient to recognize a common alternate case variant of the "Sec-WebSocket-Accept" header ("Sec-Websocket-Accept").
* Buffers writes to socket (up to 128 bytes) to better support WiFiClientSecure.
* Removed WebSocketServer because there was no goal to implement that here.

### Notes / Limitations
* Supports only single frame text frames.
* Max frame size is 65535 characters.
* No support for continuation, binary, or ping/pong.

### Credits
Thanks to morrissinger for [ESP8266-Websocket](https://github.com/morrissinger/ESP8266-Websocket), which this library has been forked from to add ESP32 support.

Thanks to brandenhall, for [Arduino-Websocket](https://github.com/brandenhall/Arduino-Websocket) which morrissinger/ESP8266-Websocket was forked from to add ESP8266 support.

Thanks to ejeklint for [Arduino-WebsocketServer](https://github.com/ejeklint/ArduinoWebsocketServer) which brandenhall/Arduino-Websocket was forked from was forked from in order to add non-hixie-76 support.
