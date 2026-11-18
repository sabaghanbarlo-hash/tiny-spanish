# Audit of existing projects (18 Nov 2026)

Read-only inspection of the account's repos. Nothing was changed in them.

## What exists
| Repo | What it is | Key files |
|---|---|---|
| tiny-french-story | Newest Reel generator: pasted script, any two characters, queue + scheduler, 9:16, "small" short format, practice and mistake reels, covers, director prompts, 17+ tests | small.py, sprites.py, lesson.py, queue_tool.py, practice_reel.py, publish.py, validate_script.py, DIRECTOR_PROMPT.md |
| tiny-japanese-video | Older Reel generator (Mika and Alex, 31 characters, 33 backgrounds) plus IG Stories | tinyvideo.py (100 KB), practice_reel.py, refill_queue.py |
| tiny-french-video | IG Stories (sequences, scheduler, publish) | publish_story.py, schedule_stories.py |
| tiny-french-youtube | Newest YouTube system: Short / Long / Story, schedule.json + daily publish workflow, thumbnails, crosspost, upload, a language module | lesson.py, short.py, tinyvideo.py, lang_fr.py, characters.py, french_places.py, scheduler.py, upload.py, schedule.json, PLAN.md |
| tiny-japanese-youtube | Original YouTube system (same lineage, older) | lesson.py, short.py, schedule.json |
| tiny-japanese-story | Story-style acting engine, later merged into the YouTube repos | acting.py, atmos.py, scenery.py |

## Recommendation
- Reels base: **tiny-french-story**. It is the newest, has the character picker, queue, covers, tests and the director prompt, and its script format already carries `Speaker: text | English | pronunciation`, `vocab`, `grammar`, `quiz`.
- YouTube base: **tiny-french-youtube**. It has all three kinds (Short, Long, Story), the weekly schedule automation and `lang_fr.py`, which is the one place that decides which words are the target language (a clean seam for `lang_es.py`).
- Not used as base: tiny-japanese-video (older, Japanese-specific romaji code), tiny-japanese-story (already merged upstream).

## What is reused as is
GitHub Actions workflows, Edge TTS voices, Pillow + ffmpeg rendering, script parser, scene/acting engine, thumbnails and covers, schedule/queue tools, SRT export, director-prompt approach, test style.

## What must be rebuilt for Spanish
1. Characters: all rigs are code-drawn for the French or Japanese casts, so four new rigs (see CHARACTER_BIBLE.md).
2. `lang_es.py` (word lists, ¿¡ handling, accents) replacing `lang_fr.py`; Spanish voices and Spanish pronunciation lines.
3. Places: `french_places.py` is Paris-specific (Haussmann buildings, Métro). Spanish-speaking settings are needed (café, mercado, plaza, taxi, hotel, aeropuerto).
4. Curriculum, caption/hashtag templates and the "mistake" and "practice" banks in Spanish.

## What does not exist (so is not added)
There is no AI image or AI video generation in these projects; everything is drawn in code. Tiny Spanish keeps that, so "reference images" are rendered from the rigs, not generated.

## Instagram posting
Posting runs through Composio with a repo secret. Tiny Spanish stays render-only until you create the @tinyspanish account and approve posting.
