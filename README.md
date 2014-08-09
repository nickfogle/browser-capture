## How to use

This uses `getUserMedia` for screen capturing. Currently the API for screen capturing is supported only by Google Chrome, Canary and Chromium by enabling an experimental flag.

# Currently it's only supported by Chrome. To do it: 

* Go to chrome://flags/#enable-usermedia-screen-capture
* Enable - "Enable screen capture support in getUserMedia()"
* Restart your browser.

# JSCapture

**The flag #enable-usermedia-screen-capture [won't be available](https://codereview.chromium.org/270353002) at Chrome 35 Stable and later versions**

JSCapture is screen capturing library implemented with pure JavaScript and HTML5.

It allows you to make screenshots and record a video of your desktop from your browser.

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

## License

This software is distributed under the terms of the MIT license.
