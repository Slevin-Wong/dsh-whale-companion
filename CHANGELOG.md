# Changelog

All notable changes to this project are documented here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and the project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

- Nothing yet. Ideas and bug reports are welcome via [Issues](../../issues).

## [1.3.0] - 2026-11-06

### Changed

- Whole widget scaled to 1.5×: 234px card, 204px portrait, 24px corner offset, 21px card radius.
- Type scaled to 2×: 38px balance figure, 23px label, 22px bonus line, 22–26px controls.
- Portrait is now a rounded square instead of a circle, so square meme images are shown uncropped.

### Added

- Sixteen candidate expressions collected from the DeepSeek-chan meme pack: every square preview, plus one near-square preview (`052`) center-cropped under the ≤ 1:1.2 rule.
- Automatic one-step-down type size for balances longer than nine characters, so long amounts never overflow the card.
- Plugin icon now uses the default expression (`007`).
- Distribution artifacts: `whale-companion-1.3.0.zip` and `whale-companion-1.3.0.tgz`.

### Removed

- Four non-square previews that exceed the 1:1.2 ratio: `056`, `058`, `087`, `097`. The previous default (`097`, the money-counting expression) is therefore no longer in the rotation.

## [1.2.0] - 2026-11-06

### Added

- Six expressions with click-to-switch, `Shift`-click random, previous/next buttons.
- Three rotation modes: auto in order (60s), auto random, manual.
- Auto rotation pauses while the pointer hovers the card.
- Clicking the balance figure refreshes immediately.

### Changed

- Vertical card layout: portrait above the balance panel, 156px wide.
- Balance figure raised to 19px; label, bonus and controls moved to their own line.

## [1.1.0] - 2026-11-06

### Changed

- Moved from `conversation.composer.dock` to the frame-wide `shell.overlay` layer, so the widget is visible on every page and session.
- Replaced the drawn SVG mascot with fan art from the DeepSeek-chan meme pack.
- Default placement: fixed bottom-right, 64px round portrait.

### Added

- Artwork notice: fan-made, non-commercial, original creators retain all rights.

## [1.0.0] - 2026-11-06

### Added

- First working bundle: a small whale-girl pet under the composer showing the DeepSeek account balance as text.
- Balance reads through the Host account channel every 30 seconds and on page visibility.
- Signed-out, unavailable and failed states with the last known amount kept on screen.

[Unreleased]: ../../compare/v1.3.0...HEAD
[1.3.0]: ../../compare/v1.2.0...v1.3.0
[1.2.0]: ../../compare/v1.1.0...v1.2.0
[1.1.0]: ../../compare/v1.0.0...v1.1.0
[1.0.0]: ../../releases/tag/v1.0.0
