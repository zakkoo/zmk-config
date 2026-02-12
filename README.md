# ZMK Keyboard Configuration

This repository contains a ZMK firmware configuration for a Corne keyboard with three different setups to accommodate different operating systems and keyboard layouts.

## Three Configuration Modes

This configuration supports three distinct setups:

### 1. Mac with Swiss German Layout (Layers 0-2)
- **Default Layer:** Layer 0 - "Mac 0"
- **Lower Layer:** Layer 1 - "Mac 1" (symbols)
- **Raise Layer:** Layer 2 - "Mac 2" (function keys & numpad)
- **OS:** macOS
- **Keyboard Layout:** Swiss German (DE)

### 2. Windows with Swiss German Layout (Layers 3-5)
- **Default Layer:** Layer 3 - "Win 0"
- **Lower Layer:** Layer 4 - "Win 1" (symbols)
- **Raise Layer:** Layer 5 - "Win 2" (function keys & numpad)
- **OS:** Windows
- **Keyboard Layout:** Swiss German (DE)

### 3. Windows with US International Layout (Layers 6-8)
- **Default Layer:** Layer 6 - "Win US 0"
- **Lower Layer:** Layer 7 - "Win US 1" (symbols)
- **Raise Layer:** Layer 8 - "Win US 2" (function keys & numpad)
- **OS:** Windows
- **Keyboard Layout:** US International

## Switching Between Configurations

To switch between configurations, use the **raise layer** and press the **bottom-right key**:

1. **Mac DE → Windows DE:** From Layer 0, press Raise + bottom-right key → switches to Layer 3
2. **Windows DE → Windows US:** From Layer 3, press Raise + bottom-right key → switches to Layer 6
3. **Windows US → Mac DE:** From Layer 6, press Raise + bottom-right key → returns to Layer 0

The switching follows a linear cycle: **Mac DE → Win DE → Win US → Mac DE**

## Key Differences Between Swiss German and US International

### Swiss German Layout (Layers 0-5)
Swiss German keyboards require **Right-Alt (AltGr)** modifiers for many special characters:
- **@** requires `Right-Alt + G` (Mac) or `Right-Alt + 2` (Windows)
- **[** requires `Right-Alt + 5` (Mac) or `Right-Alt + [` (Windows)
- **]** requires `Right-Alt + 6` (Mac) or `Right-Alt + ]` (Windows)
- **{** requires `Right-Alt + 8` (Mac) or `Right-Alt + '` (Windows)
- **}** requires `Right-Alt + 9` (Mac) or `Right-Alt + \` (Windows)
- **\** requires `Right-Alt + Shift + 7` (Mac) or `Right-Alt + <` (Windows)
- **Umlauts** (ä, ö, ü) are direct keys on the Swiss German layout

### US International Layout (Layers 6-8)
US International keyboards use standard US symbol positions:
- **@** is `Shift + 2`
- **[** and **]** are direct bracket keys
- **{** and **}** are `Shift + [` and `Shift + ]`
- **\** is a direct key (above Enter)
- **Umlauts** (ä, ö, ü) require **Right-Alt** combinations:
  - **ä:** `Right-Alt + Q`
  - **ö:** `Right-Alt + P`
  - **ü:** `Right-Alt + Y`

### Why Different Windows Setups?
macOS and Windows handle the Swiss German keyboard layout differently, especially for AltGr/Right-Alt key sequences. The Windows DE setup (Layers 3-5) uses different key codes than the Mac DE setup (Layers 0-2) to produce the same symbols on Windows with a Swiss German layout.

The Windows US setup (Layers 6-8) provides an alternative for users who prefer or need to use US International layout on their Windows systems.

## Layer Structure

### Default Layers (0, 3, 6)
Standard QWERTY layout with:
- Home row mods access via layer taps on G and H
- Sticky modifiers for Ctrl, Shift, Cmd/Win
- Standard alphanumeric keys

### Lower Layers (1, 4, 7) - Symbol Layer
Access special characters and symbols:
- Row 1: Backtick, hash, percent, punctuation
- Row 2: Brackets, parentheses, umlauts
- Row 3: Braces, operators, special characters
- Thumb keys: Currency symbols

**Note:** Umlauts (ä, ö, ü) remain in the same visual position across all setups for muscle memory consistency, even though the underlying key codes differ between Swiss German and US International layouts.

### Raise Layers (2, 5, 8) - Function Keys & Numpad
- Row 1: F1-F5, numpad 7-9
- Row 2: F6-F8, numpad 4-6, navigation arrows
- Row 3: F9-F12, numpad 1-3, Bluetooth controls, layer switching
- Thumb keys: Enter, numpad 0

## Building and Flashing

This configuration uses GitHub Actions for automated firmware builds. To update your keyboard:

1. Push changes to the `main` branch
2. Wait for GitHub Actions to complete the build
3. Download the firmware file from the Actions artifacts
4. Flash to your keyboard using the bootloader

## Display Labels

If using nice!view displays, each layer shows its label:
- **Mac Layers:** "Mac 0", "Mac 1", "Mac 2"
- **Windows DE Layers:** "Win 0", "Win 1", "Win 2"
- **Windows US Layers:** "Win US 0", "Win US 1", "Win US 2"

## License

This configuration is provided as-is for personal use.
