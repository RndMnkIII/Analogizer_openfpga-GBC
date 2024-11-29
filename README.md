# Gameboy/Game Boy Color for Analogue Pocket Core with support for Analogizer-FPGA adapter
* Analogizer V1.0.0 [26/11/2024]: Added initial support for Analogizer adapter (RGBS, RGsB, YPbPr, Y/C, SVGA Scandoubler) and SNAC (included PSX DS/DS2). The PSX DS/DS2
  can be used in **Digital DPAD** mode (ignores the analog sticks, regardless of the ANALOG button setting on the controller) or in **Analog DPAD** mode (left analog stick is mapped to DPAD movements)
* Analogizer V1.0.1 [29/11/2024]: When the 'Analog Wide' option is on and the core is working in GBC mode the Pocket screen will blank out to avoid video glitches.

Adapted to Analogizer by [@RndMnkIII](https://github.com/RndMnkIII) based on **budude2** Gameboy/Game Boy Color for Analogue Pocket (https://github.com/budude2/openfpga-GBC).
The core can output RGBS, RGsB, YPbPr, Y/C and SVGA scandoubler(0%, 25%, 50% 75% scanlines and HQ2x) video signals. 
This core has an additional **```Analog Wide```** setting which allows to increase the horizontal size of the image on the CRT/SVGA monitor.

| Video output | Status | SOG Switch(Only R2,R3 Analogizer) |
| :----------- | :----: | :-------------------------------: |     
| RGBS         |  ✅    |     Off                           |
| RGsB         |  ✅    |     On                            |
| YPbPr        |  ✅🔹  |     On                            |
| Y/C NTSC     |  ✅    |     Off                           |
| Y/C PAL      |  ✅    |     Off                           |
| Scandoubler  |  ✅    |     Off                           |

🔹 Tested with Sony PVM-9044D

| :video_game:            | Analogizer A/B config Switch | Status |
| :---------------------- | :--------------------------- | :----: |
| DB15                    | A                            |  ✅    |
| NES                     | A                            |  ✅    |
| SNES                    | A                            |  ✅    |
| PCENGINE                | A                            |  ✅    |
| PCE MULTITAP            | A                            |  ✅    |
| PSX DS/DS2 Digital DPAD | B                            |  ✅    |
| PSX DS/DS2 Analog  DPAD | B                            |  ✅    |

The Analogizer interface allow to mix game inputs from compatible SNAC gamepads supported by Analogizer (DB15 Neogeo, NES, SNES, PCEngine, PSX) with Analogue Pocket built-in controls or from Dock USB or wireless supported controllers (Analogue support).

All Analogizer adapter versions (v1, v2 and v3) has a side slide switch labeled as 'A B' that must be configured based on the used SNAC game controller.
For example for use it with PSX Dual Shock or Dual Shock 2 native gamepad you must position the switch lever on the B side position. For the remaining
game controllers you must switch the lever on the A side position. 
Be careful when handling this switch. Use something with a thin, flat tip such as a precision screwdriver with a 2.0mm flat blade for example. Place the tip on the switch lever and press gently until it slides into the desired position:
```
     ---
   B|O  |A  A/B switch on position B
     ---   
     ---
   B|  O|A  A/B switch on position A
     ---
``` 

The following options exist in the core menu to configure Analogizer:
* **Analog Wide (Only CRT)** Check: Enable/Disable (this will freeze the Pocket screen in GBC mode, to avoid screen tearing).
* **SNAC Adapter** List: None, DB15,NES,SNES,PCE,PCE Multitap, SNES swap A,B<->X,Y buttons, PSX (Digital DPAD), PSX (Analog DPAD).
* **SNAC Controller Assignment** List: several options about how to map SNAC controllers to P1-P4 Pocket controls. The controls not mapped to SNAC by default will map to Pocket connected controllers (Pocket built-in or Dock).
* **Analogizer Video Out** List: you can choose between RGBS (VGA to SCART), RGsB (works is a PVM as YPbPr but using RGB color space), YPbPr (for TV with component video input),
Y/C NTSC or PAL (for SVideo o compositive video using Y/C Active adapter by Mike S11), RGBHV for SVGA monitor Scandouble video output.

-----------------------------------------------------------------------------------------------------
# Gameboy/Game Boy Color for Analogue Pocket
Ported from the original core developed at https://github.com/MiSTer-devel/Gameboy_MiSTer

Please report any issues encountered to this repo. Issues will be upstreamed as necessary.

## Installation
To install the core, copy the `Assets`, `Cores`, and `Platform` folders over to the root of your SD card. Please note that Finder on macOS automatically _replaces_ folders, rather than merging them like Windows does, so you have to manually merge the folders.

Place the GBC bios in `/Assets/gbc/common` named "gbc_bios.bin", the GB bios in `/Assets/gb/common` named "gb_bios.bin", and the SGB bios in `/Assets/gb/common` named "sgb_boot.bin".


## Usage
ROMs should be placed in `/Assets/gbc/common`, and `/Assets/gb/common`

## Features

### Supported
* Real-Time Clock
* Fastforward
* Original Gameboy display modes
* Super Gameboy Emulation
* Custom Borders (SGB)
* Custom Palettes (SGB)
* Enhance GBA features
* Save States and Sleep

### In Progress
¯\\_(ツ)_/¯
