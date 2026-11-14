# Jellyfin plugins

A Jellyfin plugin repository. Only the plugin catalogue (`manifest.json`) and release builds live here.

## Install

1. In Jellyfin, open **Dashboard → Plugins → Repositories** and add:
   ```text
   https://raw.githubusercontent.com/Grassth/jellyfin-plugins/main/manifest.json
   ```
2. Open **Catalog**, install the plugin, and restart Jellyfin.

## Plugins

| Plugin | Jellyfin | Notes |
| --- | --- | --- |
| **Trailers4Jellyfin** | 12.x | Downloads trailers for upcoming and recently released movies from TMDB/YouTube and plays them before your movies. Fork of [Awatatah/Trailers4Jellyfin](https://github.com/Awatatah/Trailers4Jellyfin), itself a fork of [robadieNZ/Trailers4Jellyfin](https://github.com/robadieNZ/Trailers4Jellyfin). Adds: no AV1 downloads (H.264 + AAC so trailers direct-play on players without AV1 decode, e.g. Nvidia Shield TV 2019), dubbed trailers skipped in favour of original-audio / subtitled ones, and hardened yt-dlp invocation. Both behaviours can be turned off under *Download Settings*. |

Trailers4Jellyfin keeps the original plugin ID, so it upgrades an existing install in place and keeps its settings.
Remove other Trailers4Jellyfin repositories from Jellyfin so they don't offer their builds over this one.

After installing, consider turning off *Only English-original movies when English is selected*
(otherwise foreign-language films get no trailer at all) and setting *Video quality* to 1080p
(needs [yt-dlp](https://github.com/yt-dlp/yt-dlp) and ffmpeg on the Jellyfin server).

## Releases

Release ZIPs are attached to tags named `<plugin>-v<version>`, e.g. `trailers4jellyfin-v2.2.0.1`.
They are published automatically by the plugin's build pipeline; please don't edit `manifest.json` by hand.
