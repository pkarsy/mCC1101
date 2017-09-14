# mCC1101
An Arduino libraray for TI CC1101, a very capable and flexible sub GHz transceiver.

It is based on panstamp library and has the same licence of course : LGPLv3 or later

It has many simplifications and some additions, compared to the original panStamp library.
- The ccpacket struct is removed. The sendPacket and getPacket functions use byte buffers.
- disabled save-to-EEPROM functionality. It is now
responsibility of the developer to save the RF paramaters.
- Now the interrupt flag is part of the class. This allows member functions to manipulate it.
- New function sendBurstPacket to send a burst of identical (And usually very short) packets mainly to wake up from WOR.
This method can have some advantages (in some scenarios) over transmitting an unmodulated baseband signal.
- New function print. For example<br/>
rf.print(F("Elevation=%d Size=%d"),30,5);<br/>
will send a RF packet containing "Elevation=30 Size=5".<br/>
This function is useful when the PC has a bridge receiving RF packets and feeding the data to a serial port.<br/>
See https://github.com/pkarsy/rfboot for details.

***Installation***

```sh
# Change this with your actual libraries directory
cd ~/sketchbook/libraries/
git clone https://github.com/pkarsy/mCC1101.git
```

Must be installed in the arduino library folder

Note:
This library, converted to pure C, is also used by the rfboot bootloader.
