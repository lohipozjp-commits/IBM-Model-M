# IBM Model M custom PCB: ZMK probe package

This package is a temporary probe build for your custom IBM Model M PCB.

What it does:
- treats the board as an 8x16 matrix
- uses the two 74HC595 chips as 16 driven outputs
- uses the 8 direct nRF52840 inputs as rows
- uses an identity matrix transform
- makes every detected key type its matrix coordinate in hex form, e.g. `r0c0`, `r3ca`, `r7cf`

How to use:
1. Start from the ZMK unified module template:
   https://github.com/zmkfirmware/unified-zmk-config-template
2. Drop these files into the matching paths.
3. Push to GitHub and wait for Actions to build.
4. Download the UF2 artifact.
5. Double-click reset on the nice!nano-compatible board so the UF2 drive appears.
6. Copy the UF2 onto the board.
7. Open a plain text editor on the host computer.
8. Press each physical key once and write down the emitted token.

Interpretation:
- `r0`..`r7` correspond to the eight direct input lines in the order listed in `ibm_model_m.overlay`.
- `c0`..`cf` correspond to the sixteen shift-register outputs in the order listed in `col-gpios`.

If you get no output:
- first reverse the 16-entry `col-gpios` order
- if that still fails, try `diode-direction = "row2col"` and swap the input/output arrays

After probing:
- replace the probe keymap with a normal keymap
- replace the identity matrix transform with the final physical-layout transform
