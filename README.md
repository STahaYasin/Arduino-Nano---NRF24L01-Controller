# Arduino Nano - NRF24L01 Wireless Controller
NRF24L01 powered wireless controller, this controller is provided with 2 dual axes joysticks, and 10 buttons.

This repo provides files to create your own wireless controller. Our main reason to create this controller was to control a Drone which is also done by the same team.

This project is based on an Arduino Nano, later we will provide a newer version with an Arduino Micro to power the board. Logical connections can be found in this schematic. Gerber files are available with this link.

## Power
This board is designed to power it with 2* 18650 bateries, there are 2 on board regulators (5V, 3.3V). please be carefull when connecting the bateries, the 3.3V regulator has a max VIN of 15V (5V regulator: 18V).

| Name | Type | Package | Voltage | PIN1 | PIN2 | PIN3 |
| --- | --- | --- | --- | --- | --- | --- |
| U3 | L7805CV | TO-220 | 5V | VIN | GND | VOUT |
| U5 | LD1117V33 | TO-220 | 3.3V | GND | VOUT | VIN |

## Joysticks
The board is provided with two dual-axis joysticks
- 2 Joysticks {P1, P2}, 4 Axis {V1, H1, V2, H2}

| NET | Arduino Pin | Arduino Port | Component Name | Component Pin | Extra |
| --- | --- | --- | --- | --- | --- |
| V1 | A0 | PC0 | P1 Joystick | V2 | Vertical Left Hand |
| H1 | A1 | PC1 | P1 Joystick | H1 | Horizontal Left Hand |
| V2 | A2 | PC2 | P2 Joystick | V2 | Vertical Right Hand |
| H2 | A3 | PC3 | P2 Joystick | H2 | Horizontal Right Hand |

## Buttons
Buttons are divided into 3 groups:
- 2 Joystick buttons {BL, BR}
-	4 Buttons left hand {BLA, BLB, BLC, BLD}
-	4 Buttons right hand {BRA, BRB, BRC, BRD}
-	2 Buttons in the middle {BCK, NXT}

| NET | Arduino Pin | Arduino Port | Component Name | Component Pin | Extra |
| --- | --- | --- | --- | --- | --- |
| BR | D0 | PD0 | P2 Joystick | B2A | Puldown and debounce circuit |
| BL | D1 | PD1 | P1 Joystick | B2A | Puldown and debounce circuit |
| BLA | D3 | PD3 | K1 | B1 & B2 | Pulldown and debounce circuit |
| BLB | D4 | PD4 | K2 | B1 & B2 | Pulldown and debounce circuit |
| BLC | D5 | PD5 | K3 | B1 & B2 | Pulldown and debounce circuit |
| BLD | D6 | PD6 | K4 | B1 & B2 | Pulldown and debounce circuit |
| BRA | D7 | PD7 | K8 | B1 & B2 | Pulldown and debounce circuit |
| BRB | D8 | PB0 | K7 | B1 & B2 | Pulldown and debounce circuit |
| BRC | D9 | PB1 | K6 | B1 & B2 | Pulldown and debounce circuit |
| BRD | D10 | PB2 | K5 | B1 & B2 | Pulldown and debounce circuit |
| BCK | A4 | PC4 | K9 | B1 & B2 | Pulldown and debounce circuit |
| NXT | A5 | PC5 | K10 | B1 & B2 | Pulldown and debounce circuit |

## NRF
The NRF24L01 serial communication pins are connected to the default (hardware ISP) arduino nano ISP pins. To use the NRF24L01 you can use the Radio library.

| NET | Arduino Pin | Arduino Port | Component Name | Component Pin | Extra |
| --- | --- | --- | --- | --- | --- |
| SCK | D13/SCK | PB5 | NRF24L01 | SCK | SPI |
| MOSI | D11/MOSI | PB3 | NRF24L01 | MOSI | SPI  |
| MISO | D12/MISO | PB4 | NRF24L01 | MISO | SPI |
| CE | A6 | PC6 | NRF24L01 | CE | SPI |
| CSN | A7 | PC7 | NRF24L01 | CSN |  |
| IRQ | D2 | PD2 | NRF24L01 | IRQ | Interrupt |
