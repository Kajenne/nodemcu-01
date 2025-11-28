# En introduktion till ett blinkprogram i Arduino

I detta moment ska ni få lära er om Arduinos två basfunktioner och skapa en förståelse för en enkel kod till ett blinkprogram i Arduino genom `esp8266`.
## Krav för detta moment

* Installation av `Arduino`
 <img width="165" height="62" alt="image" src="https://github.com/user-attachments/assets/68f213af-1471-4d59-8493-bf9eed7685e9" />

* Nedladdning av board `esp8266`
  
  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/9e7dcb24-fcd2-4d8f-8f7a-d65778631bc2" />

* Tillgång till en NodeMCU som går att kopplas till datorn med kompatibel sladd 

<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/6da8abd9-79b4-4b46-b6a0-6e5502f0c59a" />

***

## Två basfunktioner i Arduino 

### void Setup
Vid start eller reset av programmet körs denna kod

```c
void setup() {
  // put your setup code here, to run once:

}
```


### void Loop
Loop körs däremot om och om igen eller tills bestämt stopp. 
```c
void loop() {
  // put your main code here, to run repeatedly:

}
```
***

## Sätt upp ett blinkprogram i Arduino
1. Börja med att gå till tools > Board > ESP8266 > Version Generic ESP8266 Module 
<img width="1227" height="1072" alt="image" src="https://github.com/user-attachments/assets/0597e894-f203-44bb-b5b3-dc4847cbb578" />

2. Koppla in din NodeMCU till din dator, välj tools > port > Den port som tillhör din NodeMCU
   
4. Välj file > Exampels > ESP8266 > Blink 
 <img width="811" height="1079" alt="image" src="https://github.com/user-attachments/assets/8f3acb11-76db-4c49-ba03-71bce50cbf59" />

En exempelkod öppnas: 
<img width="1100" height="769" alt="image" src="https://github.com/user-attachments/assets/5b160753-f89b-4a00-b490-4dfeefdd7616" />

5. Verify
 <img width="518" height="44" alt="image" src="https://github.com/user-attachments/assets/a315e6d1-4166-4917-b788-3097ef8d5e35" />

7. Upload
 <img width="516" height="51" alt="image" src="https://github.com/user-attachments/assets/57e7ba2d-3d48-438c-99d3-0af86b59ab18" />

Klart, lampan på din NodeMCU bör blinka.

***

## Enkelt blinkprogram exempel och förklaring 
```c
/*
  ESP8266 Blink by Simon Peter
  Blink the blue LED on the ESP-01 module
  This example code is in the public domain

  The blue LED on the ESP-01 module is connected to GPIO1
  (which is also the TXD pin; so we cannot use Serial.print() at the same time)

  Note that this sketch uses LED_BUILTIN to find the pin with the internal LED
*/

void setup() {
  pinMode(LED_BUILTIN, OUTPUT);  // Initialize the LED_BUILTIN pin as an output
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, LOW);  // Turn the LED on (Note that LOW is the voltage level
  // but actually the LED is on; this is because
  // it is active low on the ESP-01)
  delay(1000);                      // Wait for a second
  digitalWrite(LED_BUILTIN, HIGH);  // Turn the LED off by making the voltage HIGH
  delay(2000);                      // Wait for two seconds (to demonstrate the active low LED)
}
```
* Notera att Arduinos basfunktioner är med i koden.
* Pinmode i setupdelen talar om vilken pin som används som output 
* Efter // följer kommentarer som talar om vad som sker 
* High - Släcker lampan
* Low - Tänder lampan
  
