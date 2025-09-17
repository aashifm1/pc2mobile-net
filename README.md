# Internet from PC (ethernet) to Mobile - Reverse Tethering

### **Method 1: Easy way with `gnirehtet` (recommended)**

`gnirehtet` is an open-source tool by Genymobile (makers of `scrcpy`). It uses **ADB** to tunnel internet from your PC to your phone over USB.

1. Install ADB:

   ```bash
   sudo apt install adb
   ```
2. Download `gnirehtet`:

   ```bash
   wget https://github.com/Genymobile/gnirehtet/releases/download/v2.5/gnirehtet-rust-linux64-v2.5.zip
   unzip gnirehtet-rust-linux64-v2.5.zip
   cd gnirehtet-rust-linux64
   ```
3. Enable **USB debugging** on your phone (Developer Options → USB debugging).
4. Start reverse tethering:

   ```bash
   ./gnirehtet run
   ```

   Your phone will prompt for VPN permission → accept.
   ✅ Now your phone should use your PC’s internet.


### **Method 2: Manual (iptables + dnsmasq)**

This only works if your phone exposes itself as a USB network card (RNDIS). But in your case, it’s not showing up (`enx...` gone), so Method 1 is more reliable.

⚡ Recommendation: Use **gnirehtet** — it works on all Android phones without special drivers.
