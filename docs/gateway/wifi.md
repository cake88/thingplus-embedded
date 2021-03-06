## wifi setup

### Set ssid and password for wan0 and wan1

/etc/network/interfaces.d/wlan.cfg

```
# WiFi Example
auto wlan0
allow-hotplug wlan0
iface wlan0 inet dhcp
    wpa-ssid "ssid"
    wpa-psk  "password"

auto wlan1
allow-hotplug wlan1
iface wlan1 inet dhcp
    wpa-ssid "ssid"
    wpa-psk  "password"
```

### Using more than two dongles

if more than two dongles were used, remove their entries in the below file

/etc/udev/rules.d/70-persistent-net.rules

```
# Auto generated by RootStock-NG: setup_sdcard.sh
# udevadm info -q all -p /sys/class/net/eth0 --attribute-walk

# BeagleBone: net device ()
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="eth*", NAME="eth0"


# USB device 0x:0x (rt2800usb)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="c8:3a:35:c4:36:8a", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="wlan*", NAME="wlan0"
```
