# DubTitlerr subtitles

English "dubtitles" — a transcript of the English dub audio, timed to picture — for
anime episodes. The set started with [One Pace](https://onepace.net/) and now covers
[14 shows](#whats-here). Produced by
[DubTitlerr](https://github.com/XenaRathon/DubTitlerr): Whisper transcription, glossary
correction, and an LLM repair pass over low-confidence lines.

## Status: work in progress, unreviewed

**Every file in this repository is machine output that has not completed human
review.** Nothing here should be read as "checked" or "finished" — it is exactly what
the pipeline produced, published as-is so it is useful to someone sooner than a fully
reviewed release would be. Every episode in every manifest is marked
`"status": "unreviewed"`, for every show, not just the first one published.

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

As of 2026-10-07: **970 episodes across 14 shows**, all unreviewed. New episodes and
shows are added automatically as DubTitlerr finishes them, so this table is a snapshot;
`manifest/` is the authoritative list.

| Show | Episodes |
| --- | ---: |
| One Pace | 497 |
| JoJo's Bizarre Adventure (2012) | 195 |
| Sword Art Online (2012) | 98 |
| Reborn as a Vending Machine, I Now Wander the Dungeon (2023) | 36 |
| Trigun (1998) | 27 |
| JUJUTSU KAISEN (2020) | 24 |
| Chained Soldier (2024) | 14 |
| JoJo's Bizarre Adventure (1993) | 13 |
| I Parry Everything (2024) | 12 |
| I'm in Love With the Villainess (2023) | 12 |
| MARRIAGETOXIN (2026) | 12 |
| Akiba Maid War (2022) | 11 |
| Life With an Ordinary Guy Who Reincarnated Into a Total Fantasy Knockout (2022) | 11 |
| Chainsmoker Cat (2026) | 8 |

Show folders carry the show's TheTVDB id (for example `Trigun (1998) {tvdb-77680}`)
except One Pace, which has none.

`manifest/<Show>.json` lists every episode covered so far for that show, one entry per
episode:

```json
{
  "show": "Trigun (1998) {tvdb-77680}",
  "season": "Season 00",
  "episode_title": "Trigun (1998) - S00E01 - Trigun the Movie Badlands Rumble",
  "duration_seconds": 5433.261,
  "status": "unreviewed",
  "sha256": "9817ba368f29398b028da8c27fb1b2d6054bfc8a43fcf2671a482737bd73050e",
  "source": "675092153:1788874348.8362608"
}
```

`duration_seconds` is there as a matching aid — compare it against your own copy of
the episode to confirm you have the right release before applying its subtitles.
`sha256` is a hash of exactly what is published for the episode, and `source` is a
fingerprint of the video file it was made from; the publisher uses them to tell when an
episode needs republishing, and you can ignore them.

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
content is the same either way.

Episode filenames follow the same `Show - SxxExx - Title` convention as the manifest, so
they line up directly with a matching video file (or an existing fansub `.ass`/`.srt`)
that follows it.

## What this is not

This is not a translation — the underlying dialogue is each episode's own English dub
audio, transcribed and lightly corrected. This repository does not include any video or
audio; the subtitle files are timed against the releases named in the manifests and are
meant to be played alongside them.
