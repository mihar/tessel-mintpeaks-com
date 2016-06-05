# Mintpeaks.com

[mintpeaks.com](http://mintpeaks.com) is my personal home control and information site, powered by Node and tessel.io

![](http://mintpeaks.com/assets/mintpeakscom.png)

## Moving parts

- **Tessel app** [mintpeaks-tessel](https://github.com/mihar/mintpeaks-tessel) - Node.js app for Tessel
- **Node app** [mintpeaks](https://github.com/mihar/mintpeaks) - Node.js app for streaming Tessel data (TCP socket, Express, Socket.io)
- **Alexa Skill** [mintpeaks-alexa-skill](https://github.com/mihar/mintpeaks-alexa-skill) - Alexa skill to get climate data by just asking

This simple app displays the real-time temperature and humidity from my apartment.

To do this, I wrote a [node.js app](https://github.com/mihar/mintpeaks-tessel) for my Tessel microcontroller that gathers the climate data.

Tessel connects to a second [node.js server](https://github.com/mihar/mintpeaks) over a TCP socket and posts the data as JSON.

That process in turn also runs an express/socket.io server, which this dumb static site connects to via websockets and streams the real-time data.

## Requirements

For this to work, you need a [Tessel 2]() which is a small hardware prototyping system, basically a micro-controller that runs Node.js out of the box.

You'll also need to buy the [climate sensor](https://tessel.io/modules#module-climate) for Tessel 2 which connects to the Tessel via the 10-pin connector.

Because the Tessel gets warm when running it can skew the measurements. I solved that by purchasing a simple 10-pin extension cable from Adafruit.

Here's how it looks:

![](http://mintpeaks.com/assets/tessel-cables.jpg)

### Troubleshooting

I was not able to get this running on Tessel 1, since their WiFi module couldn't handle sending data for more than a couple of hours before freezing completely.

Tessel 2 seems to work great so far.
