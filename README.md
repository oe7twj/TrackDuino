# TrackDuino
Track Display for a 1541 Floppy Drive


### Nessecary Hardware:
- an old 1541 Floppy Drive
- an arduino Nano [3€]
- a TM1637 display (4x 7 segment) [1€]
- a bundle jumper wire [1€]


### Nessecary Software:
- Arduino Workbench
- Arduino Lib: digitalWriteFast 
  https://github.com/NicksonYap/digitalWriteFast
- Arduino Lib: TimerOne


### TrackDuino can do for you:
- either display the current track 
- or work as an I2C slave device sending the current track


## How does it work:

After reset the current track is unknown.

If Floppy Drive starts the Arduino starts reading data from inserted Floppy Disc.
It simply reads the data from internal IO device VIA 6522.
Each track contains some data sectors, and each sector has an sector-header.
The sector-header contains information about the current track# and sector# and some others.

As soon the track number is extracted from sector data it display the track number (or offers it as I2C slave).
Now it is simple to track the change of track by reading the data for the stepper motor.


![Screenshot](/docu/7-Seg-blau.jpg)


