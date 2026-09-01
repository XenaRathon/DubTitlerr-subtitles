# DubTitlerr subtitles — One Pace

English "dubtitles" (a transcript of the English dub audio, timed to picture) for
[One Pace](https://onepace.net/) episodes, produced by
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

## Layout

```
<Show>/<Season>/<Episode>.srt   — dialogue only, no signs/songs
<Show>/<Season>/<Episode>.ass   — dialogue merged with the fansub's signs/songs track
manifest.json                   — one entry per episode: show, season, title, duration
```

Durations are included as a matching aid against your own copy of each episode.

## What this is not

This is not a translation — the underlying dialogue is [One Pace](https://onepace.net/)'s
own official-language dub audio, transcribed and lightly corrected. This repository
does not include any video, audio, or signs/songs artwork; the `.ass` files reference
styling only, timed against One Pace's own releases.
