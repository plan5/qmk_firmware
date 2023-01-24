# qpad-mk50-picow

![qpad-mk50-picow front](front.jpg)
![qpad-mk50-picow back inside](back.jpg)

This project hand-wires a Raspberry Pi Pico to the cheap QPAD MK-50 mechanical
keyboard (105 key ISO version). For another project using the Raspberry Pi Pico
but with direct pin wiring, see [Adafruit Macropad](../../adafruit/macropad/).

The rows on this PCB are scattered all over the place and it was no fun tracing
them. I had to sacrifice right Ctrl because that would have needed an additional
pin. It's now effectively a left Ctrl after joining the rows of both keys. The
LEDs had to be ignored as well (I will check out what can be done with the
onboard LED of the Pico).

Use the info.json and default keymap as help to find the correct solder joints
for now and **file an issue if you're interested in reproducing this**. I will
be more keen to add the instructions if I know someone out there wants to use
this.

* Keyboard Maintainer: [plan5](https://github.com/plan5)
* Hardware Supported: Raspberry Pi Pico W (and probably non-W Pico)
* Hardware Availability: QPAD MK-50 is out of production but can be found used.

Make example for this keyboard (after setting up your build environment):

    make handwired/qpad-mk50-pico:default

Flashing example for this keyboard:

1. Bring Raspberr Pi Pico (W) into programming mode (hold BOOTSEL button on the
   board to mount as drive.
2. Copy .uf2 image to the mounted drive.
3. Unplug and replug keyboard.
4. For later iterations you can hold Escape while plugging in to enter
   programming mode/bootmagic.

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## Bootloader

Enter the bootloader in 3 ways:

* **Bootmagic reset**: Hold down the key at (0,0) in the matrix (usually the top left key or Escape) and plug in the keyboard
* **Physical reset button**: Briefly press the button on the back of the PCB - some may have pads you must short instead
* **Keycode in layout**: Press the key mapped to `QK_BOOT` if it is available

