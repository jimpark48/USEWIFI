# USBWIFI

+ Backup USB wifi package files.
+ Because previous thing is not compatible with our PCs


## How to set up USB WIFI module

+ Check module name of WIFI LAN card
    
    ```bash
    $ lsusb
    
    Bus 001 Device 005: ID 0bda:b831 Realtek Semiconductor Corp.
    ```
    
+ Install build environment
    
    ```bash
    $ sudo apt update
    $ sudo apt install -y build-essential dkms git linux-headers-$(uname -r)
    ```
    
+ Download source files of compatible driver for WIFI LAN card
    + Or, use this backup package files 
    
    ```bash
    $ cd ~
    $ git clone https://github.com/heesn/rtl8831.git
    $ cd rtl8831
    ```
    
+ Install LAN card driver
    
    ```bash
    $ cd ~/rtl8831
    $ sudo dkms install .
    
    # If it has error, then follow below!!!
    $ cd ~/rtl8831
    $ make && sudo make install

    # If second method has error, then follow below!!!
    $ dkms status
    $ sudo dkms remove rtl8851bu/0.2 --all
    $ sudo dkms install .
    ```
    
+ After install, reboot
    
    ```bash
    $ sudo reboot now
    ```
