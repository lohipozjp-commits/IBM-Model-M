Use this package to replace the files in your repo root exactly.

Important paths:
- build.yaml
- config/ibm_model_m.conf
- config/ibm_model_m.keymap
- boards/shields/ibm_model_m/Kconfig.shield
- boards/shields/ibm_model_m/Kconfig.defconfig
- boards/shields/ibm_model_m/ibm_model_m.overlay
- boards/shields/ibm_model_m/boards/nice_nano_nrf52840_zmk.overlay

Then:
git add .
git commit -m "replace ibm model m probe package"
git push
