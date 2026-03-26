This is a minimal ZMK shield whose only purpose is to boot an application and
define an ext-power node with GPIO0.13 active-high.

Important:
- There is intentionally NO boards/nice_nano.overlay file in this package.
- This avoids the previous parse error caused by trying to patch /ext-power.
- The package uses zmk,kscan-mock per the dongle guide.
