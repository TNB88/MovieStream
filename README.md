# MovieStream remote configuration

`tmdb_hosts.json` controls the preferred TMDb API domains used by the patched
Umbrella, Homelander, and POV Kodi add-ons.

Put the preferred domain first. Keep at least one known-good fallback domain.
The add-ons validate the file, refresh it every 15 minutes, cache the last valid
copy, and retain built-in fallback domains if GitHub is temporarily unavailable.

Current configuration example:

```json
{
  "version": 1,
  "tmdb_api_hosts": [
    "api.tmdb.org",
    "api.themoviedb.org"
  ]
}
```

Only bare DNS hostnames are accepted: do not include `https://`, paths, ports,
or query strings.
