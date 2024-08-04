# CORNE Keyboard

This README provides step-by-step instructions on how to change the layout of your CORN Keyboard using the QMK Configurator, compile the necessary files, and flash the new firmware.

## Requirements

-   QMK Firmware repository
-   QMK Toolbox (for flashing the firmware)
-   JSON file with your current layout (optional)

## Steps

### 1. Change Layout with QMK Configurator

1. Go to the [QMK Configurator](https://config.qmk.fm/).
2. Import your existing JSON file if you have one. You can do this by clicking on the "Upload" button and selecting your JSON file.
3. Modify the layout as needed. You can change the key assignments by clicking on the keys and selecting the desired function from the menu.
4. Once you are satisfied with your layout, export the new JSON file by clicking on the "Export" button.

### 2. Compile/Create the `keymap.c` File from JSON

1. In your QMK Firmware directory, run the following command to convert your JSON file to a `keymap.c` file:
    ```sh
    qmk json2c path/to/your_layout.json -o keyboards/crkbd/keymaps/your_keymap/keymap.c
    ```
    Replace `path/to/your_layout.json` with the path to your exported JSON file and `your_keymap` with a name for your keymap.

### 3. Compile/Create HEX File from `keymap.c` File

1. Navigate to the QMK Firmware root directory.
2. Run the following command to compile the firmware:
    ```sh
    qmk compile -kb crkbd -km your_keymap
    ```
    Replace `your_keymap` with the name of your keymap.

### 4. Flash Both Sides of CORN Keyboard

1. Connect one side of your CORN Keyboard to your computer.
2. Open QMK Toolbox.
3. Load the generated HEX file, which is located in the QMK Firmware root folder.
4. Put your keyboard into bootloader mode (usually by pressing the reset button on the keyboard).
5. Click on the "Flash" button in QMK Toolbox to flash the firmware to your keyboard.
6. Repeat steps 1-5 for the other side of the keyboard.

## Additional Resources

-   [QMK Firmware Documentation](https://docs.qmk.fm/)
-   [QMK Configurator](https://config.qmk.fm/)
-   [QMK Toolbox](https://github.com/qmk/qmk_toolbox)

## Troubleshooting

If you encounter any issues, consult the QMK Firmware documentation or seek help from the QMK community on their [Discord server](https://discord.gg/Uq7gKkQ).

Happy typing!
