# Användarmanual
### Kurs 4, Workshop 1

---

## Innehållsförteckning
1. Vad är PlatformIO?
2. PlatformIO vs Arduino IDE – kort jämförelse
3. Vad behöver du för att komma igång?
4. Installera Visual Studio Code (VS Code)
5. Installera PlatformIO i VS Code
6. Anslut och testa med ditt Arduino-kort
7. Vanliga problem och lösningar
8. Sammanfattning

--- 

## Vad är PlatformIO?

PlatformIO är ett utvecklingsverktyg för programmering av mikrokontroller, som till exempel Arduino. Det är ett tillägg till Visual Studio Code, som är en modern texteditor. PlatformIO är ett kraftfullt alternativ till den vanliga Arduino IDE.

--- 

## PlatformIO vs Arduino IDE – kort jämförelse

| Funktion                     | Arduino IDE                  | PlatformIO i VS Code               |
|-----------------------------|------------------------------|------------------------------------|
| Enkelt gränssnitt           | ✅ Ja                         | 🔸 Lite mer avancerat             |
| Kodkomplettering            | 🔸 Begränsat                  | ✅ Ja (med smarta tips)           |
| Stöd för flera projekt      | 🔸 Svårt att hantera          | ✅ Ja, med bra projektstruktur    |
| Tilläggsmöjligheter         | 🔸 Begränsade                 | ✅ Många tillägg tillgängliga     |
| Integration med Git         | ❌ Nej                        | ✅ Ja                              |

>  **Skulle jag använda PlatformIO nu?**  
> Absolut! Smått knepigt men verkar ha bra potential! Men om du är helt nybörjare kan Arduino IDE vara enklare i början.

---

## Vad behöver du för att komma igång?

- En dator (Windows, macOS eller Linux)
- Arduino-kort (ex: Arduino Uno R4 WIFI)
- USB-kabel till kortet
- Internetuppkoppling
- Tålamod!

---

## Installera Visual Studio Code

1. Gå till [https://code.visualstudio.com](https://code.visualstudio.com)
2. Klicka på **Download** och välj din version (Windows/Mac/Linux)
3. Kör installationsfilen och följ instruktionerna

--- 

## Installera PlatformIO i VS Code

1. Öppna VS Code
2. Klicka på **Extensions** (fyrkantsikonen till vänster)
![extensions](https://github.com/user-attachments/assets/0f9d74a6-0c1a-489b-8ec9-05657efd8989)
3. Sök efter **PlatformIO IDE**
4. Klicka på **Installera**
![platform](https://github.com/user-attachments/assets/2c4b82cf-91ed-446a-b6b8-313f218a6d16)

VS Code kommer nu att installera alla nödvändiga delar automatiskt.

---

## Anslut och testa med ditt Arduino-kort

1. Anslut ditt Arduino-kort till datorn med USB-kabeln
2. Öppna PlatformIO (via VS Code-menyn)
![oppna](https://github.com/user-attachments/assets/f22097c9-3f0f-4a18-a1bd-372a6aaaedb1)

3. Skapa ett nytt projekt:
   - Välj kort: t.ex. **Arduino Uno R4 WIFI**
   - Välj ramverk: **Arduino**
   
![snalla](https://github.com/user-attachments/assets/af3da640-2387-41b9-a41c-cd872d78dad7)

4. Skapa en ny fil, t.ex. ws4.ini (viktigt att filen slutar på .ini). Skriv in ett enkelt testprogram, t.ex. en switch-knapp som får en LED att lysa:
![nuuu](https://github.com/user-attachments/assets/a06b98dc-cf5b-4f77-b44f-3c71f23a89cf)


int ledPin = 2;
int buttonPin = 3;

void setup()
{
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT_PULLUP);
  
  digitalWrite(buttonPin, LOW);
  
  Serial.begin(9600);
}

void loop()
{
  digitalRead(buttonPin);
  Serial.println(digitalRead(buttonPin));
  delay(100);
  
  if (digitalRead(buttonPin) == 0)
  {
    digitalWrite(ledPin, HIGH);
   
  }
  else if (digitalRead(buttonPin) == 1)
  {
    digitalWrite(ledPin, LOW);
  
  }
} 

5. Klicka på Build (kugghjulet) och sedan Upload (pil-upp-ikonen)

![bygg](https://github.com/user-attachments/assets/014250e4-8917-4ee0-bb6f-d453325896ad)

![upload](https://github.com/user-attachments/assets/3942ddd0-e4b1-43ff-8a3d-86f2aca4f66b)

---

## Vanliga problem och lösningar

| Problem                  | Möjlig lösning                                      |
|--------------------------|------------------------------------------------------|
| **"Port not found"**     | Kontrollera att Arduino är anslutet via USB         |
| **Fel kort valt**        | Dubbelkolla kortmodellen i projektinställningarna   |
| **Ingen uppladdning sker** | Stäng andra program som använder porten          |
| **Installationen misslyckas** | Starta om VS Code eller datorn              |

---

## Sammanfattning

PlatformIO är ett kraftfullt verktyg som hjälper dig att programmera Arduino på ett mer strukturerat sätt än med Arduino IDE.  
Det kräver lite mer i början, men ger dig fler möjligheter på sikt.  



   
