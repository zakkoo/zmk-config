# zmk-config

ZMK firmware config for a split Corne (nice!nano v2 + nice!view), built via GitHub Actions.

- `config/corne.keymap` — all 9 layers
- `config/corne.conf` — Kconfig (display on, Studio locking off)
- `build.yaml` — CI build matrix (both halves, ZMK Studio enabled)

## Keymap layout

Three "worlds", each with three layers:

| Layers | World |
|---|---|
| 0/1/2 | macOS, Swiss German |
| 3/4/5 | Windows, Swiss German |
| 6/7/8 | Windows, US Standard |

Within each world: `mo0` = default, `mo1` = symbols, `mo2` = function keys + numpad.
Worlds are cycled with `mo2` + bottom-right key (`&to`).

## Rule: keymap edits must update the header docs

`config/corne.keymap` starts with hand-maintained ASCII layer maps. **They are not
auto-generated.** Every change to a `bindings = <...>` block must be mirrored in the
matching ASCII map in the same file, in the same commit. A binding change without the
doc update is an incomplete change — do not report it as done.

When editing a binding:

1. Find the key's number in the KEY NUMBERING grid in the file header.
2. Apply it across all layers of that role (symbols = 1/4/7, fn/numpad = 2/5/8,
   default = 0/3/6) unless the change is deliberately world-specific.
3. Update that key's cell in the corresponding ASCII map. Cells are 7 chars wide —
   keep columns aligned.
4. If the behavior is non-obvious or destructive, add a line to that layer's `Note:` block.

The same rule is restated at the top of `corne.keymap` itself.
