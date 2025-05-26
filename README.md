# Asteroid Split Keyboard - ZMK Configuration

This repository contains the ZMK firmware configuration for the Asteroid split keyboard.

## Keyboard Specifications

- **Layout**: 6x6 split keyboard (72 keys total)
- **Controller**: Pro Micro nRF52840 (Nice!Nano v2 compatible)
- **Connection**: Wireless split with Bluetooth
- **Left side**: Central (master)
- **Right side**: Peripheral (slave)

## Features

- **QWERTY Layout**: Standard QWERTY layout with function layers
- **3 Bluetooth Connections**: Switch between up to 3 paired devices
- **Power Management**: Auto-sleep after 15 minutes of inactivity
- **Split Communication**: Wireless communication between halves
- **Function Layers**:
  - Layer 0: Default QWERTY with number row and arrow keys
  - Layer 1: Bluetooth controls, symbols, and mouse movement

## Pin Mapping

Based on your PCB layout:

### Row Pins (Same for both halves)
- Row 0: Pin 006
- Row 1: Pin 008
- Row 2: Pin 017
- Row 3: Pin 020
- Row 4: Pin 022
- Row 5: Pin 011

### Column Pins
**Left Half:**
- Col 0: Pin 115
- Col 1: Pin 100
- Col 2: Pin 104
- Col 3: Pin 106
- Col 4: Pin 113
- Col 5: Pin 111

**Right Half:**
- Col 6: Pin 106
- Col 7: Pin 104
- Col 8: Pin 100
- Col 9: Pin 111
- Col 10: Pin 113
- Col 11: Pin 115

## Key Layout

```
Default Layer (0) - Standard Mac QWERTY:
┌─────┬─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ `~  │ 1!  │ 2@  │ 3#  │ 4$  │ 5%  │   │ 6^  │ 7&  │ 8*  │ 9(  │ 0)  │ -_  │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ TAB │  Q  │  W  │  E  │  R  │  T  │   │  Y  │  U  │  I  │  O  │  P  │ [{  │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│CAPS │  A  │  S  │  D  │  F  │  G  │   │  H  │  J  │  K  │  L  │ ;:  │ '"  │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│SHIFT│  Z  │  X  │  C  │  V  │  B  │   │  N  │  M  │ ,<  │ .>  │ /?  │SHIFT│
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │ FN  │CTRL │ OPT │ CMD │   │ SPC │ CMD │ OPT │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │   │     │     │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────┴─────┴─────┴─────┘
```

## Function Layer (FN + Key)

Access by holding the FN key (bottom row, third position from left):

**Function Keys & System:**
- **Row 1**: ESC, F1-F11 (complete function key row)
- **Row 2**: BT1-BT5 (Bluetooth device selection), F12, Volume Down/Up, Mute, Previous Track
- **Row 3**: Missing symbols: = (equals), Return
- **Row 4**: Play/Pause, Next Track, Bluetooth Clear
- **Row 5**: Arrow keys (←↓↑→) for navigation

**Missing Keys from Standard Layout:**
- **]} (right bracket)**: FN + P
- **\| (backslash/pipe)**: FN + [{
- **= (equals)**: FN + ;
- **Return**: FN + '
- **Delete**: FN + /

## Complete Mac Keyboard Compatibility

This layout provides **100% Mac keyboard functionality**:

✅ **All standard keys**: Every key from a Mac keyboard is accessible
✅ **Proper SHIFT behavior**: All shifted symbols work exactly as expected
✅ **Function keys**: F1-F12 accessible via FN layer
✅ **Media controls**: Volume, play/pause, track navigation
✅ **Bluetooth**: 5-device switching + clear function
✅ **Navigation**: Arrow keys via FN layer
✅ **System keys**: ESC, Delete, Return all accessible

**Standard Mac Key Behavior:**
- SHIFT + letters = Uppercase
- SHIFT + numbers = Symbols (! @ # $ % ^ & * ( ))
- SHIFT + symbols = Alternate symbols ({ } | + _ etc.)
- All modifier combinations work as expected

## Building the Firmware

This configuration is designed to work with GitHub Actions for automatic firmware building. When you push changes to this repository, the firmware will be automatically built and available as artifacts.

### Manual Building

If you want to build locally:

1. Set up the ZMK development environment
2. Clone this repository to your ZMK config folder
3. Build with: `west build -d build/left -b nice_nano_v2 -- -DSHIELD=asteroid_left`
4. Build with: `west build -d build/right -b nice_nano_v2 -- -DSHIELD=asteroid_right`

## Flashing

1. Download the firmware files from GitHub Actions artifacts
2. Put your Nice!Nano into bootloader mode (double-tap reset)
3. Copy the `.uf2` file to the mounted drive
4. Repeat for both halves

## Pairing Split Halves

1. Flash both halves with their respective firmware
2. Reset both halves
3. The left half will appear as "Asteroid" in Bluetooth settings
4. The halves should automatically pair with each other

## Customization

You can customize the keymap by editing `config/asteroid.keymap`. The configuration supports:
- Custom key bindings
- Macro definitions
- Tap-dance behaviors
- Combo keys
- RGB underglow (if hardware is added)
- Rotary encoder support (if hardware is added)

## Troubleshooting

- **Split halves not communicating**: Reset both halves and ensure they're both powered
- **Keys not responding**: Check your wiring against the pin mapping above
- **Bluetooth issues**: Clear pairings and re-pair devices
- **Battery drain**: Ensure sleep mode is working (15-minute timeout)

## Contributing

Feel free to submit issues and pull requests to improve this configuration.