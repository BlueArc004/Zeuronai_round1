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

## References

1. https://debian-live-config.readthedocs.io/en/latest/custom.html
2. https://code.visualstudio.com/docs/setup/linux
3. https://gist.github.com/berkorbay/6feda478a00b0432d13f1fc0a50467f1
4. https://support.zoom.com/hc/en/article?id=zm_kb&sysparm_article=KB0063458
