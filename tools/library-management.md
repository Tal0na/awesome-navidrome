# Music Library Management Tools

A concise list of tools (in English) for organizing, tagging, deduplicating and converting music libraries. Each entry contains a short description, key features, and when to use it.

- **beets** — Library manager and music organizer.
  - Key features: automatic metadata lookup from MusicBrainz, flexible import rules, plugin system, AcoustID fingerprinting, filesystem renaming.
  - Best for: power users who want automated, scriptable library management and consistent folder/file naming.
  - Link: https://beets.io/

- **MusicBrainz Picard** — Cross-platform tagger.
  - Key features: album-oriented tagging, AcoustID/Chromaprint audio fingerprinting, plugins, batch processing.
  - Best for: accurate album tagging and fingerprint-based identification.
  - Link: https://picard.musicbrainz.org/

- **Kid3** — Metadata editor (GUI/CLI).
  - Key features: edit tags for many formats (MP3, FLAC, OGG, M4A), batch changes, scripting support, export/import tag lists.
  - Best for: manual batch editing across multiple file formats.
  - Link: https://kid3.kde.org/

- **Mp3tag** — Windows tag editor.
  - Key features: intuitive UI, powerful renaming and exporting, online database lookups (Discogs, MusicBrainz), actions for mass edits.
  - Best for: Windows users needing a simple, fast GUI for batch tagging.
  - Link: https://www.mp3tag.de/

- **MusicBee** — Windows music player + library manager.
  - Key features: auto-tagging, library organization, advanced playback, plugin support, sync with devices.
  - Best for: users who want a full-featured Windows player with strong library tools.
  - Link: https://getmusicbee.com/

- **foobar2000** — Customizable audio player with tagging features.
  - Key features: lightweight, component ecosystem, advanced tagging and file operations, converter component.
  - Best for: advanced users who want a minimalist player with powerful extensions.
  - Link: https://www.foobar2000.org/

- **Clementine / Strawberry** — Cross-platform music players with library functions.
  - Key features: library view, metadata editing, remote streaming, smart playlists.
  - Best for: cross-platform desktop users who want simple library management inside a player.
  - Link: https://www.strawberrymusicplayer.org/

- **MediaMonkey** — Windows music organizer and player.
  - Key features: large-library support, auto-tagging, duplicate finding, CD ripping and conversion.
  - Best for: large collections on Windows with extensive management needs.
  - Link: https://www.mediamonkey.com/

- **AcoustID / Chromaprint** — Audio fingerprinting system.
  - Key features: identify tracks by audio fingerprint, integrate with MusicBrainz and Picard, match recordings without reliable metadata.
  - Best for: identifying unknown tracks or verifying duplicates by sound.
  - Link: https://acoustid.org/

- **ffmpeg** — Audio conversion and processing toolkit.
  - Key features: convert formats, resample, normalize, extract audio, batch processing via CLI.
  - Best for: format conversions, resampling, and scripting bulk audio tasks.
  - Link: https://ffmpeg.org/

- **dupeGuru** — Duplicate file finder (music-aware mode).
  - Key features: fuzzy matching, filename and content checks, music mode that compares tags and audio.
  - Best for: finding and removing duplicate songs across folders and libraries.
  - Link: https://dupeguru.voltaicideas.net/

- **puddletag** — Linux tag editor inspired by Mp3tag.
  - Key features: spreadsheet-style tagging, scripting, web lookups, flexible batch operations.
  - Best for: Linux users who want Mp3tag-like functionality.
  - Link: https://puddletag.sourceforge.io/

Tips for choosing tools:

- Use fingerprinting (AcoustID/Picard) when filenames and tags are unreliable.
- Use `beets` for automated imports and long-term library hygiene.
- Use GUI tag editors (Mp3tag/Kid3/puddletag) for quick manual fixes.
- Use `ffmpeg` for format conversion and batch audio processing in scripts.

If you want, I can expand any entry with example commands, plugin suggestions, or short workflows (import → tag → dedupe → organize).
