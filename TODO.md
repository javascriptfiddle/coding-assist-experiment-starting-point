# TODO

## In Progress
- [x] Implement minimum endpoints for connect -> search -> stream

## Implementation Tasks
- [x] `routers/system.py`: Implement `ping` (connectivity check)
- [x] `routers/system.py`: Implement `getLicense` (return `valid: true`)
- [x] `routers/browsing.py`: Implement `getMusicFolders` (single dummy folder "YouTube Music")
- [x] `routers/searching.py`: Implement `search3` (proxy to `ytmusicapi.search`, map to `Child` objects)
- [x] `routers/media__retrieval.py`: Implement `stream` (proxy audio via `StreamingResponse` using `yt-dlp` + `httpx`)
- [x] `pyproject.toml`: Add `httpx` dependency for async audio proxying
- [x] `main.py`: Add middleware to strip `.view` suffix from request paths
- [x] `routers/user__management.py`: Implement `getUser`
- [x] `routers/user__management.py`: Implement `getUsers`
- [x] `routers/lists.py`: Implement `getAlbumList` / `getAlbumList2` (empty responses)
- [x] `routers/playlists.py`: Implement `getPlaylists` (empty response)
- [x] `routers/browsing.py`: Implement `getGenres` (empty response)
- [x] `main.py`: Add request/response logging to `server.log`
- [x] `routers/searching.py`: Enrich `Child` objects with `contentType`, `suffix`, `parent`, etc.
- [x] `routers/browsing.py`: Implement `getSong`
- [x] `routers/media__retrieval.py`: Implement `getCoverArt`

## Decisions Made
- Stream delivery: **Proxy (StreamingResponse)**
- YouTube Music auth: **Anonymous / Unauthenticated**

## Future Enhancements
- [ ] Add `ytmusicapi` authenticated mode for higher rate limits / personalized results
- [ ] Add `ytmusicapi` authenticated mode for higher rate limits / personalized results
- [ ] Consider caching `yt-dlp` extracted URLs to reduce extraction overhead
- [ ] Handle `yt-dlp` / `ytmusicapi` rate limiting and errors gracefully
- [ ] Add unit tests for the implemented endpoints
- [ ] Implement `getAlbum`, `getArtist`, `getMusicDirectory` for browsing
- [ ] Implement `scrobble` for play count tracking
- [ ] Support `maxBitRate` and `format` parameters on `stream`
- [ ] Support `timeOffset` parameter on `stream` (transcode offset)
- [ ] Add `estimateContentLength` support on `stream`
