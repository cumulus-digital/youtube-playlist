# Youtube Playlist Embed

Creates a Youtube Playlist embed with sidebar of playlist videos.  Based on [YoutubeTV](https://github.com/jakiestfu/Youtube-TV), built with [Monkberry](https://monkberry.js.org)

## Usage:

Add a container element to your page

```html
<div id="container"></div>
```

Then initialize the container with its selector

```javascript
var myEmbed = new YPL('#container', {
	API_KEY: 'YOUR_YOUTUBE_API_KEY',
	playlist: 'PLAYLIST_ID',
	autoplay: true
});
```

A global YouTube API key can be set by assigning it to `window.YPL_API_KEY` and omitting it from the embed instantiation.

## Options

```javascript
{
	playlist: null,
	controls: true,
	annotations: false,
	autoplay: false,
	chainVideos: true,
	wmode: 'opaque',
	events: {
		onStateChange: noop,
	},
	refreshList: false
}
```

* `playlist` The ID of your playlist
* `controls` (boolean) Show player controls
* `annotations` (boolean) Show annotations
* `autoplay` (boolean) Automatically start playing the first video
* `chainVideos` (boolean) Automatically play the next video
* `wmode` The window mode of the YT embed
* `events.onStateChange` called from the YT API
* `refreshList` (Number or false) Time in seconds between refreshing the playlist from the YT API

## Public methods

### `fetchList()`
Fetches the list of playlist videos and their info from YouTube, updates the embed.

### `playVideo("ID")`
Plays a video by its YT ID.

### `playNext()`
Plays the next video after the currently active item.
