---
title: "Welcome to my blog"
date: 2024-12-26
---

using wpa_supplicant

    $ip a
    $ sudo iwlist wlan0 scan | grep -i ssid
    $ sudo wpa_passphrase networkname password | sudo tee /etc/wpa_supplicant/wpa_supplicant.conf

    ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=wheel
   
    scan_ssid=1  # if ssid is hidden
   
    proto=RSN
   key_mgmt=WPA-PSK
   
   group=CCMP
   pairwise=CCMP
   
   priority=10

---
using nmcli

    nmcli device wifi list
    nmcli device wifi connect ‘CoffeeShopWifi‘ password ‘wifi1234‘
    nmcli connection show --active

---
direct edit system files

   sudo apt install wpasupplicant 
   sudo nano /etc/network/interfaces

    auto wlp3s0
    iface wlp3s0 inet dhcp  
        wpa-ssid "JohnSmithGuest"
        wpa-psk "wifi_password"

    sudo service networking restart
