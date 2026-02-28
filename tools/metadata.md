## Metadata — best practices for music libraries

This document explains common metadata tags, format differences, and practical tips to keep a clean, searchable music library compatible with Navidrome and other servers/players.

**Why metadata matters:** correct and consistent metadata enables accurate browsing, searching, playlists, scrobbling, and features (compilations, multi-disc albums, lyrics, cover art).

- **Title:** track title. (ID3: `TIT2`, Vorbis: `TITLE`)
- **Artist:** track performing artist. For multi-artist tracks use a consistent separator (ID3: `TPE1`, Vorbis: `ARTIST`).
- **Album:** release/album name. (ID3: `TALB`, Vorbis: `ALBUM`)
- **Album Artist:** use for compilations to group properly (ID3: `TPE2`, Vorbis: `ALBUMARTIST`).
- **TrackNumber / DiscNumber:** numeric order and disc index (`TRCK`, `DISCNUMBER`).
- **Date / Year:** release date or year (`TDRC` / `DATE` / `YEAR`).
- **Genre:** standardize genres to avoid duplicates (e.g., use `Electronic` not `Electronic;Ambient`).
- **Composer / Conductor / Publisher:** useful for classical or soundtrack libraries.
- **MusicBrainz IDs:** `musicbrainz_trackid`, `musicbrainz_albumid`, `musicbrainz_artistid` help with persistent identification.
- **ReplayGain:** `replaygain_track_gain` / `replaygain_album_gain` for normalized playback where supported.
- **Cover art:** embedded images (ID3 APIC) or sidecar `cover.jpg` per album folder—Navidrome supports both.
- **Lyrics:** unsynchronised lyrics should use the USLT/LYRICS tag; synchronized lyrics are commonly provided as `.lrc` files.

Format specifics

- ID3 (MP3/AAC/M4A): frames like `TIT2`, `TPE1`, `TALB`, `USLT` (lyrics), `APIC` (art).
- Vorbis/FLAC/OGG: simple key/value tags like `TITLE`, `ARTIST`, `ALBUM`, `LYRICS`.
- MP4/M4A: tags are different (e.g., `©nam` for title) — GUI tools handle translation for you.

Practical tips

- Keep `Album Artist` populated for compilations so the album groups correctly in players and Navidrome.
- Use zero-padded track numbers for correct sorting (`01`, `02`, ...).
- Prefer full `YYYY-MM-DD` dates when available for better sorting/filtering.
- Avoid embedding multiple genres in a single string; use a primary genre and optionally `TCON` lists where supported.
- Use MusicBrainz IDs if you rely on external agents (Picard, beets) — they reduce ambiguity.

Common tools & example commands

- `beets` — automatic tagging, MusicBrainz integration:

  beets import /path/to/music

- `MusicBrainz Picard` — GUI/album-based tagger; drag-and-drop albums, save tags.
- `Mp3tag` (Windows) — batch rename and tag operations via actions and masks.
- CLI examples:
  - Add unsynchronised lyrics with `eyeD3` (MP3):

    eyeD3 --add-lyrics="lyrics.txt" "01 - My Song.mp3"

  - Write a Vorbis tag with `vorbiscomment` (FLAC/OGG):

    vorbiscomment -w example.flac -t "TITLE=My Song" -t "ARTIST=Artist Name"

  - Set tags on MP4/M4A with `mp4tags` or `AtomicParsley` as appropriate.

Batch and library hygiene

- Run an automated tool like `beets` to normalize tags and filenames using a consistent import policy.
- Use `dupeGuru` or similar to detect duplicates; prefer audio fingerprinting (AcoustID) when available.
- Keep a consistent folder structure, e.g. `Artist/Album/DiscNumber - TrackNumber - Title.ext`.

Navidrome-specific notes

- Navidrome reads tags from files and respects common embedded artwork and lyrics tags. Configure `ND_LYRICSPRIORITY` to control lyric source order.
- For best results with Navidrome features (compilations, multi-disc), ensure `albumartist`, `discnumber`, and `tracknumber` are correct.

References & further reading

- MusicBrainz tagging: https://musicbrainz.org/doc/Style
- ID3v2 frames: https://id3.org/ID3v2
- Vorbis comment specification: https://xiph.org/vorbis/doc/v-comment.html

If you want, I can:

- add a short `beets` config example to enforce filenames/tags;
- provide bulk `eyeD3` / `vorbiscomment` scripts to set common tags across many files.
