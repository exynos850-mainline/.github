## Mainline development space for the Samsung Exynos850 SOC

### Also see: https://github.com/samsungexynos850/linux , development will also be occuring there
### Also see the [Nura wiki for the Samsung Exynos850](https://wiki.nura.eco/wiki/Samsung_Exynos_850)
### and the [wiki for the Samsung Galaxy a13](https://wiki.nura.eco/wiki/Samsung_Galaxy_A13_(samsung-a13))
### Exynos850 devices

If you would like a device supported, you will need to be able to test and be competent.
You may contact me via email at: superaviation001@gmail.com
  
### Current status (A135F).
- Booting.
- eMMC - working
- Framebuffer output - working
- USB - working/partial
- touchscreen - working
- 3d accel - working
- PMIC - working
- Modem - WIP
  
### Info about the Exynos 850

####  Exynos 850 Boot Flow
![Exynos 850 boot sequence](https://docs.u-boot.org/en/latest/_images/exynos850-boot-architecture.svg)
- Refer to https://docs.u-boot.org/en/latest/board/samsung/e850-96.html for abit more info about this

On a “power-on” event, the processor starts executing code at address 0x00000000 where the internal ROM (iROM) is mapped. iROM contains the Boot ROM code (BL0). All other bootloaders are stored in external storage (usually eMMC), so the user can update those later.

By default the board is configured to boot from eMMC. On power-on, the Boot ROM code (BL0) jumps to the beginning of eMMC boot partition 0 (mmc0boot0) where BL1 must reside. The boot flow then progresses through multiple various bootloaders (as shown in Figure 1), eventually ending up executing U-Boot (designated as “Bootloader” in the figure).

The Exynos850 has some support for custom operating systems, with postmarketOS being in development for the Galaxy A13 and A12 Nacho. The Galaxy A12 Nacho, Galaxy A13 and Galaxy A21s have all had/currently have support for a custom operating system, either an Android Custom ROM or linux. The A12 Nacho is currently WIP in getting a mainline kernel port, along with the A13.

It is also useful to mention the Winlink E850-96 board based on the Exynos850, which has very well documented support in the mainline kernel, and quite a lot of code available for it, being available at Linaro's git.
The WinLink E850-96 board is also implemented in the mainline Linux kernel and U-Boot.

Currently, the Samsung Galaxy A12 Nacho is implemented in uniLoader, a secondary bootloader used for a variety of purposes. The Samsung Galaxy A13 is WIP in a fork.

- Credits: [U-Boot Docs](https://docs.u-boot.org/en/latest/board/samsung/e850-96.html)

### Credits
- famfo, base device tree for a127f, which i based my a135f device tree on,
  whole reason i started this
- ivoszbg, for uniLoader, wouldnt boot without it
- halal-beef, botchedrpr and the exynos990-mainline team, where i got reference from
- everyone else who helped me gather info

#### Currently working on the following:

- exynos850-mainline, right here
- postmarketOS (mainline WIP)

### Go check out Thomas’s a21s repo [linux](https://github.com/samsungexynos850/linux)
---

<sub>7.3 :)</sub>
