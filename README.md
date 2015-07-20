# mintpeaks-com
mintpeaks is my personal home control and information site, powered by Node and tessel.io

## Moving parts

This simple app displays the real-time temperature and humidity from my apartment.

To do this, I wrote a [node.js app](/mihar/mintpeaks-tessel) for my Tessel microcontroller.

Tessel connects to a second [node.js server](/mihar/mintpeaks) over a TCP socket and posts the data as JSON.

That process in turn also runs an express/socket.io server, which this dumb static site connects to via websockets and streams the real-time data.
