# Map Tester's Checklist

## PR files
- File requirements: `map.mts`, `map.conf`, `screenshot.png`, and `barriers.data`
- `screenshot.png` satisfies [these criteria](Making-a-Map-for-Capture-the-Flag.md#13-screenshot) and has an aspect ratio of 3:2.
- `map.conf`:
  - `enabled = true`
  - Proper license (see [the license section in the link](Making-a-Map-for-Capture-the-Flag.md#11-exporting-the-map))
  - Suitable initial items
  - Applicable hint (test map and check)
  - If [map constants (click the link and read the section)](Making-a-Map-for-Capture-the-Flag.md#11-exporting-the-map) are modified, they are within reasonable bounds. (test map and check)


## Map
### Basics
- No errors
- Area under flag is indestructible with an area of at least 5x5 blocks.
- The bases have their own team chests.
- Map is inescapable - walls and floor should be made of indestructible nodes.
- Proper build-time barriers
- Functional treasure chests
- Flags can be captured without issues
- Map is free of other general "bugs"

### Mechanics:
- Both teams have an equal chance of winning; base positions, balance of terrain, ore count, and so on.
- Creativity, uniqueness, and last but not least, your opinion and suggestions!
