# TEMPEST – Abhören elektromagnetischer Emissionen
  
>Ein TEMPEST-Angriff nutzt elektromagnetische Emissionen, aber auch Geräusche und Vibrationen, um Informationen über das Ziel zu erhalten. In meinem Fall das Bildsignal eines Monitors. Genauer gesagt geht es darum, das Signal von einem entfernten Gerät zu extrahieren und anzuzeigen. Mit einem Software Defined Radio (SDR) und entsprechender Software ist dies möglich.

---
![[TempestDemo.mp4]]
___

#### Software und Hardware
Eine der folgenden Programme zur Rekonstruktion des empfangenen Bildes wird benötigt:
-          [TempestSDR](https://github.com/martinmarinov/TempestSDR)
-          [gr-Tempest](https://github.com/git-artes/gr-tempest)
-          [deep-Tempest](https://github.com/emidan19/deep-tempest)

Zum Vereinfachen des Findens des Bildes wird zudem noch eine weitere klassische SDR-Software benötigt (wie z.B. [HDSDR](https://hdsdr.de/)), sowie ein spezielles [Demo-Video](https://github.com/eried/Research/blob/master/HackRF/TempestSDR/tempest_test_elize_song.mp4).
-          Einfaches SDR-Gerät: [RTL-SDR auf Amazon](https://www.amazon.de/DVB-T-DAB-Stick-RTL2832U-Chipsatz/dp/B0C4DXV2CC/)
-          Leistungsfähigeres SDR-Gerät: HackRF One [HackRF One auf OpenSourceSDRLab](https://opensourcesdrlab.com/products/h4m-receiver-and-spectrum-analyzer?VariantsId=10005)


|    ![[Portapack.png\|300]]     |
| :----------------------------------------------: |
| *HackRF one + Portapack und 32dBi Antenne (SDR)* |


#### Vorbereitung und Installation
-          Einrichten von **TempestSDR** oder **gr-** bzw. **deep-tempest** ein
-          Anleitung: siehe GitHub Repositories
---
#### Durchführen des Angriffs
1.       Finden der Frequenz des Monitors:
	- Abspielen des Videos auf dem anzugreifenden Monitor
	- Suchen der Monitorfrequenz in klassischer SDR-Software
	- Wenn das Lied „Für Elise“ zu hören ist, ist diese Frequenz gefunden
	- Notieren der Frequenz

|                  ![[SDR-Software.png]]                   |
| :------------------------------------------------------: |
| *Klassische SDR Software zum Suchen der Monitorfrequenz* |


|                ![[fueElise.png]]                 |
| :-----------------------------------------------------------------: |
| *Screenshot aus dem Test-Video zum finden der Frequenz (Für Elise)* |

`Wichtig ist anzumerken, dass dieses Vorgehen nur der Veranschaulichung gilt. In einem realistischen Angriffsszenario würde das Herausfinden der Monitor-Frequenz über Berechnungen erfolgen. Parameter hierfür sind z.b. Monitor -Größe/-Auflösung/-Frequenz.`


> **ACHTUNG:  
> Ab hier spezifisch für TempestSDR!**

2.      **Konfiguration von TempestSDR:**
	- Eingeben der Monitorparameter und der notierten Frequenz in TempestSDR
	  (oder einer der anderen Tempest-Software)
	- Laden des Gerätetreibers
	- Starten des Vorgangs

|                                ![[TempestSDR.png]]                                |
| :------------------------------------------------------------------------------------------------: |
| *TempestSDR beim Eingeben der Monitorparameter (links) und geladener Treiber für das SDR (rechts)* |

	
3.      **Bildrekonstruktion:**
	- Wenn kein Bild zu sehen ist, Auswahl des höchsten Ausschlags
	- Durch leichtes Anpassen der Parameter und ein bisschen Geduld lassen sich die Ergebnisse verbessern.

| ![[MonitorCapture.png]] |
| :----------------------------------: |
|         *Abgefangenes Bild*          |

---
#### Links zu den verwendeten Papern
- [Deep-Tempest](https://arxiv.org/pdf/2407.09717v1)
- [gr-Tempest](https://iie.fing.edu.uy/publicaciones/2022/LBCS22/LBCS22.pdf)

#### Weitere Materialien
Im `media` Ordner befinden sich Bildschirmaufnahmen des Angriffes in Echtzeit, sowie unter anderem eine kurze Zusammenfassung der Schritt-für-Schritt Anleitung als Video.

- Demo-Video: [[TempestDemo.mp4]]
- Sound des abgefangenen Test-Videos: [[fuerElise.mp4]]
- bisher bester Angriff auf einen abgebildeten Canvas: [[BestAttempt.mp4]]
- Kurze Aufnahme der initialen Einstellung von TempestSDR: [[TempestSDR.mp4]]
- Angriff auf eine abgebildete Webpage: [[Webpage.mp4]]
