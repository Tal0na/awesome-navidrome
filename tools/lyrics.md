## Adding lyrics to Navidrome

This guide explains how Navidrome searches for and displays lyrics, and provides practical ways to add lyrics to your tracks.

**Summary:** Navidrome can use embedded lyrics in file tags (unsynchronized/USLT), or external files with the same base name as the track (e.g., `song.mp3` + `song.lrc`). The search priority is controlled by the `ND_LYRICSPRIORITY` option (default: `.lrc,.txt,embedded`).

1. External synchronized lyrics (.lrc)

- Create an LRC file with the same base name as the audio file and place it in the same folder. Example: if the audio file is `01 - My Song.mp3`, name the lyrics file `01 - My Song.lrc`.
- Simple LRC format (timestamps in mm:ss.xx or [mm:ss.xx]):

  [00:12.00] First line of lyrics
  [00:34.50] Second line of lyrics

- Navidrome will display synchronized lyrics if the `.lrc` extension is included in `ND_LYRICSPRIORITY`.

2. Embedded (unsynchronized) lyrics

- For unsynchronized lyrics, place the lyrics text in the appropriate tag of the file (ID3 USLT for MP3, `LYRICS`/`UNSYNCEDLYRICS` field for Vorbis/FLAC).
- Useful tools:
  - `Mp3tag` (Windows): select files → `Extended Tags` → add/edit the lyrics field.
  - `Kid3` (GUI/CLI): `Unsynchronised lyrics` field.
  - CLI taggers: `eyeD3`, `mid3v2`, `vorbiscomment` for scripting and bulk edits.

3. Configure lyrics priority in Navidrome

- The `ND_LYRICSPRIORITY` option controls which sources are searched and in what order. Example valid values: `.lrc,.txt,embedded` (default) or `embedded,.lrc` to prefer embedded tags.
- Configuration examples:
  - Docker / docker-compose (in the `navidrome` service):

  ```yaml
  environment:
    - ND_LYRICSPRIORITY=.lrc,.txt,embedded
  ```

  - Environment variable in Windows PowerShell (temporary for the session):

  ```powershell
  $env:ND_LYRICSPRIORITY = ".lrc,.txt,embedded"
  Restart-Service navidrome
  ```

4. Force a library re-scan

- After adding or editing lyrics, run a new scan so Navidrome reads the updated files: restart the service/container or use the scan option in Navidrome's admin panel (or force a re-scan by touching/modifying file dates).

5. Minimal LRC example

   [00:00.00] Intro
   [00:15.20] Verse 1 line 1
   [00:22.50] Verse 1 line 2

6. Tips and troubleshooting

- Exact name: the external lyrics file must have exactly the same base name as the audio (spaces, punctuation and capitalization matter on case-sensitive filesystems).
- Check `ND_LYRICSPRIORITY` if Navidrome doesn't find lyrics.
- Logs: temporarily increase `ND_LOGLEVEL=debug` to see scanner messages related to lyrics.
- If embedded lyrics don't show up, confirm the tagger wrote the correct frame (USLT for MP3, `LYRICS` field for FLAC/OGG).

Useful links:

- Navidrome config options (lyrics priority): https://www.navidrome.org/docs/usage/configuration/options/

If you want, I can:

- add example `eyeD3` / `vorbiscomment` commands for bulk-adding lyrics;
- show a full example `docker-compose.yml` with `ND_LYRICSPRIORITY` configured.

