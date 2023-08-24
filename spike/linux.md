

```




[1469516.510636] usb 3-5: new full-speed USB device number 66 using xhci_hcd
[1469516.669077] usb 3-5: New USB device found, idVendor=0694, idProduct=0009, bcdDevice= 2.00
[1469516.669088] usb 3-5: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[1469516.669093] usb 3-5: Product: SPIKE Prime VCP
[1469516.669097] usb 3-5: Manufacturer: LEGO System A/S
[1469516.669099] usb 3-5: SerialNumber: 206A38525746
[1469516.673302] cdc_acm 3-5:1.0: ttyACM0: USB ACM device



```

```
/etc/udev/rules.d/50-myusb.rules
=================================
KERNEL=="ttyACM0",MODE="0666"

```

```
sudo udevadm control --reload-rules && sudo service udev restart && sudo udevadm trigger
```


## run

* minicom -wD /dev/ttyACM0