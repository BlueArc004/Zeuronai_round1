# Custom Debian ISO with Preinstalled Applications

This repository contains scripts and configuration files to build a custom Debian ISO with GitHub Desktop, Visual Studio Code, Google Chrome, and Zoom preinstalled.

## Requirements

- Debian-based system (e.g., Ubuntu)
- `live-build` and `debootstrap` packages

## Building the Custom ISO

1. Clone this repository:

    ```bash
    git clone https://github.com/BlueArc004/Zeuronai_round1.git
    cd Zeuronai_round1
    ```
    
2. Config ISO:

    ```bash
    sudo lb config
    ```
3. Build the ISO:
   
    ```bash
    sudo lb config
    ```

5. The custom ISO will be created in the current directory.

## Installation

Burn the ISO to a USB drive or use it in a virtual machine to install the custom Debian system.

## Verification

1. Boot from the ISO.
2. Verify that GitHub Desktop, Visual Studio Code, Google Chrome, and Zoom are installed and functional.

