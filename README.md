# ZMK Keyboard Configuration

This repository contains a ZMK firmware configuration for a Corne keyboard with three different setups to accommodate different operating systems and keyboard layouts.

## Three Configuration Modes

This configuration supports three distinct setups:

1. Mac with Swiss German Layout (Layers 0-2)

2. Windows with Swiss German Layout (Layers 3-5)

3. Windows with US International Layout (Layers 6-8)

## Switching Between Configurations

To switch between configurations, use the **raise layer** and press the **bottom-right key**:

1. **Mac DE → Windows DE:** From Layer 0, press Raise + bottom-right key → switches to Layer 3
2. **Windows DE → Windows US:** From Layer 3, press Raise + bottom-right key → switches to Layer 6
3. **Windows US → Mac DE:** From Layer 6, press Raise + bottom-right key → returns to Layer 0

The switching follows a linear cycle: **Mac DE → Win DE → Win US → Mac DE**

## Display Labels

If using nice!view displays, each layer shows its label:
- **Mac Layers:** "Mac 0", "Mac 1", "Mac 2"
- **Windows DE Layers:** "Win 0", "Win 1", "Win 2"
- **Windows US Layers:** "Win US 0", "Win US 1", "Win US 2"
