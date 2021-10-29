# Lirc

[參考](https://www.lirc.org/html/configuration-guide.html)

<img src="http://192.168.0.10/lib/2a6400f7-5ffc-4eb4-a077-37290e20944a/file/images/auto-upload/image-1634984770022.png?raw=1" width="436.97515869140625" height="null" />

LIRC是IR遙控器控制服務，將USB(RF)遙控器給LIRC控制，為了給支援LIRC的Application(Kodi,r_attenu)使用。

確保LIRC已經啟動，OSMC的LIRC不會自行啟動，在插入IR裝置後才會啟動。[來源](https://discourse.osmc.tv/t/lirc-reconfigure/11060)

### 設置

找出裝置id：

`ls -al /dev/input/by-id/`

建立lircd.conf：

此檔為遙控器按鍵內碼code與kernel內預設按鍵名字的對應map。

`irrecord --device=/dev/input/by-id/usb-Logitech_USB_Receiver-if02-event-mouse`

### 完整指令

`/usr/sbin/lircd --driver=devinput --device=/dev/input/by-id/usb-Logitech_USB_Receiver-if02-event-mouse --uinput --output=/var/run/lirc/lircd-lirc0 --pidfile=/var/run/lirc/lircd-lirc0.pid /home/osmc/mouse.lircd.conf`

\--output：為其他Application看見此裝置的接口(socket)，預設為/usr/var/run/lirc/lircd。

### 測試

irw \[socket]


