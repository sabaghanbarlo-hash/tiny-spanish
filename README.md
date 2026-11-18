# Tiny Spanish 🇲🇽

*Spanish, one tiny story at a time.* Free beginner Spanish for English speakers, taught by four recurring animated characters.

Sibling of Tiny Japanese and Tiny French. Same free toolchain (GitHub Actions, Microsoft Edge neural voices, Pillow, ffmpeg). No paid APIs. The Tiny Japanese and Tiny French repos are not touched by this project.

## Status
| Stage | State |
|---|---|
| 1. Audit of existing repos | Done: see `docs/AUDIT.md` |
| 2. Brand, cast, language rules, curriculum, templates | Done (this commit) |
| 3. Instagram Reel engine (clone of tiny-french-story) | Next |
| 4. YouTube engine: Short / Long / Story (clone of tiny-french-youtube) | Next |
| 5. New Spanish character rigs and Spanish places | Next |
| 6. Episode tracking, regeneration, export | Partly: `state/*.json` and `tools/validate_script.py` exist |
| 7. End-to-end test | Sample Reel script `episodes/instagram/001-introducing-yourself.txt` passes the validator; render test pending |

## Layout
- `config/brand.json`, `config/characters.json`: brand rules, voices, cast
- `docs/CHARACTER_BIBLE.md`, `docs/SPANISH_RULES.md`, `docs/AUDIT.md`
- `curriculum/a1-instagram.json`: the first 20 Reel episodes (A1)
- `templates/`: copyable script templates (Reel, YouTube lesson, Short)
- `episodes/instagram/`, `episodes/youtube/`: finished scripts
- `state/instagram.json`, `state/youtube.json`: separate numbering and publishing history
- `tools/validate_script.py`: checks Spanish punctuation, LatAm rules, cast names

## Check a script
`python tools/validate_script.py episodes/instagram/001-introducing-yourself.txt`
