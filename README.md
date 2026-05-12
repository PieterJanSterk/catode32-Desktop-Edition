# Catode32 Desktop Emulator

This repository provides a desktop-based environment for Catode32, allowing you to run and test your code in a local window using Python and Pygame. It serves as a hardware abstraction layer, replacing physical components (OLED, GPIO pins) with a windowed interface and keyboard input.

## What's Included

The emulator consists of 5 core files that bridge the gap between MicroPython hardware and your desktop:

| File | Purpose |
| :--- | :--- |
| **main_desktop.py** | The entry point—replaces the standard `boot.py` and `main.py`. |
| **config_desktop.py** | Hardware configuration—manages screen scale and key mappings. |
| **renderer_desktop.py** | The display engine—draws to a Pygame window instead of the OLED. |
| **input_desktop.py** | Input handler—reads your computer keyboard instead of GPIO pins. |
| **framebuf.py** | A pure-Python replacement for MicroPython's built-in module. |

## Installation

Follow these steps to get the desktop version running on your machine:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/moonbench/catode32](https://github.com/moonbench/catode32)
    ```
2.  **Add the Desktop files:**
    Place the 5 files listed above into the `/src` folder of your project.
3.  **Install dependencies:**
    The emulator requires Pygame to handle the window and input:
    ```bash
    pip install pygame
    ```
4.  **Run the emulator:**
    Navigate to the `/src` folder and execute the main script:
    ```bash
    python main_desktop.py
    ```

## Controls

The keyboard is mapped to simulate the physical buttons of the Catode32 hardware:

| Keyboard Key | Hardware Button |
| :--- | :--- |
| **Arrow Keys** | D-Pad |
| **Z / X** | A / B |
| **A / S** | Menu 1 / Menu 2 |
| **Escape** | Quit Emulator |

## Customization

### Adjusting Window Size
If the default window is too small or too large for your monitor, you can easily scale the interface. Open `config_desktop.py` and modify the `DISPLAY_SCALE` variable:

* **Scale 6 (Default):** Resulting window is 768 × 384px.
* **Scale 8:** Resulting window is 1024 × 512px (recommended for high-resolution monitors).

Increasing this number will provide a "chunkier," more visible retro-pixel aesthetic on modern displays.
