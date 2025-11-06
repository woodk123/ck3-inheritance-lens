# CK3 Inheritance Lens Modding Guidelines

This repository targets the modern Crusader Kings III modding stack. Keep these reminders in mind when adding or editing files:

## Encoding Requirements
- **Localization (.yml), scripted gameplay (.txt), and event files** must be saved with a UTF-8 byte order mark (BOM). The game logs `[E][lexer.cpp:299]: File ... should be in utf8-bom encoding` when the BOM is missing.
- GUI `.gui` files can remain plain UTF-8 without BOM, but avoid mixing encodings within the same file.

## GUI Definitions
- Wrap widget definitions inside the appropriate `guiTypes` blocks so the engine recognizes custom windows and scripted GUI helpers.
- Use valid widget type names (for example `windowType`, `containerType`, `buttonType`). Legacy placeholders such as `containerwindowtype` will raise `is not a valid widget/type/property` errors.
- Ensure `position`, `size`, and `parentanchor` arrays stay within their expected index ranges to avoid `Index out of bounds for gui percent value` errors.

## Scripted Content
- Follow CK3's syntax for scripted triggers, effects, and events: every block must have matching braces, valid keywords (`trigger = { ... }`, `effect = { ... }`, etc.), and unique IDs.
- Replace deprecated commands (like `clr_character_flag`) with their modern equivalents (`clear_character_flag`), and verify that referenced variables are initialized before use.
- Game rules defined in `common/game_rules` require `name`, `group`, `default`, and at least one `option` block.

Keeping these notes close should help prevent the log spam encountered previously and speed up debugging when expanding the inheritance lens feature set.
