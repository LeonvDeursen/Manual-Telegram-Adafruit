





1. Begin met het installeren van telegram op je telefoon en maak een account aan. 

2. Zoek de user ‘Botfather’ en maak een nieuwe bot aan. Ik noem de bot Sandman, jij noemt jouw bot? Je hebt de gegenereerde key zodadelijk nodig.

3.

4. voeg via de ‘Library Manager’ van Arduino de ‘universaltelegrambot’ toe.

5. En voeg “ArduinoJson” Benoit Blanchon toe, niet de beta maar de laatste versie.

6. Open ‘echobot’ uit universaltelegrambot > esp8266 examples (naar beneden scrollen in de lijst).

7. Pas in de Arduino code de wifi credentials en het BOTtoken aan, Upload je code, open de serial monitor. Check hier of je Wifi werkt.

8. Als je nu een berichtje vanuit telegram naar je bot stuurt, dan luistert je ESP mee en zal het bericht terugsturen als een echo naar telegram Bot.

9. Geef nu in je serial monitor de tekst weer, binnen de for loop doe je een

Serial.println(bot.messages[i].text);

10. Je kan binnen de loop van numNewMessages aanpassen om intelligentie toe te voegen en de tekst aan te passen die hij terugstuurt. Probeer een extra bericht te sturen m.b.v. een tweede aanroep van sendMessage. bot.sendMessage(bot.messages[i].chat_id, "Alles goed kameraad?", "");

11. Configureer de ingebouwde led als output, voe aan de void setup de volgende redel toe:

pinMode(LED_BUILTIN, OUTPUT); // Initialize the LED_BUILTIN pin as an output

12. We gaan nu rudimentaire intelligentie aanbrengen. Binnen dezelfde loop maken we een if / else if aan die luistert naar .text waarde (stap 9).

Wanneer deze waarde gelijk is aan jouw commando bijvoorbeeld “lights on” zet je de builtin led (LED_BUILTIN = LOW) aan. Verzin ook welke tekst je in de else if wil hebben om hem uit (HIGH) te zetten.

13. Koppel je ledstrip en activeer disco modus!
