# Sonoff S26

```
$ make backup
source venv/bin/activate; \
        esptool.py -p /dev/ttyUSB0 read_flash 0x00000 0x100000 backup_2020-07-30T19:11:54-03:00.bin
esptool.py v2.8
Serial port /dev/ttyUSB0
Connecting....
Detecting chip type... ESP8266
Chip is ESP8266EX
Features: WiFi
Crystal is 26MHz
MAC: cc:50:e3:68:49:7b
Uploading stub...
Running stub...
Stub running...
1048576 (100 %)
Read 1048576 bytes at 0x0 in 95.6 seconds (87.7 kbit/s)...
Hard resetting via RTS pin...
```

```
$ make flash
source venv/bin/activate; \
        esptool.py -p /dev/ttyUSB0 write_flash --flash_size 1MB --flash_mode dout 0x00000 \
        tasmota_6.1.1.bin
esptool.py v2.8
Serial port /dev/ttyUSB0
Connecting....
Detecting chip type... ESP8266
Chip is ESP8266EX
Features: WiFi
Crystal is 26MHz
MAC: cc:50:e3:68:49:7b
Uploading stub...
Running stub...
Stub running...
Configuring flash size...
Compressed 501344 bytes to 344992...
Wrote 501344 bytes (344992 compressed) at 0x00000000 in 33.6 seconds (effective 119.2 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...
```

## Resources
[https://drud.cz/2019/05/05/how-to-flash-sonoff-s26-with-tasmota/](https://drud.cz/2019/05/05/how-to-flash-sonoff-s26-with-tasmota/)
