Measured on 450W from RX2540M2

How to turn on PSU
1. pull down the B21-#PRESENT = connect it to GND B24 or A1-A8, B1-B8
2. pull down the A21-#POWERON = connect it to GND

| TOP | function |
| --- | --- |
| A1 |  |
| -  | GND |
| A8 |  |
| A9 |  |
| -  | 12V rail |             3k0    1k0
| A16 |  |
| A17 |  | 28 30 potom 0  1k5    10
| A18 |  | 28 30          1k5    10
| A19 | powergood | 0 0            4k5    1k5
| A20 | NC | 0 0            nc     1k5
| A21 | #poweron | 28 25          5k0    4k0
| A22 | NC | 0 0            nc     1k5
| A23 |  | 0 0            15     15   gnd
| A24 | voltagefeedback | 0 0            3k5    1k0  12v 
| A25 |  | 0 0            1k5    40


| BOTTOM | function |
| ------ | -------- |
| B1 |  |
| - | GND |
| B8 |  |
| B9 |  |
| - | 12V rail |  0              3k0    1k0
| B16 |  |
| B17 |  | 33 31          1k5    60  gnd na psu1 (adresa)
| B18 |  | 33 31          1k5    60  gnd
| B19 | 12Vsb | 120 118  1k0    10
| B20 |  | 0 0            1k5    10
| B21(short) | #present | 28 25   5k0    4k0 gnd
| B22 | NC | 0 0            nc     nc
| B23 |  | 0 0            8k0    3k0
| B24(short) | gnd | 0 0 0      0
| B25 | NC | 0 0            nc     nc

odporovo nie su spojene ziadne A s B iba B24 je spojene s gnd a velke kontakty su spolocne
okrem 12v make zdroje=pullup 
ziaden signal vsetko dc iba A17 sa meni ale tiez dc v radoch minut, mozno zmena na 0 po strachani datovych signalov
12kohm medzi gnd a pullup nezapne zdroj

FAN 
always on when AC connected, low speed when turned off

Status led 
Green blinking - AC connected, 12v rail turned off, 12vStandBy turned onn
Green - 12v rail turned on
Orange - failure, 12v rail turned off, 12vStandBy turned onn

B19 - 12v StandBy
always on 12v


B21 present
B21 is short pad = connects last when inserted into server
in PSU pullup to 3v3
on mainboard connected to gnd

A21 power on
in PSU pullup to 3v3

A19 - power good or PSU status
0v when turned off
3v3 when turned on
0v failure state = orange led

A24 - voltage feedback, 
in psu is connected to 12V rail using resitor
on mainboard it is connected to 12v rail, if voltage drops on connector resistance PSU boost voltage to compensate it, too big drop result in failure state = turn off and orange led 


PMBus
psu is passive - no digital signal 

B17,B18 PMBus address?
in psu is pull up to 3v3
on mainboard B17 is connected to gnd on PSU1 position, on PSU2 position is not connected
             B18 is connected to gnd on both PSU1 and PSU2 positions 
