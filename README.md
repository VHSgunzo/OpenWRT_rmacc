# RMACC

## Features:
```
* WI-FI RANDOM MAC ADDRESS CHANGER 
```
## Supports:
```
All OpenWRT-based distributions
```
## To get started:
* **Download the latest revision**
```
git clone https://github.com/VHSgunzo/OpenWRT_rmacc.git
```
* **Follow instruction**
```
cd OpenWRT_rmacc
scp rmacc root@192.168.1.1:/bin/rmacc
chmod +x /bin/rmacc
scp soft root@192.168.1.1:~/soft
ssh root@192.168.1.1
opkg update
opkg install $(cat soft)
rm -rf /etc/config/wireless
wifi config
wifi down
wifi up
uci set wireless.@wifi-device[0].disabled=0
uci commit
```
* **Open in your browser: http://192.168.1.1/cgi-bin/luci/admin/network/wireless**
```
radio0 > Scan > Choise and add Wi-Fi AC > Save
Don't forget set "wlan0" in Network and ifconfig name
```
* **And next**
```
ssh root@192.168.1.1
rmacc start
reboot
```
## USAGE:
```
OpenWRT WI-FI MAC ADDRESS CHANGER
        Usage:
        ┌──[root@OpenWrt]─[/root]
        └──╼ $ rmacc {start|stop|restart|reload}

         start   - Change WI-FI MAC address
         stop    - Reset to original WI-FI MAC address
         restart - NEW WI-FI MAC address
         reload  - Reload OpenWRT WI-FI network
```
