# ws2000_NX8_linux
I was having a problem where linux was mixing the inputs of 2 axes for a Spektrum ws2000 and Realflight would not read all 8 channels correctly because of this.


This is a smiple fix for realflight.

Add the flie
sudo nano /etc/udev/hwdb.d/71-spektrum-buttons.hwdb
with the following

# Spektrum Receiver - disable duplicate button events
evdev:input:b0003v0483p*
 KEYBOARD_KEY_90001=reserved
 KEYBOARD_KEY_90002=reserved
 KEYBOARD_KEY_90003=reserved



 then

sudo systemd-hwdb update
sudo udevadm trigger


unplug and replug the ws2000 and you should be ready


 
