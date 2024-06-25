# Custom Debian ISO with Preinstalled Applications

This repository contains scripts and configuration files to build a custom Debian ISO with GitHub Desktop, Visual Studio Code, Google Chrome, and Zoom preinstalled.

## Requirements

- Debian-based system (e.g., Ubuntu)
- `live-build` and `debootstrap` packages

1. Install Required Packages
    ```bash
    sudo apt update
    sudo apt install -y live-build debootstrap
    ```
2. Preinstall Applications
   1. Github Desktop:
   ```bash
   wget -O github-desktop.deb https://github.com/shiftkey/desktop/releases/download/release-2.9.4-linux1/GitHubDesktop-linux-2.9.4-linux1.deb
   sudo dpkg -i github-desktop.deb
   sudo apt-get install -f
   ```
   2. Visual Studio Code:
   ```bash
   wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
   sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
   sudo apt update
   sudo apt install code
   ```
   3. Chrome:
   ```bash
   wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   sudo dpkg -i google-chrome-stable_current_amd64.deb
   sudo apt-get install -f
   ```
   4. Zoom:
   ```bash
   wget https://zoom.us/client/latest/zoom_amd64.deb
   sudo dpkg -i zoom_amd64.deb
   sudo apt-get install -f
   ```
4. Build the ISO:
   - Setting directory for build config:

    ```bash
    mkdir live-build-config
    cd live-build-config
    lb config
    ```
5. Add packages
   ```bash
   mkdir -p config/package-lists
   echo "code" >> config/package-lists/custom.list.chroot
   echo "google-chrome-stable" >> config/package-lists/custom.list.chroot
   echo "zoom" >> config/package-lists/custom.list.chroot

   ```
   ```bash
   mkdir -p config/packages.chroot
   cp /path/to/github-desktop.deb config/packages.chroot/
   ```

6. Adding in hooks
   ```bash
   mkdir -p config/hooks/normal
   cat <<EOF > config/hooks/normal/install-github-desktop.hook.chroot
   dpkg -i /packages.chroot/github-desktop.deb
   apt-get install -f
   EOF
   ```
   ```bash
    chmod +x config/hooks/normal/install-github-desktop.hook.chroot

    ```
7. Create ISO
   ```bash
   lb build
   ```
   - The file will be created in current Directory
## Installation

Burn the ISO to a USB drive or use it in a virtual machine to install the custom Debian system.

## Verification

1. Boot from the ISO.
2. Verify that GitHub Desktop, Visual Studio Code, Google Chrome, and Zoom are installed and functional.

