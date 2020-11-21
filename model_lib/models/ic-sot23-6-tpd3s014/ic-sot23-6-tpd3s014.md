=Model development notes

The device provides reverse polarity protection and overcurrent protection.

The forward current limit is 0.85A typical, with a series resistance of 97 milliOhms.
The model can be a MOSFET biased at IDSS in the current diode configuration.

M1 %vin %vout %vout %vout ML2WN4A
.model ML2WN4A NMOS VTO=-0.7 KP=81.63m RD=5m RS=5m L=2u W=85u

It also has a protection network of 5 diodes on pins D1 and D2.
There is a charge pump to get a supply voltage higher than the rail.

To avoid the complexity of the charge pump for now, just model it in the on-state as
a 0.097 Ohm resistor, and model the protection diodes. It is interesting though,
because there are other features such as undervoltage lockout for the charge pump
and a pulldown at the output for power-down.

Quiescent current is 66uA, at 5V this is 75.7K

Diodes:
1.4pF from D1 and D2 to gnd
Diode resistances are 0.2 Ohm
Lower clamp diode is 0.95V max at 8mA
Zener voltage is 6V at 1mA
