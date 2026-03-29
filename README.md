# Hackintosh for Asus Vivobook M3504Y
Hackintosh OpenCore for Asus Vivobook M3504Y
# Disclaimer
For macOS to work properly, you need to change the Wifi module to a compatible one, otherwise you won't be able to use Wifi and Bluetooth.
# Screenshots 
![macOS15](https://github.com/jirnobruh/Hackintosh-Asus-Vivobook-M3504Y/blob/main/pictures/AboutMacOS15.png)
# Hardware

| Component         | Model                                                                                       |
| ----------------- | ------------------------------------------------------------------------------------------- |
| Notebook          | Asus Vivobook M3504YA                                                                       |
| CPU               | AMD Ryzen 5 7530u                                                                           |
| iGPU              | AMD Radion Vega 7 (Radeon RX Graphics 512 МБ)                                               |
| Audio             | Realtek                                                                                     |
| Wi-Fi + Bluetooth | Intel AX210NGW (Initially, there was a Mediatek MT7902 network card)                        |
| RAM               | 16gb DDR4 3200MHz                                                                           |
| SSD               | Samsung 970 EVO 1tb (Initially, there was a Micron at 512gb, but for my purposes I set 1tb) |
# Work / Not work

| Component            | Status                                                                                                                                                                                   |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AMD Radion Vega 7    | ⚠️ Metal support, but for Chromium and Electron (I test Discord and Obsidian) applications, need to disable hardware acceleration, otherwise they work unstable / crash the system.      |
| Audio VoodooHDA      | ❌ At the moment, the built-in speakers could not be started, jack 3.5 does not work either.<br>✅ If use a USB sound card or an adapter from USB (USB-c) to jack 3.5, the sound is output |
| Microphone VoodooHDA | ❌ Don't work<br>✅ If use USB sound card or an adapter from USB (USB-c) to jack 3.5                                                                                                       |
| Audio AppleALC       | Dont test                                                                                                                                                                                |
| Microphone AppleALC  | Dont test                                                                                                                                                                                |
| Wi-FI                | ✅ Itlwm kext work                                                                                                                                                                        |
| Bluetooth            | ✅ Working, it sees devices in the area, but I hasn't checked their functionality.                                                                                                        |
| USB ports            | ✅ (but i dont check his version work)                                                                                                                                                    |
| PowerDelivery        | ✅                                                                                                                                                                                        |
| Power Safe Mode      | ✅ macOS 15 <br>⚠️ macOS 26: is sometimes disabled                                                                                                                                        |
| Integrated Webcam    | ✅                                                                                                                                                                                        |
# Problems
- Chromium / Electron / Web applications need to disable hardware acceleration
	- Discord crash system
	- Obsidian works fine, but any pop-up window on top (such as the SlashCommander plugin) causes the application to crash
	- Telegram works fine, but you can't view any photos or videos
	- Voodoo audio kext makes the speakers squeak 
# How create OpenCore?
I was creating an OpenCore bootloader in Windows 11 using [OpCore-Simplify](https://github.com/lzhoang2801/OpCore-Simplify) everything is working fine, so I won't throw my loader yet. 
The only thing I had to change myself was that sometimes the loader lost some kext. Fixed it using Gemini by sending him config.plist
# Which macOS are running?
I have tested 2 versions of macOS:
1) macOS 26.3.2 Tahoe
2) macOS 15.7.4

I settled on macOS 15 because of the more stable operation and the old design I used to work on.
If you want to install macOS 26, be prepared to drain your battery faster than on macOS 15.
# Triple boot (Windows + Linux + macOS)
I'm using a triple boot on my laptop - Windows 11 + ZorinOS 18 + macOS 15. At the time of writing, OpenCore sees all three systems, but I still want Grub to start initially, or add a button to exit to UEFI, because even with Fast boot turned off, the laptop doesn't enter UEFI when I press the del button.
