# LVGL ESP32 ST7789 Build

Este repositorio permite compilar firmware de MicroPython con soporte para LVGL y pantallas ST7789 sobre ESP32.

## Uso

1. Haz Fork del repositorio.
2. Ve a la pestaña **Actions** y ejecuta **Run Workflow**.
3. Una vez completado, descarga el binario desde **Artifacts**.
4. Flashea el dispositivo con:

```bash
esptool.py --chip esp32 --port COM3 --baud 460800 write_flash -z \
  0x1000 bootloader.bin \
  0x8000 partition-table.bin \
  0x10000 firmware.bin
```

## Requisitos

- ESP32 con soporte SPIRAM (JC2432W328N compatible)
- Pantalla ST7789 conectada por SPI
