## Welcome, this is where linux and AOSP is developed for the Galaxy A13 Exynos variants.

![The Samsung Galaxy A13 (Exynos) is built on the Exynos850 Chipset.](https://www.businesskorea.co.kr/news/photo/202204/91014_105252_4128.png)

### General information - Galaxy A13

**Seperate to the Samsung Galaxy M13 and F13. Also seperate to the A137F**

The Samsung Galaxy A13 **Exynos** is a budget Android smartphone made by Samsung. The 4G Exynos variant was released on the 4th of March 2022, running One UI 4.1 (Android 12), being upgradable to One UI 6.1 (Android 14). Despite this being a modern smartphone, Samsung chose to restrict it to a 32bit system, which can be bypassed via a custom rom or port of some sorts. This device has ram options from 3-6GB, and storage options from 32-128GB, with an eMMC 5.1 storage being present in the phone.

The 4G variant has a quad camera setup, including a 50MP wide-angle, 5MP ultrawide angle, 2MP macro and 2MP depth sensor. The main camera however has a true resolution of 12.5MP. The front camera has a resolution of 8MP and an aperture of f/2.2 (wide). Both the main and front cameras are capable of recording videos in 1080p@30fps resolution.

- Credits: [Wikipedia](https://en.wikipedia.org/wiki/Samsung_Galaxy_A13)

### Info about the Exynos 850

####  Exynos 850 Boot Flow
![Exynos 850 boot sequence]([(https://docs.u-boot.org/en/latest/_images/exynos850-boot-architecture.svg)])
- Refer to https://docs.u-boot.org/en/latest/board/samsung/e850-96.html for abit more info about this

On a “power-on” event, the processor starts executing code at address 0x00000000 where the internal ROM (iROM) is mapped. iROM contains the Boot ROM code (BL0). All other bootloaders are stored in external storage (usually eMMC), so the user can update those later.

By default the board is configured to boot from eMMC. On power-on, the Boot ROM code (BL0) jumps to the beginning of eMMC boot partition 0 (mmc0boot0) where BL1 must reside. The boot flow then progresses through multiple various bootloaders (as shown in Figure 1), eventually ending up executing U-Boot (designated as “Bootloader” in the figure).

The Exynos850 has some support for custom operating systems, with postmarketOS being in development for the Galaxy A13 and A12 Nacho. The Galaxy A12 Nacho, Galaxy A13 and Galaxy A21s have all had/currently have support for a custom operating system, either an Android Custom ROM or postmarketOS (Only for Galaxy A13 as of 03/04/26). The A12 Nacho is currently WIP in getting a mainline kernel port, along with the A13.

It is also useful to mention the Winlink E850-96 board based on the Exynos850, which has very well documented support in the mainline kernel, and quite a lot of code available for it, being available at Linaro's git.
The WinLink E850-96 board is also implemented in the mainline Linux kernel and U-Boot.

Currently, the Samsung Galaxy A12 Nacho is implemented in UniLoader, a secondary bootloader used for a variety of purposes. The Samsung Galaxy A13 is WIP in a fork.

- Credits: [U-Boot Docs](https://docs.u-boot.org/en/latest/board/samsung/e850-96.html)

---

<sub>postmarketOS close-to-booting on A13 :)</sub>
