# Channel Loop Player

Paste a YouTube channel link; every video plays one after another and the list loops forever.
Single self-contained `index.html` (no build step, no framework), using the YouTube IFrame Player API.

## Use

- `/channel/UC…` links work with no API key.
- `@handle`, `/c/name`, `/user/name` links need a YouTube Data API v3 key, entered in the page's "API key" field.
  The key (and last link) is saved only in your browser's localStorage. It is never part of this repo.
- With a key, video titles are shown in the queue.
- "Play all at once" shows up to 24 muted players at a time, with Prev/Next 24 paging.
- The YouTube player loads only a channel's most recent ~200 videos.

## Run locally

```bash
python -m http.server 8080
```

Open http://localhost:8080. Opening the file directly (`file://`) makes YouTube return error 153.

## Restrict your API key

In Google Cloud Console → Credentials, restrict the key to HTTP referrers (this site's github.io URL and `http://localhost:8080/*`) and to the YouTube Data API v3.
