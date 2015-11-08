# The GH4 Project
I love the Panasonic GH4, but Panasonic refuses to produce documentation for an open API like Sony have for most of it’s cameras and Olympus have for the Olympus Air.

My main aim for this project is to produce an iOS SDK that can be installed via pods to stream live video from a GH4, capture photos and download them to an app.

Out of the cameras I’ve had a play with, the GH4’s app kind of sucks, so the idea is to produce a better version of what Panasonic have produced.

# Discovered Endpoints
```http://192.168.54.1:80/cam.cgi?mode=accctrl&type=req_acc&value=4D454930-0100-1000-8001-02070002D200&value2=iPhone```
Puts the camera in control mode

```http://192.168.54.1/cam.cgi?mode=getstate```
Gets the current state of the camera, seems to need to be called every 5/6 seconds otherwise the camera will turn off/WiFi times out.

```http://192.168.54.1/cam.cgi?mode=startstream&value=58284```
Starts the media stream. The value is the port you’d like to use. The stream is UDP. I can’t seem to get this working in VLC.

# Accessing Media
The GH4 uses DLNA to serve media over the network, all you need is a DLNA client to discover the server and access content. PlatinumUPNP is our preferred.
