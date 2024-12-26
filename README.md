# Balancerende lijnvolg-Robot

Mijn doel is om een lijnvolgende balancerende robot te bouwen. Als basis gebruik ik een 2-wielige balancerende robot die ik al "bouwpakket" gekocht heb. Lekker eenvoudig starten was de gedachten. Het mooie van dit bouwpakket is dat we de robot met behulp van een App op de telefoon via Bleutooth kunen besturen. Mijn gedachte is om deze bleutooth module weg te laten en hier voor in de plaats een microcontroller aan te sluiten welke de robot bestuurd. Deze microcontroller is in dit geval de ESP32-CAM. De camera hiervan gebruiken we om de lijn te detecteren en te analyseren, aan de hand van deze beelden en analyse sturen we een signaal naar de robot. Hoe eenvoudige kan dat zijn, toch ??

Een paar opmerkingen:

Op de ESP32-CAM hebben we een 2e seriele uitgang gemaakt die de data naar de seriele ingang van de Arduino-UNO verstuurt. Deze commando's (enkele karakters) betekenen bijvoorbeeld vooruit, linksom draaien, rechtsom draaien, achteruit of stop.

Elke echte robot hoort een intelligente led te hebben, vandaar tijdens het scannen van het beeld loopt het KITT-loopticht.

De voedingsspanning van de ESP32-CAM moet echt goed minimaal 5.00 Volt zijn, vandaar dat we vanuit de accu met een aparte step-down converter 5.00 Volt maken in plaats van dat we "ongeveer" 5 Volt vanuit de Arduino-UNO boord halen, dat gaf toch problemen.

Stilstaan is en blijft een uitdaging voor een balancerende robot, ik weet het, het kan beter, maar ik ben tevreden met dit resultaat !!

In de Arduino-IDE versie 1.6.8 gebruik ik versie 1.6.23 van de Arduino-bord libary. Als ik die naar een hogere versie update gaat het gewoon FOUT en werkt het UNO bordje NIET meer. (misschien max 1.8.3/6)

Programma's:

Het bestand Arduino-Balance-Car-master.zip is het orginele programma van MoebiusTech  voor de Arduino-UNO waarmee ik begonnen ben. 

ESP32_LijnSensor_v5.zip is het programma voor de ESP32-CAM om het beeld te analyseren en de besturings commando's naar de Arduino-UNO te versturen

BBC_v2.zip is het prgramma voor de Arduino-UNO om te balanceren en de besturingen vanuit de ESP32-CAM te onvangen via de seriele poort
