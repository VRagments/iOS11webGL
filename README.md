# Problem Playing Hls Video on WegGL with iOS 11

Initial Thread:
[ThreeJS iOS webGL HLS not working](https://github.com/mrdoob/three.js/issues/9754)

# To get it working in iOS 10

To get HLS video streaming to WebGL working in iOS 10 these 3 steps where necessary:

* Use custom shader to correct color mapping (in this example see 'video-shader')
* flipY texture coordinate to correct video rotation (ignored in this example - video will be flipped)
* use `crossOrigin="anonymous"` to get videos working (not an issue here since video is on same origin)

# Problem in iOS 11

With the before mentioned method the whole canvas is white.
The video is played as the audio of the video can be heard.
But the texture is no longer drawn.
If we remove the `video-shader` component the whole texture area will be black instead of white with the other symptoms being the same.


# Run example

Start a webserver inside the root folder.

`python -m SimpleHTTPServer`

Navigation to this address and test video playback.

It works on

* MacOS Safari
* Android Chrome

It should also be working on:

* iOS Safari
* iOS Chrome
* iOS Firefox
