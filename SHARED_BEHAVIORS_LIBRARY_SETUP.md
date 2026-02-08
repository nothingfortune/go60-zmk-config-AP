# Shared ZMK Behaviors Library Setup

This guide explains how to create and use a shared ZMK behaviors library across multiple keyboard repositories, keeping your custom behaviors in sync.

---

## 1. Create the Shared Behaviors Repo

1. On GitHub, create a new repository (e.g. `zmk-behaviors-lib`).
2. Locally, clone it and create a structure like:
    ```
    zmk-behaviors-lib/
      dts/
        behaviors/
          hold-taps.dtsi
          mod-morphs.dtsi
          macros.dtsi
    ```
3. Copy your custom behavior definitions (from each board's keymap) into these `.dtsi` files, grouping by type.
4. Commit and push.

---

## 2. Add the Library as a West Module in Each Board Repo

1. In each keyboard repo, edit `west.yml`:
    ```yaml
    manifest:
      projects:
        - name: zmk-behaviors-lib
          url: https://github.com/YOURNAME/zmk-behaviors-lib
          revision: main
    ```
2. Run:
    ```sh
    west update
    ```

---

## 3. Include Shared Behaviors in Your Keymap

At the top of your keymap file, add:
```dts
#include <zmk-behaviors-lib/dts/behaviors/hold-taps.dtsi>
#include <zmk-behaviors-lib/dts/behaviors/mod-morphs.dtsi>
#include <zmk-behaviors-lib/dts/behaviors/macros.dtsi>
```

---

## 4. Use Behaviors as Usual

- Reference your shared behaviors in your keymap as you would any local behavior.
- When you update a behavior in the shared repo, just `git pull` and `west update` in each board repo to sync.

---

## 5. Tips

- Keep behaviors generic and parameterized for maximum reuse.
- Use version tags/releases in the shared repo for stability.
- Document each behavior in the `.dtsi` files for clarity.

---

## 6. Troubleshooting

- If a behavior is not found, check the include path and that `west update` completed successfully.
- If you need board-specific overrides, define those after the shared includes in your keymap.

---

## Example Directory Layout

```
/your-keyboard-repo/
  config/
    go60.keymap
  west.yml
  ...
  modules/
    zmk-behaviors-lib/
      dts/behaviors/hold-taps.dtsi
      dts/behaviors/mod-morphs.dtsi
      dts/behaviors/macros.dtsi
```

---

## 7. Keeping Everything in Sync

- Make all behavior changes in the shared repo.
- Pull and update in each board repo as needed.
- Use GitHub Actions in each board repo as before; no changes needed for CI.

---

**You now have a maintainable, DRY setup for ZMK behaviors across all your boards!**
