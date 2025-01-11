# 🌐 **TEMPEST** – Abhören elektromagnetischer Emissionen  

> **⚡️ Ein TEMPEST-Angriff** nutzt elektromagnetische Emissionen, Geräusche und Vibrationen, um Informationen über das Ziel zu erhalten. Hier wird das Bildsignal eines Monitors extrahiert und angezeigt – möglich mit einem Software Defined Radio (SDR) und entsprechender Software.  



🎥 **Demo-Video:** [📁 TempestDemo.mp4](media/TempestDemo.mp4)  

---  

## 🛠️ Software und Hardware  

Eine der folgenden Programme zur Rekonstruktion des empfangenen Bildes wird benötigt:  

- [TempestSDR](https://github.com/martinmarinov/TempestSDR)  
- [gr-Tempest](https://github.com/git-artes/gr-tempest)  
- [deep-Tempest](https://github.com/emidan19/deep-tempest)  

  Zusätzlich wird eine klassische SDR-Software wie [HDSDR](https://hdsdr.de/) benötigt, um die Frequenz zu finden.  
  Ein [Demo-Video](https://github.com/eried/Research/blob/master/HackRF/TempestSDR/tempest_test_elize_song.mp4) ist ebenfalls nützlich.  

### 📡 **Empfohlene Hardware:**  
- **Einfaches SDR-Gerät:** [RTL-SDR auf Amazon](https://www.amazon.de/DVB-T-DAB-Stick-RTL2832U-Chipsatz/dp/B0C4DXV2CC/)  
- **Leistungsfähigeres SDR-Gerät:** [HackRF One](https://opensourcesdrlab.com/products/h4m-receiver-and-spectrum-analyzer?VariantsId=10005)  

| ![HackRF One + Portapack](images/Portapack.png) |  
| :---------------------------------------------: |  
| *HackRF One + Portapack und 32dBi Antenne (SDR)* |  

---  

## 🔧 Vorbereitung und Installation  

- Installation von **TempestSDR**, **gr-tempest** oder **deep-tempest**.  
- Siehe die Anleitungen in den jeweiligen GitHub-Repositories.  

---  

## 🕵️‍♂️ Durchführung des Angriffs  

### 1️⃣ **Finden der Frequenz des Monitors**  

1. Abspielen des Videos auf dem anzugreifenden Monitor.  
   - Stelle sicher, dass der Monitor eingeschaltet ist und ein geeignetes Testvideo abgespielt wird.  

2. Suche der Monitorfrequenz in der SDR-Software.  
   - Nutze die SDR-Software, um das Signal zu scannen.  
   - Beobachte die Frequenzspektren, um den Monitor zu identifizieren.  

3. Überprüfung des Signals mit „Für Elise“.  
   - Wenn das Lied „Für Elise“ zu hören ist, wurde die Frequenz gefunden.  

4. Notiere die Frequenz.  
   - Diese wird für den nächsten Schritt benötigt.  

| ![SDR Software](images/SDR-Software.png) |  
| :--------------------------------------: |  
| *🖥️ Klassische SDR Software zum Suchen der Monitorfrequenz* |  

| ![Für Elise Test-Video](images/fueElise.png) |  
| :------------------------------------------: |  
| *🎶 Screenshot aus dem Test-Video zur Frequenzsuche (Für Elise)* |  


```
⚠️ Wichtig:
Dieses Vorgehen dient nur der Veranschaulichung.  
In realistischen Angriffsszenarien wird die Monitor-Frequenz basierend auf Parametern wie Größe, Auflösung und Frequenz berechnet.
```

---  

### 2️⃣ **Konfiguration von TempestSDR**  

1. Eingabe der Monitorparameter und Frequenz.  
   - Öffne die Tempest-Software.  
   - Gib die zuvor notierte Frequenz und den Monitor-Typ ein.  

2. Laden des Gerätetreibers.  
   - Stelle sicher, dass der SDR-Treiber korrekt installiert ist.  
   - Wähle den passenden Treiber in der Software aus.  

3. Starten des Vorgangs.  
   - Beginne mit der Datenaufnahme und überprüfe die Ergebnisse in Echtzeit.  

| ![TempestSDR Konfiguration](images/TempestSDR.png) |  
| :------------------------------------------------: |  
| *⚙️ TempestSDR: Monitorparameter (links) und geladener Treiber (rechts)* |  

---  

### 3️⃣ **Bildrekonstruktion**  

1. Kein sichtbares Bild? Wähle den höchsten Ausschlag.  
   - Beobachte das Spektrum und identifiziere den Punkt mit der stärksten Aktivität.  

2. Anpassung der Parameter.  
   - Justiere die Software-Einstellungen für Kontrast, Helligkeit und Frequenzband.  
   - Geduld ist hier entscheidend, um ein klares Bild zu erhalten.  

| ![Abgefangenes Bild](images/MonitorCapture.png) |  
| :---------------------------------------------: |  
| *🖼️ Abgefangenes Bild* |  

---  

## 📚 Links zu den verwendeten Papern  

- [Deep-Tempest](https://arxiv.org/pdf/2407.09717v1)  
- [gr-Tempest](https://iie.fing.edu.uy/publicaciones/2022/LBCS22/LBCS22.pdf)  

---  

## 📂 Weitere Materialien  

Im Ordner `media/` befinden sich:  
- Bildschirmaufnahmen des Angriffs in Echtzeit.  
- Kurze Schritt-für-Schritt-Anleitung als Video.  

  - **Demo-Video:** [TempestDemo.mp4](media/TempestDemo.mp4)  
  - **Sound des abgefangenen Test-Videos:** [fuerElise.mp4](media/fuerElise.mp4)  
  - **Bester Angriff auf einen Canvas:** [BestAttempt.mp4](media/BestAttempt.mp4)  
  - **Einstellungen von TempestSDR:** [TempestSDR.mp4](media/TempestSDR.mp4)  
  - **Angriff auf eine Webpage:** [Webpage.mp4](media/Webpage.mp4)  
