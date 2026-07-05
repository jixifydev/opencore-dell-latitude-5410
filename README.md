# OpenCore EFI Package for Dell Latitude 5410

:warning: **DISCLAIMER:**
This is not a guide, please refer to [Dortania](https://dortania.github.io/getting-started/) before doing anything. I am not responsible for any damage. This OpenCore configuration is optimized for my specific hardware, so please use it only as a reference or if you happen to have the same or similar hardware.

## :white_check_mark: Working:

- [x] CPU power management.
- [x] Graphics acceleration.
- [x] Battery read-out.
- [x] Wi-Fi.
- [x] Bluetooth.
- [x] USB ports.
- [x] Card Reader.
- [x] HDMI and DP(USB-C) video & audio output.
- [x] Ethernet.
- [x] Audio (Internal speakers, 3.5mm headphone jack).
- [x] Internal microphone.
- [x] 720p WebCam.
- [x] AirDrop & Handoff. (only from MacOS to iPhone, not vice versa)
- [x] iCloud & App Store.
- [x] iMessage & FaceTime.
- [x] Trackpad with all macOS gestures.
- [x] Keyboard (The cursor sometimes jumps when pressing a key for a longer period of time or even during simple typing)

## :x: Not working:

--

## ⚠️ **Hidden BIOS Settings (modGRUBShell Required)**

This EFI doesn’t enable `AppleXcpmCfgLock`, `framebuffer-fbmem`, or `framebuffer-stolenmem`. Use **modGRUBShell.efi**:

1. **Disable CFG Lock**

   ```
   setup_var_cv CpuSetup 0x3E 0x1 0x0
   ```

2. **Set DVMT Pre-Allocated to 64MB**

   ```
   setup_var_cv SaSetup 0xF5 0x1 0x2
   ```

3. **Set DVMT Total GFX Memory to Max (Optional)**

   ```
   setup_var_cv SaSetup 0xF6 0x1 0x3
   ```

---


---

## ⚠️ **CPU Performance Guide (no Throttling)**

Download the Voltageshifter1.25.

1. **Setting the perfect Min / Max Watt**

   ```
   sudo ./voltageshift power 15 25
   ```

2. **Make it permanent upon restarts**

   ```
   sudo ./voltageshift buildlaunchd 0 0 0 0 0 0 1 15 25 1 20
   ```

---

