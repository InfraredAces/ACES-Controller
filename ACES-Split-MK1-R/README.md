# GP2040 Configuration for ACES Split MK1

![Pin Mapping](assets/PinMapping.png)

To add config, update cmake.yml to include "ACES-Split-MK1" in the matrix

```
jobs:
  build:
    strategy:
      matrix:
        GP2040_BOARDCONFIG: [ACES-Split-MK1-R]
```

# ACES Split MK1

## Changes from default Pico pinout.

- Remove Turbo from GPIO pin 14
- Remove Turbo LED from GPIO pin 15
- Add SOCD2 to GPIO pin 14
- Add SOCD1 to GPIO pin 15
- Add Extra Button to GPIO pin 22
- Add RS to GPIO pin 26
- Add LS to GPIO pin 27

## Changes to default Pico Add On Configuration

### SOCD Slider

- Add Enable definition (Disabled for time being)

```
#define SLIDER_SOCD_ENABLED 0
```

- Set SLIDER_SOCD_SLOT_ONE to SOCD_MODE_NEUTRAL
- Set SLIDER_SOCD_SLOT_TWO to SOCD_MODE_SECOND_INPUT_PRIORITY

### RGB LED
- Set LED_BRIGHTNESS_MAXIMUM to 80
- Set LED_BRIGHTNESS_STEPS to 10
- Change LED Chain Order

```
#define LEDS_DPAD_LEFT   0
#define LEDS_DPAD_DOWN   1
#define LEDS_DPAD_RIGHT  2
#define LEDS_BUTTON_B3   3
#define LEDS_BUTTON_B4   4
#define LEDS_BUTTON_R1   5
#define LEDS_BUTTON_L1   6
#define LEDS_BUTTON_L2   7
#define LEDS_BUTTON_R2   8
#define LEDS_BUTTON_B2   9
#define LEDS_BUTTON_B1   10
#define LEDS_DPAD_UP     11
```

Waiting to add Extra Button to RGB LED chain

### Extra Button Add On
- Add Enable definition

```
#define EXTRA_BUTTON_ENABLED 1
```

- Change EXTRA_BUTTON_MASK to GAMEPAD_MASK_DU
- Change EXTRA_BUTTON_PIN to 22

### Hotkey Action Mapping
- Set HOTKEY_F2_LEFT_ACTION to HOTKEY_SOCD_FIRST_INPUT
- Set HOTKEY_F2_RIGHT_ACTION to HOTKEY_SOCD_LAST_INPUT