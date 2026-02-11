# Padavan 3.4 - The "Dave Täht Tribute" Edition

> "When you miss Dave, modprobe sch_cake!"
> — A tribute to the soul of bufferbloat mitigation.

---

## 🕊️ In Loving Memory of Dave Täht

### "穿越時空的夢想，我來幫他實現！"
(Making a time-traveling dream come true!)

This project is dedicated to Dave Täht, a visionary whose work on FQ-CoDel, CAKE, and LibreQoS changed the internet forever. We are fulfilling a wish he made 5 years ago on Reddit:

### ❝ Help port the code to more chipsets. ❞

> The BEST engineering result I ever had:
> Essentially the summation of my 16+ years of work to that point on making wifi better. Unpatented. Please share and enjoy.
> **Help port the code to more chipsets.**
>
> — Dave Täht (Reddit, 5 years ago)

Original Source: [Reddit - r/Starlink](https://www.reddit.com/r/Starlink/comments/okmx3x/comment/h61unnn/)

Dave turned down numerous lucrative contracts to keep his code Free and Open Source. He valued global impact over prestige. Because of him, millions of devices—from Starlink satellites to rural ISP routers—deliver smoother connectivity, enabling telemedicine, education, and connection for the underserved.

May his soul find eternal peace, and his spirit live on forever in our routers.

[👉 Read the full Memorial at LibreQoS](https://libreqos.io/2025/04/01/in-loving-memory-of-dave/)

---

## 🌟 Project Philosophy: Open & Accessible

### 「永遠保持開放且開源的精神」
(Forever maintaining an open and open-source spirit)

This repository is based on the stable `padavan-ng` with **Linux 3.4 kernel**. We believe in giving power back to the user while honoring the giants who paved the way.

1.  **CAKE Integration**: By default, we aim to support the `sch_cake` module (backported to 3.4) to honor Dave's legacy.
2.  **Easy Multi-Model Support**: Support for a massive range of legacy devices, keeping them alive and fast.
3.  **Flexible Language System**:
    * English Base: The firmware defaults to a clean, English-only interface.
    * Custom Language Packs: You can select one additional language (Traditional Chinese, Russian, etc.) during the build process to keep the firmware lightweight yet localized.

---

## 🗣️ Tributes from the Community
"Dave’s impact on society was immense... He wanted, ultimately, to speed up the internet so that a drummer in London could play in real-time with a guitarist in Los Angeles."
— Steven J. Vaughan-Nichols

"I will miss him but will be always grateful to have known him."
— Vint Cerf

"Without him, Netflix and similar services might still be plagued by glitches and stutters."
— Eric S. Raymond

See also:

[LibreQoS Project](https://libreqos.io/)

[LibreQoS Github Project](https://github.com/LibreQoE/LibreQoS/)

[Dave's Talks: Reducing Network Latency (GOTO 2024)](https://www.youtube.com/watch?v=UDo9W4tt69c)

![Dave Täht Tribute](https://i0.wp.com/libreqos.io/wp-content/uploads/2025/04/WISPAPALOOZA-2024_6.jpg)
*[Image Credit: LibreQoS]*

---

## 🚀 Supported Devices (Kernel 3.4)

We support a vast array of MT7620/MT7621 devices. Pick the one you love!

| Brand | Models (Examples) |
| :--- | :--- |
| **Xiaomi** | MI-3, MI-4, MI-MINI, MI-NANO, MI-R3G (v1/v2), R2100 |
| **ASUS** | RT-N56U, RT-N14U, RT-AC1200, RT-AC51U, RT-N11P |
| **TP-Link** | TL-WR840N/841N (multiple versions), TL-C20, TL-C50, TL-MR series |
| **ZyXEL** | Keenetic series (Giga III, Ultra II, Extra, Lite, Omni, Viva) |
| **D-Link** | DIR-882, DIR-878, DIR-860L, DIR-620 |
| **Others** | Newifi (D1/D2/Mini), Phicomm (PSG1218), Totolink (A3004NS), Ubiquiti (ER-X) |
| **And many more** | 5K, Belkin, GL.iNet, HiWiFi, Linksys, Youku, ZTE... |

---

## ✨ Features (3.4 Edition)

* **Kernel**: Highly optimized Linux 3.4.x (Padavan-NG foundation).
* **Performance & Queue Management**:
    * **CAKE / FQ_CoDel** (The Dave Täht Special) - Backported to 3.4 to mitigate bufferbloat on older devices!
    * Hardware NAT (PPE) support for gigabit speeds.
* **Wireless**: Optimized drivers for MT7603/MT7612/MT7620/MT7628.
* **Network**:
    * IPv6 support.
    * WireGuard support.
    * Hardware flow offloading.
* **Control**: LED & GPIO control via sysfs.

---

## 🛠️ Compilation Guide

We support both **GitHub Actions** (for ease of use) and **Manual Compilation**.

### Option A: GitHub Actions (Recommended)

Just go to the `Actions` tab in this repository, select `Build firmware (Ultimate Fix)`, and choose:

1.  Target Model: (e.g., `TL_C2-V1`, `MI-MINI`, `RT-N56U`...)
2.  Language: (e.g., `English_Only` or `CN (繁體中文)`)
3.  Toolchain: (Default or Padavan-NG)

The system will automatically apply the **CAKE Patch**, configure your language, and build your firmware.

### Option B: Manual Compilation

#### Please see the original part of readme below!

---

Original readme below

# README #

Welcome to the padavan-ng project

This project aims to improve the supported devices on the software part, allowing power user to take full control over their hardware.
This project was created in hope to be useful, but comes without warranty or support. Installing it will probably void your warranty.
Contributors of this project are not responsible for what happens next. Flash at your own risk!

### Contribution ###

Feel free to send in improvements/fixes. I'll keep the issue/pull request system open for that purpose.
NOTE: if and when a possible interesting change will get added depends on a verification/test of the particular change and if i have time to do it.

### Compilation Instructions ###

* Install dependencies

```shell
# I recommend building only on OS: Ubuntu Desktop 22.04.4 LTS (Jammy Jellyfish) and Before building the firmware, select "App Updates" and install them. Next, update the packages
sudo apt update
sudo apt upgrade
sudo apt install autoconf autoconf-archive automake autopoint bison build-essential ca-certificates cmake cpio curl dos2unix doxygen fakeroot flex gawk gettext git gperf help2man htop kmod libarchive-tools libblkid-dev libc-ares-dev libcurl4-openssl-dev libdevmapper-dev libev-dev libevent-dev libexif-dev libflac-dev libgmp3-dev libid3tag0-dev libidn2-dev libjpeg-dev libkeyutils-dev libltdl-dev libmpc-dev libmpfr-dev libncurses5-dev libogg-dev libsqlite3-dev libssl-dev libsystemd-dev libtool libtool-bin libudev-dev libunbound-dev libvorbis-dev libxml2-dev locales mc nano pkg-config ppp-dev python3 python3-docutils sshpass texinfo unzip uuid uuid-dev vim wget xxd zlib1g-dev

```
[Automatic Padavan firmware builds using GitHub servers](https://github.com/shvchk/padavan-builder-workflow)

[Автоматическая сборка прошивки Padavan на серверах GitHub](https://github.com/shvchk/padavan-builder-workflow/blob/main/README.ru.md)

### Firmware management ###
```shell 
Login details
IP: 192.168.1.1 or http://my.router
User: admin
Password: admin
WiFi name 2.4GHz: Padavan_2.4GHz
WiFi name 5GHz: Padavan_5GHz
WiFi Password 2.4/5GHz: 1234567890
```
# Для желающих поддержать проект #

Чтобы выразить благодарность и поддержать мою работу:

ЮMoney кошелёк 4100118647832050

Ссылка для быстрого пополнения https://yoomoney.ru/to/4100118647832050

ЮMoney виртуальная карта 5599 0020 6991 1404

Виртуальная карта Приват Банка гривна: 5169 3600 0910 4443

Виртуальная карта Приват Банка USD: 5169 3600 0910 4385

Большое спасибо вам за вашу поддержку!

Желаю всем добра, а так же Здоровья! Вы даёте мне возможоность жить и дышать! © by Sergey Hadzhioglu

# For those who want to support the project #

To express gratitude and support my work:

ЮMoney wallet 4100118647832050

Link for quick replenishment https://yoomoney.ru/to/4100118647832050

ЮMoney Virtual Card 5599 0020 6991 1404

Virtual Card Privat Bank UAH: 5169 3600 0910 4443

Virtual Card Privat Bank USD: 5169 3600 0910 4385

Thank you very much for your support!

I wish you all the best, and also Health! You give me the opportunity to live and breathe! © by Sergey Hadzhioglu

<a href="https://imgbb.com/"><img src="https://i.ibb.co/4KRbrfM/maxresdefault.jpg" alt="maxresdefault" border="0"></a>

# DISCLAIMER #
IMPORTANT NOTE!! PLEASE READ IT CAREFULLY!!
# NO WARRANTY OR SUPPORT
This product includes copyrighted third-party software licensed under the terms of the GNU General Public License. Please see The GNU General Public License for the exact terms
and conditions of this license. The firmware or any other product designed or produced by this project may contain in whole or in part pre-release, untested, or not fully tested works.
This may contain errors that could cause failures or loss of data, and may be incomplete or contain inaccuracies. You expressly acknowledge and agree that use of software or any part,
produced by this project, is at Your sole and entire risk.

ANY PRODUCT IS PROVIDED 'AS IS' AND WITHOUT WARRANTY, UPGRADES OR SUPPORT OF ANY KIND. ALL CONTRIBUTORS EXPRESSLY DISCLAIM ALL WARRANTIES AND/OR CONDITIONS, EXPRESS OR IMPLIED,
INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES AND/OR CONDITIONS OF SATISFACTORY QUALITY, OF FITNESS FOR A PARTICULAR PURPOSE, OF ACCURACY, OF QUIET ENJOYMENT, AND NONINFRINGEMENT
OF THIRD PARTY RIGHTS.
