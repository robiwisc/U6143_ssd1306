# U6143_ssd1306
This fork contains alternative display modes. 

C - the original files with a fix to the IP address to use eth0.

C_HostName_IP - updated to display the host name on top and added a 4th display in the loop containing the IP address. 

C_StaticHostName_IP - updated to only display the hostname and IP address.


## Preparation
```bash
sudo raspi-config
```
Choose Interface Options 
Enable i2c

##  Clone U6143_ssd1306 library 
```bash
git clone https://github.com/robiwisc/U6143_ssd1306.git
```
## Compile 
```bash
cd U6143_ssd1306/C

or

cd U6143_ssd1306/C_HostName_IP

```
```bash
sudo make clean && sudo make 
```
## Run 
```
sudo ./display
```

## Add automatic start script
- Open the rc.local file 
```bash
sudo nano /etc/rc.local
```
- Add command to the rc.local file
```bash
cd /home/pi/U6143_ssd1306/C
or
cd /home/pi/U6143_ssd1306/C_HostName_IP
sudo make clean 
sudo make 
sudo ./display &
```
- reboot your system

## For older 0.91 inch lcd without mcu 
- For the older version lcd without mcu controller, you can use python demo
- Install the dependent library files
```bash
sudo pip3 install adafruit-circuitpython-ssd1306
sudo apt-get install python3-pip
sudo apt-get install python3-pil
```
- Test demo 
```bash 
cd /home/pi/U6143_ssd1306/python 
sudo python3 ssd1306_stats.py
```










