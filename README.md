## Now fully support VideoJS 4.3.0!

# Video.js - YouTube Source Support
Allows you to use YouTube URL as source with [Video.js](https://github.com/zencoder/video-js/).

## How does it work?
Including the script vjs.youtube.js will add the YouTube as a tech. You just have to add it to your techOrder option. Then, you add the option src with your YouTube URL.

It supports:
- youtube.com as well as youtu.be
- Regular URLs: http://www.youtube.com/watch?v=xjS6SftYQaQ
- Embeded URLs: http://www.youtube.com/embed/xjS6SftYQaQ
- Playlist URLs: http://www.youtube.com/playlist?list=PLA60DCEB33156E51F OR http://www.youtube.com/watch?v=xjS6SftYQaQ&list=SPA60DCEB33156E51F

Here is 3 examples:
1. using autoplay/loop
2. using YouTube controls
3. using JavaScript events

	<!DOCTYPE html>
	<html>
	<head>
	  <link href="video-js.min.css" rel="stylesheet" />
	</head>
	<body>
  	<video id="vid1" src="" class="video-js vjs-default-skin" controls preload="auto" autoplay="autoplay" loop="loop" width="640" height="360" data-setup='{ "techOrder": ["youtube"], "src": "http://www.youtube.com/watch?v=xjS6SftYQaQ" }'></video>
  	<br />
  	<video id="vid2" src="" class="video-js vjs-default-skin" controls preload="auto" width="640" height="360" data-setup='{ "techOrder": ["youtube"], "src": "http://www.youtube.com/watch?v=xjS6SftYQaQ", "ytcontrols": true }'></video>
  	<br />
  	<video id="vid3" src="" class="video-js vjs-default-skin" controls preload="auto" width="640" height="360"></video>
	  
	  <script src="video.min.js"></script>
	  <script src="vjs.youtube.js"></script>
	  <script>
	  videojs('vid3', { "techOrder": ["youtube"], "src": "http://www.youtube.com/watch?v=xjS6SftYQaQ" }).ready(function() {
	    // Detect when the YouTube API is ready
	    this.on('apiready', function() {
	      console.log('YouTube API is ready!');
	    });
	
	    // Cue a video using ended event
	    this.one('ended', function() {
	      this.src('http://www.youtube.com/watch?v=6h-sZkglI8Y');
	    });
	  });
	  </script>
	</body>
	</html>

## Additional Options
ytcontrols: Display the YouTube controls instead of Video.js.

##Special Thank You
Thanks to John Hurliman for the original code on the old Video.js
