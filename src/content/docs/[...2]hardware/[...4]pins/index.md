---
title: Pins und Schnittstellen
description: Der Calliope mini verfügt über diverse Schnittstellen mit unterschiedlichen Protokollen, die programmiert werden können und womit Daten ausgetauscht werden.
template: docs
published: true
---

# {title} 

{description}


## Stromversorgung

### Spannung

- Alle ein und Ausgabe-Pins liefern 3,3 V und werden auch mit 3,3 V betrieben.

<!-- :::admonition type="info" -->
Sensoren die mit 5V betrieben werden, funktionieren in den meisten Fällen nicht.
<!-- ::: -->

### Stromstärke

- Der Calliope mini kann bis zu **15 milli Ampere (mA) pro Pin** maximal bereitstellen
- für alle Pins sind es **100 mA insgesamt**

<!-- :::no -->
Schließe niemals mehre Verbraucher, mit 20mA wie z.B. 2 LEDs an einen I/O-Pin an.
<!-- ::: -->

<!-- :::yes -->
Verwendete stattdessen verschiedene I/O Pins oder eine Transistorenschaltung. Beachte, dass ingesamt nicht die 100 mA überschritten werden.
<!-- ::: -->




## Analoge Pins

<!-- :::admonition type="info" -->
In der Signalverarbeitung wird werden Daten verallgemeinert in zwei verschiedenen Formen übertragen: 
- **Digital**: Ein binäres, digitales Signal ist an oder aus, 1 oder 0. Es ist abgestuft, abzählbar und verlustbehaftet (diskrete Werte).
- **Analog**: Ein analoges Signal, dahingegen hat einen zeitlich kontinuierlichen, stufenlosen Verlauf. Es kann theoretisch unendlich viele Werte in einem Wertebereich annehmen.
<!-- ::: -->

### Digital Analog-Umsetzer (DAU/DAC)
Der integrierte Digital-Analog-Umsetzer des Calliope mini sorgt dafür, dass die analogen Signale vom Prozessor - der nur digital Signale verarbeiten kann - umgewandelt werden. Die Daten werden in den Bereich **0 - 1023** geschrieben und können auch so in dem jeweiligen Editor oder auch seriell als analoge Werte ausgelesen werden.

### PWM

Um eine LED zu dimmen oder die Geschwindigkeit eines Motors zu varieren, müsste analog die Spannung verändert werden. Der Ausgang der Pins liegt allerdigns immer bei 3,3 V. Mit der Pulsweitenmodulation wird durch schnelles ein und auschalten in unterschiedlicher Periodendauer ein analoges Signal simuliert werden, welches unterschiedliche abgestufte Werte annehmen kann. 

**Wieviele PWM-Pins können parallel verwendet werden?** 
Es können bis zu 3 PWM-Signale gleichzeitig generiert werden, bevor diese anfangen unflüssig und abgestuft zu werden. 


## Pinbelegung

| Pin | Übertragung | Typ/Protokoll |
| :------ | :-- | :------------- |
| P0 | digital | Touchpin |
| P1 | digital, analog | Touchpin | 
| P2 | digital, analog | Touchpin |
| P3 | digital | Touchpin |
| C4 | digital, analog | |
| C5 | digital, analog | |
| C6 | digital, analog | |
| C7 | digital, SCK | SPI |
| C8 | digital, MISO | SPI |
| C9 | digital, MOSI | SPI |
| C10 | digital | |
| C11 | digital | |
| C12 | digital | |
| C13 | ? | |
| C14 | ? | |
| C15 | ? | |
| C16 | digital, analog, RX | UART |
| C17 | digital, analog, TX | UART |
| C18 | SDA | I2C | 
| C19 | SCL | I2C |

<!-- | C1 | digital | |
| C0 | digital | I/O Pin | 
| C2 | digital/analog | |
| C3 | digital | | -->