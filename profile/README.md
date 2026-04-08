## Mainline development space for the Samsung Exynos850 SOC

### Go check out famfo's repo too, for A127F! [linux-a127f](https://git.catgirls.systems/famfo/linux-a127f)
### Also see the [postmarketOS wiki for the Samsung Exynos850](https://wiki.postmarketos.org/wiki/Samsung_Exynos_850_(S5E3830))

### Exynos850 devices

Devices with an * next to their name are devices that may be supported in the future.
- Samsung Galaxy A13 (SM-A135F)*
  Note: there is 3GB, 4GB and 6GB ram variants for this phone.
  Anything for this should also support the SM-A135M.
  Currently being worked on.
- Samsung Galaxy M13 (SM-M135F)*
  Note: there is 3GB, 4GB and 6GB ram variants for this phone.
  Yet to see anyone with this phone, so unlikely to be supported.
- Samsung Galaxy F13 (SM-E135F)*
  Note: Never seen anyone owning this, so probably not unless someone steps up.
- Samsung Galaxy A12 Nacho (SM-A127F)*
  Note: there is a 3GB and 4GB ram variant for this phone.
  Famfo is working on this phone.
- Samsung Galaxy M12 (SM-M127F)*
  Note: there is a 3GB and 4GB ram variant for this phone.
  (Kinda) identical to A12 Nacho
- Samsung Galaxy A21s (SM-A217F)*
  Note: there is 3GB, 4GB and 6GB ram variants for this phone.
  Maybe.
- Samsung Galaxy A04s (SM-A047F)
  Note: there is a 3GB and 4GB ram variant for this phone.
- Samsung Galaxy XCover 5 (SM-G525F)
  Note: I've never seen anyone with this, ever.
  Seems cool, so maybe, if I can get a tester.
- Samsung Galaxy A14 4G Exynos (SM-A145F/M)
### Current status (A135F).
- eMMC [X] Driver is probing.
- No graphical output as of now.

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

---

<sub>7.0.0-rc6 :)</sub>
