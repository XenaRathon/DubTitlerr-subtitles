# DubTitlerr subtitles — One Pace

English "dubtitles" — a transcript of the English dub audio, timed to picture — for
[One Pace](https://onepace.net/) episodes. Produced by
[DubTitlerr](https://github.com/XenaRathon/DubTitlerr): Whisper transcription, glossary
correction, and an LLM repair pass over low-confidence lines.

## Status: work in progress, unreviewed

**Every file in this repository is machine output that has not completed human
review.** Nothing here should be read as "checked" or "finished" — it is exactly what
the pipeline produced, published as-is so it is useful to someone sooner than a fully
reviewed release would be.

Concretely:

- an episode appears here once DubTitlerr has muxed a dubtitle track into it
  (`.dubtitles.done` is valid for the current file) — that is the only bar it clears;
- most lines were never flagged for review at all (repair only questions a line it is
  unsure about); the ones that were flagged may or may not have a human verdict yet;
- expect occasional wrong names, mistimed lines, or repair mistakes that a review pass
  would have caught. If you spot one, an issue or PR against the affected episode's
  files is welcome.

A future, separate release will carry a stricter guarantee — every line the pipeline
was unsure about has been read and judged by a human — once review catches up. This
repository will say so explicitly when that happens; until then, treat everything here
as a draft.

## What's here

Currently: **Season 31** (One Pace's cut of the Dressrosa arc), 48 episodes,
`S31E01`–`S31E48`.

`manifest/<Show>.json` lists every episode covered so far for that show, one entry per
episode:

```json
{
  "show": "One Pace",
  "season": "Season 31",
  "episode_title": "One Pace - S31E01 - Arriving at Dressrosa! ...",
  "duration_seconds": 1790.897,
  "status": "unreviewed"
}
```

`duration_seconds` is there as a matching aid — compare it against your own copy of
the episode to confirm you have the right release before applying its subtitles.

## Layout

```
subtitles/<Show>/<Season>/<Episode>.srt   — dialogue, SubRip format
subtitles/<Show>/<Season>/<Episode>.ass   — the same dialogue, Advanced SubStation Alpha
manifest/<Show>.json                      — one entry per episode: season, title, duration
```

Episodes are named `<Show> - SxxExx - <Episode Title>`. The release tags a media file
carries (resolution, source, codec, group) are stripped: they describe somebody's encode,
not the episode.

Pick whichever format your player or muxing tool expects — the `.ass` files carry
subtitle styling (font, size, colour) that `.srt` doesn't support, but the dialogue
content in this release is the same either way.

Episode filenames match One Pace's own naming, so they line up directly with a
matching video file (or an existing fansub `.ass`/`.srt`) that follows the same
convention.

## What this is not

This is not a translation — the underlying dialogue is [One Pace](https://onepace.net/)'s
own official-language dub audio, transcribed and lightly corrected. This repository
does not include any video or audio; the subtitle files are timed against One Pace's
own releases and are meant to be played alongside them.
