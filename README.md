# Arduino-Nano---NRF24L01-Controller
NRF24L01 powered wireless controller, this controller is provided with 2 dual axes joysticks, and 10 buttons.

This repo provides files to create your own wireless controller. Our main reason to create this controller was to control a Drone which is also done by the same team.

This project is based on an Arduino Nano, later we will provide a newer version with an Arduino Micro to power the board. Logical connections can be found in this schematic. Gerber files are available with this link.

## Power
This board is designed to power it with 2* 18650 bateries, there are 2 on board regulators (5V, 3.3V). please be carefull when connecting the bateries, the 3.3V regulator has a max VIN of 15V (5V regulator: 18V).

| Name | Type | Package | Voltage | PIN1 | PIN2 | PIN3 |
| --- | --- | --- | --- | --- | --- | --- |
| U3 | L7805CV | TO-220 | 5V | VIN | GND | VOUT |
| U5 | LD1117V33 | TO-220 | 3.3V | GND | VOUT | VIN |

## Buttons
Buttons are divided into 3 groups:
- 2 Joystick buttons {BL, BR}
-	4 Buttons left hand {BLA, BLB, BLC, BLD}
-	4 Buttons right hand {BRA, BRB, BRC, BRD}
-	2 Buttons in the middle {BCK, NXT}

| NET | Arduino Pin | Arduino Port | Component Name | Component Pin | Extra |
| --- | --- | --- | --- | --- | --- |
| BR | D0 | PE0 | P2 Joystick | B2A | Puldown and debounce circuit |
| BL | D1 | PE1 | P1 Joystick | B2A | Puldown and debounce circuit |
| BLA | D3 | PE1 | K1 | B1 & B2 | Puldown and debounce circuit |
| BLB | D4 | PE1 | K2 | B1 & B2 | Puldown and debounce circuit |
| BLC | D5 | PE1 | K3 | B1 & B2 | Puldown and debounce circuit |
| BLD | D6 | PE1 | K4 | B1 & B2 | Puldown and debounce circuit |
| BRA | D7 | PE1 | K8 | B1 & B2 | Puldown and debounce circuit |
| BRB | D8 | PE1 | K7 | B1 & B2 | Puldown and debounce circuit |
| BRC | D9 | PE1 | K6 | B1 & B2 | Puldown and debounce circuit |
| BRD | D10 | PE1 | K5 | B1 & B2 | Puldown and debounce circuit |
| BCK | A4 | PE1 | K9 | B1 & B2 | Puldown and debounce circuit |
| NXT | A5 | PE1 | K10 | B1 & B2 | Puldown and debounce circuit |

## NRF
The NRF24L01 serial communication pins are connected to the default (hardware ISP) arduino nano ISP pins. To use the NRF24L01 you can use the Radio library.

| NET | Arduino Pin | Arduino Port | Component Name | Component Pin | Extra |
| --- | --- | --- | --- | --- | --- |
| SCK | D13/SCK | PE0 | NRF24L01 | SCK | SPI |
| MOSI | D11/MOSI | PE0 | NRF24L01 | MOSI | SPI  |
| MISO | D12/MISO | PE0 | NRF24L01 | MISO | SPI |
| CE | A6 | PE0 | NRF24L01 | CE | SPI |
| CSN | A7 | PE0 | NRF24L01 | CSN |  |
| IRQ | D2 | PE0 | NRF24L01 | IRQ | Interrupt |
