# Inheritance Lens

Inheritance Lens is a Crusader Kings III quality-of-life mod that previews succession outcomes without modifying core balance or AI behaviors. The mod evaluates each of the player's titles on demand, summarizes the predicted heirs, and displays the information in a dedicated panel and optional map mode. It supports feudal, clan, tribal, theocratic, administrative, imperial, and any other title-driven governments because predictions are computed from active succession laws.

## Features
- On-demand "Preview Succession" action that aggregates predicted heirs for every player-held county tier and above title.
- Custom panel styled after the vanilla realm view, summarizing recipients, succession laws, and explanations.
- Triggered map mode that colors titles by their predicted heir and shows a compact portrait legend.
- Warnings for elective titles, duchy fragmentation, potential confederate partition creations, vassal transfers, invalid heirs, and other risk cases.
- Lightweight caching with automatic invalidation on major succession changes.
- Game rule to control refresh cadence (on-demand only vs. long interval background refresh).
- Localization-ready strings with English text included.

## Non-Goals
- No changes to succession balance, stats, defines, AI, or economy.
- No new traits, modifiers, or powers beyond shortcuts to existing vanilla UIs.
- No assumptions based on government type; all predictions are title-law driven.

## Known Limitations
- Predictions rely on the same data available to the player and may briefly desync if multiple succession factors change simultaneously before the cache invalidates.
- Confederate partition warnings highlight likely new titles but cannot guarantee AI behavior around title creation.
- Complex elective tie-breakers are displayed using the game-provided candidate ordering; manual resolution may still be required.

## Compatibility
Inheritance Lens is designed to avoid overwriting vanilla files and should be compatible with most UI and mechanics mods. It relies exclusively on additive scripted content and standard hooks.

## Installation
Place the mod folder alongside `descriptor.mod` in your Crusader Kings III mod directory. Enable "Inheritance Lens" in the Paradox launcher.

## Credits
Designed and implemented by the Inheritance Lens development team with accessibility and localization in mind.
