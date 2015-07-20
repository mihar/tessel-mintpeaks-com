# Mintpeaks.com

[mintpeaks.com](http://mintpeaks.com) is my personal home control and information site, powered by Node and tessel.io

## Moving parts

- **Tessel app** [mintpeaks-tessel](/mihar/mintpeaks-tessel) - Node.js app for Tessel
- **Node app** [mintpeaks](/mihar/mintpeaks) - Node.js app for streaming Tessel data (TCP socket, Express, Socket.io)

This simple app displays the real-time temperature and humidity from my apartment.

To do this, I wrote a [node.js app](/mihar/mintpeaks-tessel) for my Tessel microcontroller that gathers the climate data.

Tessel connects to a second [node.js server](/mihar/mintpeaks) over a TCP socket and posts the data as JSON.

That process in turn also runs an express/socket.io server, which this dumb static site connects to via websockets and streams the real-time data.
