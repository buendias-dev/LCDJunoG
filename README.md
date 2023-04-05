# JunoG display replacement
The Roland Juno-G display was defective. It was replaced by a new display but this item wasn't available anymore.
This project try to implement the previous work by dpeddi to replace original lcd screen with a generic one.

## Acknoledments
This work is based on this [github project](https://github.com/dpeddi/LCDJunoG), a masterpiece of reverse engeniering by the user dpeddi.

## References
### Roland Juno-G forum
https://forums.rolandclan.com/viewtopic.php?f=12&t=58712&start=30

### Original GitHub by dpeddi
https://github.com/dpeddi/LCDJunoG

You can take a look at another forks in Insights > Forks

### Detailled Github project by bjaan
https://github.com/bjaan/roland-juno-g-display-replacement


## Project development
### BOM
Connecting Roland Juno-G FPC connector to PCB display connector was the main problem
- [Raspberry Pi Pico](https://es.aliexpress.com/item/1005004005660504.html)
- [FPC/FFC Adapter Board 1.0mm 18P, Curved needle](https://es.aliexpress.com/item/32974345886.html)
- [FPC FFC Ribbon Flexible Flat Length 30CM, 18P, Forward Direction, Pitch 1.0mm](https://es.aliexpress.com/item/1005002468369055.html)
- [Dupont Jumper Wire Line 10CM 20CM 30CM Female VS Female, 20cm, 20pin](https://www.aliexpress.com/item/4000578173872.html)

### Raspberry Pico program uploading
I upload the program compiled by bjaan. You can find uf2 file in [releases](https://github.com/bjaan/roland-juno-g-display-replacement/releases)

1. Press BOOTSEL in Raspberry Pico and without releasing this button connect Raspberry Pico to power supply
2. Copy UF2 file to USB drive


### Disasembly Juno-G
Lots of screws. Please, download Juno-G Service Documentation and label all the screws that you have to take out.

Following the Service manual, locate CN12 connector. It's a 18 pin FPC connector located on the right.

To replace original screen, you have to remove three boards (one on the right, then one on the left and finally you can take out display board)

### Pinout
|JUNO-G Pin|JUNO-G Pin Function|Raspberry Pi Pico | Pico Pin|
|---|---|---|---|
|18|+5V|VSYS|39
|17|GND|GND (next to VSYS)|38|
|16|+3V|(not connected)||
|15|RST|GP14|19|
|14|CS1|GP13|17|
|13|CS2|GP12|16|
|12|RS|GP11|15|
|11|WE|GP10|14|
|10|D0|GP2|4|
|9|D1|GP3|5|
|8|D2|GP4|6|
|7|D3|GP5|7|
|6|D4|GP6|9|
|5|D5|GP7|10|
|4|D6|GP8|11|
|3|D7|GP9|12|
|2|BRGT|GP26|31|
|1|BRGT Vref|3V3|36|


```
       /----------\
      -|1       40|-
      -|        39|-18
      -|        38|-17
    10-|4         |-
     9-|5       36|-1
     8-|6         |-
     7-|7         |-
      -|          |-
     6-|9         |-
     5-|10      31|-2
     4-|11        |-
     3-|12        |-
      -|          |-
    11-|14        |-
    12-|15        |-
    13-|16        |-
    14-|17        |-
    15-|19        |-
      -|20      21|-
       \----------/
```                 
### Printing display support
I printed [dpeddi support](https://github.com/dpeddi/LCDJunoG/blob/main/junog_display_support%20v8.stl) slightly modified.

Because it was printed in blue, it was finally painted in black.

### Display label
Inspired by bjaan a I drew this simple label printed by the use of a label printer.
![Display Labels Preview](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/display_label_view.jpg)

This was the file. It was printed in a 130cm height.
[Display Label](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/display_label.png)


## Screenshots
![Display connection](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/display_conn.png)
![FFC to Display connector](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/ffc_2_display_conn.png)
![Raspberry Pi Pico](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/rasppico.png)
![Testing display](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/testing_display.jpeg)
![Working display](https://raw.githubusercontent.com/buendias-dev/LCDJunoG/main/working_display.jpeg)

