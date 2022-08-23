# Raspberry Pi Usage
## SSH
1. power up rpi by supplying voltage through usb
2. connect wifi signaled by rpi (wifi-name: `MDPGrp16`)
	- Passphrase: `2022Grp16`
	- *No need other cables*
1. ssh to `pi@192.168.16.1`
	- passphrase: `raspberry`

## Communication with STM32
> The given usb cable is malfunctioning (I use my own cable instead)
> - check usb integrity : `lsusb`  should seed the UART usb bridge

To enable **Linux** communication we need to
- `sudo systemctl start serial-getty@ttyUSB0.service`

Use **python** program to access (`pyserial` lib)
- we have to **stop** the `ttyUSB0.service`

Need to change mod after enable/disable, start/stop a service
- `sudo chmod 777 /dev/ttyUSB0`
