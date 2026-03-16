# Politics -- Claude Notes

## Overview
Single-file political compass test. All HTML/CSS/JS in `index.html`. No build tools, no dependencies.

## Architecture
- `P[]` -- question bank (6 pages, 62 total)
- `S[]` -- scoring matrix: each entry is `[axis, direction]` where axis is `'e'`(economic) or `'s'`(social), direction is `1` or `-1`
- `ans[]` -- user answers array (62 slots, null = unanswered)
- Scoring: each axis normalized independently by its question count (`et/(ec*2)*10`)

## Key Functions
- `render()` -- builds current page of questions
- `calc()` -- scores all answers, calls `drawCompass()`
- `drawCompass(econ, social)` -- SVG grid + animated dot
- `shareImage()` -- canvas-based PNG generation from SVG
- `save()` / restore -- localStorage persistence of `ans` and `pg`

## Dev
```bash
open ~/Documents/Code/politics/index.html
```

## Deploy
```bash
git push origin main
```

## Status
v1.0.0 -- complete.
