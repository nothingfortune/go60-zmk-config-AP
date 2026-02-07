# MoErgo Go60 Custom Configuration for ZMK

![MoErgo Logo](moergo_logo.png)

This repo is the official ZMK configuration of the MoErgo Go60 wireless split keyboard. Use it to develop your own keymap and easily build your own ZMK firmware to run on your Go60.

**NOTE: You can also customize the layout of your Go60 keyboard with the Go60 Layout Editor webapp. For most users Go60 Layout Editor is the recommended and simpler option. More information is available at the official MoErgo Go60 Support site (see resources below).**

These steps will get you using your keymap on your keyboard in the fastest time possible. It uses the GitHub Actions feature to build your firmware online.

If you are looking to dig deeper into ZMK and develop new functionality, it is recommended to follow the steps of installing ZMK as found on the official ZMK documentation site (linked below).

## Resources
- The [official MoErgo Go60 Support](https://moergo.com/go60-support) web site. Go60 documentation and other technical resources.
- The [official MoErgo Discord Server](https://moergo.com/discord). Instant conversations with other Go60 users.

- The [official ZMK Documentation](https://zmk.dev/docs) web site. Find the answers to many of your questions about ZMK Firmware.
- The [official ZMK Discord Server](https://discord.gg/8cfMkQksSB). Instant conversations with other ZMK developers and users. Great technical resource!

- The [official MoErgo ZMK Distribution](https://github.com/moergo-sc/zmk). Repository for ZMK firmware customized for Go60 and Glove80.

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
