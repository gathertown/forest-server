# forest-server

The code behind [The Forest](https://gather.town/app/e5kK4mRdSOALriFT/TheForest), a dynamic, living Gather map.

(better documentation and easier setup coming this week!)

## FYI

needs `config.js` in the root dir filled with the following:

```js
module.exports = {
	PROD_ROOM_ID: "YourSpaceId12345\\Space Name", // note the \, NOT / as is in the URL
	DEV_ROOM_ID: "same thing^ but for if you're running gather locally",
	API_KEY: "your-Gather-API-key",
};
```

change `const IS_PROD = true` to `false` in the first line of `index.js` to run locally. you'll also need gather running locally

start it with `node index.js` (long running process)

will need to change that space's starting map to `forest-v1` -- or change the `MAP_ID` in `index.js` to suit your space

## how it works

Run this code on your own server, and change the urls from forest-001.gather.town to your domain.
When someone chops a tree, it hits that endpoint, and then this server writes the new map data to our API.
From there, our game server notices the changes and propogates them to the client (player).
