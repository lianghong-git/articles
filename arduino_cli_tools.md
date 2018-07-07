# arduino_mk的使用方法
sudo apt-get install arduino arduino-mk  
mkdir blink_test  
cd blink_test  
cp /usr/share/doc/arduino-core/examples/01.Basics/Blink/Blink.ino  
vim Makefile  
		ARDUINO_LIBS = Ethernet SPI  
BOARD_TAG = uno  
MONITOR_PORT = /dev/ttyACM0  
include	/usr/share/arduino/Arduino.mk`  
make  
make upload  
