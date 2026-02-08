# MoErgo Go60 Custom Configuration for ZMK

![MoErgo Logo](moergo_logo.png)

This repo is a fork official ZMK configuration of the MoErgo Go60 wireless split keyboard. 

Keymaps have been adjusted and refined based on personal preferences.

## Resources
- The [official MoErgo Go60 Support](https://moergo.com/go60-support) web site. Go60 documentation and other technical resources.

- The [official MoErgo Discord Server](https://moergo.com/discord). Instant conversations with other Go60 users.

- The [official ZMK Documentation](https://zmk.dev/docs) web site. Find the answers to many of your questions about ZMK Firmware.
- The [official ZMK Discord Server](https://discord.gg/8cfMkQksSB). Instant conversations with other ZMK developers and users. Great technical resource!

- The [official MoErgo ZMK Distribution](https://github.com/moergo-sc/zmk). Repository for ZMK firmware customized for Go60 and Glove80.

- The [ZMK Helpers v2] (https://github.com/urob/zmk-helpers/).
This is a collection of helper macros (formerly zmk-nodefree-config), simplifying the configuration of ZMK keymaps.


## Instructions
1. Log into, or sign up for, your personal GitHub account.
2. Create your own repository using this repository as a template ([instructions](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)) and check it out on your local computer.
3. Edit the keymap file(s) to suit your needs
4. Commit and push your changes to your personal repo. Upon pushing it, GitHub Actions will start building a new version of your firmware with the updated keymap.

## Firmware Files
To locate your firmware files and reflash your Go60...
1. log into GitHub and navigate to your personal config repository you just uploaded your keymap changes to.
2. Click "Actions" in the main navigation, and in the left navigation click the "Build" link.
3. Select the desired workflow run in the centre area of the page (based on date and time of the build you wish to use). You can also start a new build from this page by clicking the "Run workflow" button.
4. After clicking the desired workflow run, you should be presented with a section at the bottom of the page called "Artifacts". This section contains the results of your build, in a file called "go60.uf2"
5. Download the go60.uf2
6. Flash the firmware to Go60 according to the user documentation on the official Go60 Support website (linked above)

Your keyboard is now ready to use.

## Configuration Features

### Layer Architecture (12 Layers)

This configuration implements a comprehensive 12-layer system optimized for ergonomic typing and advanced functionality:

**Primary Layers:**
- **Layer 0 - Base (QWERTY)**: Standard QWERTY with bilateral home row mods (GACS order)
- **Layer 1 - Typing**: Alternative typing layer accessible via Magic layer
- **Layer 2 - Autoshift**: Auto-capitalization on hold for all alphanumeric keys

**Navigation & Input:**
- **Layer 3 - Nav**: Navigation layer with arrow keys and modifier access (hold Space/Enter)
- **Layer 4 - Symbol**: Symbol layer on home row (hold G/H or thumb keys)
- **Layer 6 - Numpad**: Full numpad layout (tap dance on bottom right key)

**Specialized Functions:**
- **Layer 5 - Gaming**: Toggle layer that disables home row mods for gaming
- **Layer 7 - Cursor**: Advanced cursor control with mouse and scroll functions
- **Layer 8 - MouseSlow**: Precision mouse movement (1:9 speed scaling)
- **Layer 9 - MouseFast**: Fast mouse movement (3:1 speed scaling)
- **Layer 10 - MouseWarp**: Warp-speed mouse movement (12:1 speed scaling)
- **Layer 11 - Magic**: System control (RGB, Bluetooth, layer switching)

### Home Row Mods (Bilateral)

**Configuration:** TailorKey-style bilateral home row mods prevent accidental activation during same-hand typing.

**Left Hand (GACS):**
- A = GUI (⌘ Cmd on macOS)
- S = ALT (⌥ Option)
- D = CTRL (⌃ Control)
- F = SHIFT (⇧ Shift)

**Right Hand (SCAG):**
- J = SHIFT (⇧ Shift)
- K = CTRL (⌃ Control)
- L = ALT (⌥ Option)
- ; = GUI (⌘ Cmd)

**Timing Configuration:**
- Index fingers: 190ms tapping-term (fastest)
- Middle fingers: 210ms tapping-term
- Ring fingers: 240ms tapping-term
- Pinky fingers: 280ms tapping-term (slowest)
- `hold-trigger-on-release` enabled for more reliable modifier activation

### Combos

**Function Keys (F1-F12):**
- F1-F5: Left hand column pairs (rows 1+2)
- F6-F9: Right hand column pairs (rows 1+2)
- F10-F12: Right hand special combinations

**Modifiers:**
- Both thumb T1 keys: Caps Lock
- Right pinky combos: Sticky Hyper (⌘⌃⌥⇧) and Meh (⌃⌥⇧)
- Left hand combos: Alt+Tab (CTRL) and Cmd+Tab (GUI) with cursor layer access

**Layer Access:**
- Gaming toggle: Left hand bottom corner combo

### Cirque Trackpad Integration

**Left Trackpad (Scroll):**
- Default: Scroll mode with Y-axis invert
- MouseSlow: 5:14 scaling
- MouseFast: 3:2 scaling
- MouseWarp: 13:3 scaling

**Right Trackpad (Cursor):**
- Default: Mouse cursor with 2-second temporary Cursor layer activation
- MouseSlow: 1:1 scaling (precision)
- MouseFast: 4:1 scaling
- MouseWarp: 6:1 scaling (rapid positioning)

### Special Features

**Auto-Pair Brackets:**
- Mod-morph behaviors automatically insert paired brackets with cursor repositioning
- N9 key: Types `()` with cursor between when modifier held
- Comma key: Types `<>` when modifier held
- Double-quote key: Types `""` when modifier held

**Smart Behaviors:**
- Grave/Escape: Context-aware ESC/` key
- Backspace: Hold for word deletion (Option+Backspace)
- Arrow keys: Hold for word jump navigation
- Magic key: Hold for Magic layer, tap for RGB status

**macOS Optimizations:**
- Screenshot macro (⌘⇧4)
- Hyper key macro (⌘⌃⌥⇧) for Raycast/Alfred
- Cursor selection macros (select word, line, extend selection)
- Mod-tab switchers for app switching with cursor navigation

### Layer Access Quick Reference

| Layer | Activation Method |
|-------|------------------|
| Base | Default layer |
| Typing | Magic layer → Key binding |
| Autoshift | Magic layer → Thumb key |
| Nav | Hold Space or Enter |
| Symbol | Hold G, H, or thumb keys |
| Gaming | Combo toggle |
| Numpad | Tap dance bottom right key |
| Cursor | Alt+Tab or Cmd+Tab combos |
| MouseSlow/Fast/Warp | Hold keys in Cursor layer |
| Magic | Hold bottom left key |

## Keyboard Layout Reference Materials

This section provides background on keyboard layouts, ergonomic concepts, and resources that informed this configuration.

### TailorKey
**Website:** https://sites.google.com/view/tailorkey/tailorkey

TailorKey is a keymap project by Moosy Research focused on "supercharging your typing experience while keeping familiarity intact." It provides pre-built configurations for both Go60 and Glove80 keyboards with ergonomic optimizations.

*"Don't just adapt to a layout. Let the layout adapt to you—make it truly yours."* — Moosy

### Moosy Research - Learn
**Website:** https://sites.google.com/view/keyboards/learn

Key insights on mastering keyboard layouts:

**Training Tips:**
- Practice 30 minutes daily; even short sessions help
- Practice before sleep—your brain consolidates learning overnight
- Focus on accuracy first, speed comes later
- Use tools like [keybr.com](https://keybr.com) and [monkeytype.com](https://monkeytype.com) for training

**Alternative Layouts:**
- QWERTY is objectively inefficient, but the fastest typists still use it
- Switching layouts is about comfort and long-term ease, not speed
- Your brain builds separate muscle memories for different keyboard types—you can keep QWERTY on laptop while learning a new layout on Go60

**Symbols are the Problem:**
- Programmers strain their right pinky/ring finger on symbol keys
- Two approaches: (1) Use a dedicated symbol layer with symbols on home row, or (2) Remap number row shifted symbols using ZMK mod-morph

### Glorious Engrammer by Sunaku
**Repository:** https://github.com/sunaku/glove80-keymaps
**Interactive Layer Map:** https://sunaku.github.io/moergo-glove80-keyboard.html#layers

A comprehensive Glove80/MoErgo keymap featuring Miryoku-style layers and home row mods. Key concepts applicable to this config:

**Home Row Mods (GACS order):**
- G = GUI (Win/Cmd/Super)
- A = ALT (Alt/Option)
- C = CTL (Control)
- S = SFT (Shift)
- For macOS, automatically rearranges to "CAGS" since Cmd is used like Ctrl

**Difficulty Levels for Learning:**
```
#define DIFFICULTY_LEVEL 1 // novice (500ms)
#define DIFFICULTY_LEVEL 2 // slower (400ms)
#define DIFFICULTY_LEVEL 3 // normal (300ms)
#define DIFFICULTY_LEVEL 4 // faster (200ms)
#define DIFFICULTY_LEVEL 5 // expert (100ms)
```

**Key Features:**
- Factory layer escape route (Magic + T3) for easy return to default
- Six specialized layers: Cursor, Number, Function, Symbol, Mouse, System
- Bilateral combinations enforcement for proper touch-typing technique
- Shift forgiveness using `hold-while-undecided` feature
- One-shot sticky shifts on pinky keys for single letter capitalization
- Unicode/Emoji support through ZMK macros

**Key Auto-Repeat:**
- Dual-function keys don't auto-repeat when held
- Use "Tap then hold" method OR use typing layer access keys

### Additional Resources

**Typing Practice:**
- [keybr.com](https://keybr.com) - Adaptive typing trainer (enable split matrix mode)
- [monkeytype.com](https://monkeytype.com) - Speed testing with split keyboard mode
- [ngram-type](https://ranelpadon.github.io/ngram-type/) - Practice common letter patterns
- [speedtyper.dev](https://speedtyper.dev) - Code-focused typing practice

**Layout Analyzers:**
- [Alpha Test Drive Tool](https://sites.google.com/view/keyboards/tools/alphatestdrive_glove80) - Test alternative layouts without changing config

**Key Philosophy:**
*"Touch typing is like learning to ride a bike—don't look down; keep your eyes forward, trust your movement, and go with the rhythm."* — Moosy
