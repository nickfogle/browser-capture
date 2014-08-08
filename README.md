# Warning!

**JSCapture won't work in Chrome 37+** due to removal of the experimental desktop sharing API.

# JSCapture

**The flag #enable-usermedia-screen-capture [won't be available](https://codereview.chromium.org/270353002) at Chrome 35 Stable and later versions**

JSCapture is screen capturing library implemented with pure JavaScript and HTML5.

It allows you to make screenshots and record a video of your desktop from your browser.

## How to use

JSCapture uses `getUserMedia` for screen capturing. Currently the API for screen capturing is supported only by Google Chrome, Canary and Chromium by enabling an experimental flag.

In order to enable the flag:

* Go to chrome://flags/#enable-usermedia-screen-capture
* Enable - "Enable screen capture support in getUserMedia()"
* Restart your browser.

When you're done and you open chrome://flags/#enable-usermedia-screen-capture, you should see something like:

![Chrome flags](http://bulgariajs.org/files/getusermedia-flag.png)

Note that you MUST use `https` in order to be allowed to do screen recording. Since there are some **very expensive** operations happening when each frame is being captured the video won't be useful when you're capturing a high resolution. In order to handle this issue use the `scale` property.

## API

* `JSCapture.capture(config)` - Captures a new screenshot.
  * `config.x` - (Number) default value `0`. Specifies the left offset.
  * `config.y` - (Number) default value `0`. Specifies the top offset.
  * `config.width` - (Number) default value the screen width. Specifies the width of the screenshot.
  * `config.height` - (Number) default value the screen height. Specifies the height of the screenshot.
  * `config.process` - (Function|Array) default value an empty array. A list of filters, which are going to process the image.
  * `config.done` - (Function) default value is `undefined`. Callback, which is being called with the captured image.
  * `config.fail` - (Function) default value is `undefined`. A callback, which is being executed on unsuccessful screen capturing (for example if the user does not allow screen capturing).
  * `config.delay` - (Number) default value `0`. Specifies the delay after each the screenshot will be captured.
* `JSCapture.record(config)` - Capture a video.
  * `config.x` - (Number) default value `0`. Specifies the left offset.
  * `config.y` - (Number) default value `0`. Specifies the top offset.
  * `config.width` - (Number) default value the screen width. Specifies the width of the video.
  * `config.height` - (Number) default value the screen height. Specifies the height of the video.
  * `config.process` - (Function|Array) default value an empty array. A list of filters, which are going to process the individual frames.
  * `config.done` - (Function) default value is `undefined`. Callback, which is being called with the captured video.
  * `config.delay` - (Number) default value `0`. Specifies the delay after each the video will be captured.
  * `config.frameRate` - (Number) default value `60` frames per second. Specifies the number of frames per second.
  * `config.done` - (Function) default value is `undefined`. A callback, which accepts the video (as a Blob), result of the screen recording, as an argument
  * `config.fail` - (Function) default value is `undefined`. A callback, which is being executed on unsuccessful screen recording (for example if the user does not allow screen capturing).
  * `config.duration` - (Number) default is `Infinity`. A number which indicates the length of the video.
* `JSCapture.stopRecording(fn)` - Stops the video recording.
  * `fn` - (Function) default value is `undefined`. A callback, which accepts the video (as a Blob), result of the screen recording, as an argument. Note that the callback provided in `config.done` won't be invoked if `JSCapture.stopRecording(fn)` is called.
* `JSCapture.isRecording()` - (Boolean) Returns whether the screen recording have been started.

## Demo

[Here](https://mgechev.github.io/jscapture/)

## Contributors

[![mgechev](http://www.gravatar.com/avatar/82bafb0432ce4ccc9dcc26f94d5fe5bc?s=117)](https://github.com/mgechev) |[![jbrooksuk](http://www.gravatar.com/avatar/13616b6551a3854378f9e6fea964e519?s=117)](https://github.com/jbrooksuk) |[![themgt](http://www.gravatar.com/avatar/8ad9f63b9bd8e84da55eb083d25344db?s=117)](https://github.com/themgt) |[![hemanth](http://www.gravatar.com/avatar/d32a6bf2b43bf62a7212f0c793d76319?s=117)](https://github.com/hemanth) |
:---: |:---: |:---: |:---: |
[mgechev](https://github.com/mgechev) |[jbrooksuk](https://github.com/jbrooksuk) |[themgt](https://github.com/themgt) |[hemanth](https://github.com/hemanth) |


## License

This software is distributed under the terms of the MIT license.
