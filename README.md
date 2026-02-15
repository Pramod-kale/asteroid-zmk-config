# Asteroid ZMK Configuration

A complete ZMK firmware configuration for the **Asteroid** split keyboard - a custom 5x6 layout split keyboard (60 keys total) designed for wireless operation with Nice!Nano v2 controllers.

## Features

- **5x6 Split Layout**: 60 keys total (30 per side)
- **Wireless Bluetooth**: Nice!Nano v2 nRF52840 controllers
- **QWERTY Layout**: Modern ergonomic layout with function layers
- **ZMK Studio Support**: Runtime keymap configuration without flashing firmware
- **Mouse Support**: Built-in mouse movement and click functionality
- **3 Bluetooth Devices**: Quick switching between paired devices
- **Power Management**: 15-minute sleep timeout for battery conservation

## ZMK Studio Support

This configuration includes full **ZMK Studio** support, allowing you to modify your keymap in real-time without flashing new firmware.

### Getting Started with ZMK Studio

1. **Flash the Firmware**: Build and flash the firmware to your keyboard (this only needs to be done once)

2. **Connect Your Keyboard**:
   - **USB**: Connect the left side (central) via USB cable
   - **Bluetooth**: Pair the keyboard with your computer

3. **Access ZMK Studio**:
   - **Web App**: Visit [zmk.studio](https://zmk.studio/) in Chrome/Edge
   - **Desktop App**: Download from the [ZMK Studio releases page](https://github.com/zmkfirmware/zmk-studio/releases)

4. **Unlock Your Keyboard**: Press the studio unlock key (FN + SHIFT) to allow ZMK Studio to make changes

5. **Configure Your Layout**: Use the visual interface to:
   - Remap any key to any function
   - Create custom layers
   - Adjust behaviors and settings
   - Save and load different configurations

### ZMK Studio Features Available

- ✅ Real-time keymap editing
- ✅ Layer management and naming
- ✅ Bluetooth device switching
- ✅ Mouse controls configuration
- ✅ Function key assignments
- ✅ Media key controls
- ✅ Multiple layout support
- ✅ Import/export configurations

### Studio Unlock Key

The studio unlock key is accessed by pressing **FN + SHIFT** (hold the FN key and press right Shift). This puts the unlock key in the function layer in an easily accessible location but out of the way during normal typing. Once pressed, you can modify your keymap through the ZMK Studio interface.

**Note**: After using ZMK Studio to modify your keymap, changes made to the `.keymap` file will not take effect unless you perform a "Restore Stock Settings" action in ZMK Studio.

## Hardware Specifications

- **Controllers**: Nice!Nano v2 (nRF52840)
- **Layout**: 5x6 split (60 keys total)
- **Connectivity**: Wireless Bluetooth + USB-C
- **Battery**: 110mAh LiPo (recommended)
- **Switches**: MX-compatible
- **Keycaps**: Standard 1u profile

## Pin Configuration

### Left Side (Central/Master)
- **Rows**: P0.06, P0.08, P0.20, P0.22, P0.24 (5 rows)
- **Columns**: P1.15, P1.00, P1.04, P1.06, P1.13, P1.11 (6 columns)

### Right Side (Peripheral/Slave)
- **Rows**: P0.31, P0.29, P0.02, P0.10, P0.09 (5 rows)
- **Columns**: P1.06, P1.04, P1.00, P1.11, P1.13, P1.15 (6 columns)

## Default Layout

### Layer 0 (Base/QWERTY)
```
┌─────┬─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │  1  │  2  │  3  │  4  │  5  │   │  6  │  7  │  8  │  9  │  0  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ ESC │  Q  │  W  │  E  │  R  │  T  │   │  Y  │  U  │  I  │  O  │  P  │BKSP │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ TAB │  A  │  S  │  D  │  F  │  G  │   │  H  │  J  │  K  │  L  │  ;  │ENTER│
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│SHIFT│  Z  │  X  │  C  │  V  │  B  │   │  N  │  M  │  ,  │  .  │  /  │SHIFT│
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │CTRL │ ALT │ CMD │SPACE│   │ FN  │     │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────┴─────┴─────┴─────┘
```

### Layer 1 (Function/FN)
```
┌─────┬─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │ F1  │ F2  │ F3  │ F4  │ F5  │   │ F6  │ F7  │ F8  │  -  │  =  │     │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│  `  │     │     │     │     │     │   │ F11 │ F12 │     │  [  │  ]  │ DEL │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │PREV │PLAY │NEXT │VOL+ │VOL- │   │BRI- │BRI+ │  ↑  │     │  '  │  \  │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │ BT1 │ BT2 │ BT3 │BTCLR│   │     │  ←  │  ↓  │  →  │     │UNLCK│
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │   │     │     │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────┴─────┴─────┴─────┘
```

## Key Features

### Bluetooth Management
- **BT1, BT2, BT3**: Switch between 3 paired devices (FN + X, C, V)
- **BTCLR**: Clear all pairings (FN + B)
- **Auto-sleep**: 15 minutes of inactivity

### Mouse Controls
- **Mouse Clicks**: Left/Right click (FN + N, M)
- **Mouse Movement**: Arrow-style movement (FN + Arrow keys)

### Media Controls
- **Play/Pause**: FN + S
- **Previous/Next**: FN + A, D
- **Volume**: FN + F, G

### Function Keys
- **F1-F10**: FN + Number row
- **F11-F12**: FN + Y, U

## Building the Firmware

### Prerequisites
- [ZMK development environment](https://zmk.dev/docs/development/setup)
- West build tool
- ARM GCC toolchain

### Build Commands

```bash
# Build left side (with ZMK Studio support)
west build -d build/left -b nice_nano_v2 -- -DSHIELD=asteroid_left -DZMK_CONFIG="$(pwd)/config"

# Build right side
west build -d build/right -b nice_nano_v2 -- -DSHIELD=asteroid_right -DZMK_CONFIG="$(pwd)/config"
```

### GitHub Actions
This repository includes automated builds via GitHub Actions. Firmware files are automatically generated for each commit and available in the Actions tab.

## Flashing Instructions

1. **Download Firmware**: Get the `.uf2` files from GitHub Actions or local build
2. **Enter Bootloader**: Double-tap the reset button on each Nice!Nano
3. **Copy Firmware**: Drag the appropriate `.uf2` file to the mounted drive
4. **Repeat**: Flash both left and right sides.

**Important**: Always flash the left side (central) first, then the right side.

## Troubleshooting

### ZMK Studio Connection Issues
- Ensure the left side is connected via USB or properly paired via Bluetooth
- Try refreshing the ZMK Studio web page or restarting the desktop app
- Press the studio unlock key (FN + SHIFT) to enable configuration mode
- Check that your browser supports WebHID (Chrome/Edge required for web app)

### Bluetooth Issues
- Clear pairings: FN + B (BTCLR)
- Re-pair both halves and host device
- Check battery levels
- Ensure both halves are powered on

### Build Issues
- Verify all pin assignments match your hardware
- Check for syntax errors in configuration files
- Ensure ZMK is up to date
- Review build logs for specific error messages

### Split Communication
- Both halves must be powered on
- Left side acts as central (connects to computer)
- Right side connects to left side automatically
- Reset both halves if connection fails

## Customization

### Adding Features
- **RGB Underglow**: Uncomment RGB settings in `asteroid.conf`
- **Rotary Encoders**: Uncomment encoder settings and add to device tree
- **Displays**: Add OLED configuration for status display

### Layout Modifications
With ZMK Studio support, you can modify your layout in real-time without editing configuration files. However, if you prefer to edit the source:

1. Edit `config/asteroid.keymap` for key assignments
2. Modify `config/asteroid.conf` for feature settings
3. Update device tree files for hardware changes
4. Rebuild and flash firmware

## Contributing

Feel free to submit issues, feature requests, or pull requests to improve this configuration.

## License

This configuration is provided under the MIT License. See LICENSE file for details.

## Acknowledgments

- [ZMK Firmware](https://zmk.dev/) - The foundation for this configuration
- [Nice!Nano](https://nicekeyboards.com/nice-nano/) - Excellent wireless controller
- ZMK Community - For support and inspiration
