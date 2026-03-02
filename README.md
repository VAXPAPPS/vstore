# Vstore

Vstore is the official graphical software center for VAXP-OS. It provides a beautiful, fast, and lightweight interface to find, install, and manage applications and system updates.

Based on a heavily customized fork of GNOME Software, Vstore has been deeply radically optimized to match the VAXP-OS philosophy: elegant aesthetics and zero background bloat.

## ✨ Features

- **VAXP Glassmorphism UI**: A stunning, modern interface featuring a transparent header bar, seamless rounded corners, and dynamic hover micro-animations tailored for VAXP-OS.
- **Zero-Daemon Architecture**: Unlike other software centers that hide in the background and consume RAM, Vstore is engineered to **completely terminate** and free all memory the moment you click the close (X) button.
- **Debloated & Streamlined**: Thoroughly purged of unnecessary upstream bloat, including `malcontent` (parental controls), `eos-updater`, and hardcoded proprietary web apps.
- **Comprehensive App Management**: Seamlessly browse, install, and manage applications using PackageKit and Flatpak.
- **System Updates**: Easily apply system upgrades and firmware updates.
- **Beautiful App Pages**: Transparent image carousels, detailed descriptions, and user ratings.

## 🛠️ Build Dependencies

To build Vstore from source, you will need the following development packages installed on your system (Debian/Ubuntu-based package names):

```bash
sudo apt install \
    meson \
    ninja-build \
    pkg-config \
    libgtk-4-dev \
    libadwaita-1-dev \
    libglib2.0-dev \
    libjson-glib-dev \
    libappstream-dev \
    libpackagekit-glib2-dev \
    libpolkit-gobject-1-dev \
    libsoup-3.0-dev \
    libflatpak-dev \
    libostree-dev \
    libxmlb-dev \
    gettext \
    gsettings-desktop-schemas-dev \
    desktop-file-utils \
    appstream
```
*(Note: Some dependencies like `flaptak` or `fwupd` may be optional depending on your meson configuration, but are generally recommended for full functionality).*

## 🚀 Building and Installation

Vstore uses the `meson` build system. Follow these steps to build and install the application:

1. **Clone the repository and enter the directory (if you haven't already):**
   ```bash
   cd Vstore/vstore
   ```

2. **Configure the build directory:**
   ```bash
   meson setup build
   ```

3. **Compile the project:**
   ```bash
   ninja -C build
   ```

4. **Install the application (requires root privileges):**
   ```bash
   sudo ninja install -C build
   ```

5. **Run the store:**
   ```bash
   vstore
   ```

## 🧹 Purging the Build Directory
If you want to reconfigure the build completely from scratch:
```bash
sudo rm -rf build
meson setup build
```
