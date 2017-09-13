# mCC1101
An Arduino libraray for TI CC1101

It is based on panstamp library and has the same licence of course : LGPLv3 or later

It has many simplifications compared to the original panStamp library.
- The ccpacket struct is not used. The sendPacket and getPacket functions use byte buffers.
- New function sendBurstPacket to send a burst of packets mainly to wake up from WOR
- New function print. For example<br/>
print(F("Elevation=%d Size=%d"),30,5);<br/>
will send a RF packet containing "Elevation=30 Size=5"

Must be installed in the arduino library folder

Note:
This library, converted to pure C, is also used by the rfboot bootloader.
