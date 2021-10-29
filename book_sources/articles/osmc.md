# OSMC

### 設定Boss DAC驅動

`sudo vim /boot/config-user.txt`

加入：

`dtparam=audio=off`

`dtoverlay=allo-boss-dac-pcm512x-audio`

### 設定Boss為default

找出卡號：

`aplay -l`

`sudo vi /etc/asound.conf`

加入：

`defaults.pcm.card 1`

`defaults.ctl.card 1`

### 觀察輸出資訊

`less /proc/asound/card1/pcm0p/sub0/hw_params`


