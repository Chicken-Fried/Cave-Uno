<p align="center">
  <img src="cave_rover_logo.png" alt="Logo Cave Rover" width="110"/>
</p>

<h1 align="center">Cave Uno (Rev 1.0)</h1>

<p align="center">
  <b>Version Française 🇫🇷</b> | <a href="README.md">English Version 🇬🇧</a>
</p>

<p align="center">
  <a href="https://ohwr.org/cern_ohl_p_v2.txt"><img src="https://img.shields.io/badge/Licence_Mat%C3%A9rielle-CERN--OHL--P-blue.svg" alt="Licence Matérielle"/></a>
  <a href="https://creativecommons.org/licenses/by-sa/4.0/"><img src="https://img.shields.io/badge/Licence_Documentation-CC_BY--SA_4.0-lightgrey.svg" alt="Licence Documentation"/></a>
  <a href="https://www.kicad.org/"><img src="https://img.shields.io/badge/KiCad-10.0-informational.svg" alt="Version KiCad"/></a>
  <a href="https://www.microchip.com/en-us/product/ATmega328PB"><img src="https://img.shields.io/badge/MCU-ATmega328PB_%40_16MHz-success.svg" alt="MCU"/></a>
  <a href="#-conçue-pour-lenseignement-technique--supérieur"><img src="https://img.shields.io/badge/Format-Compatible_Shields_Uno_R3-orange.svg" alt="Format Uno R3"/></a>
  <a href="#-ingénierie-européenne--patrimoine-ardéchois"><img src="https://img.shields.io/badge/Con%C3%A7u_en-Europe_%F0%9F%87%AA%F0%9F%87%BA-blue.svg" alt="Conçu en Europe"/></a>
  <a href="#-points-forts--caractéristiques-matérielles"><img src="https://img.shields.io/badge/USB--C-Plug_%26_Play_(Sans_Pilote)-brightgreen.svg" alt="USB-C Sans Pilote"/></a>
</p>

**Cave Uno** est une carte de développement microcontrôleur open-source de nouvelle génération, conçue et développée en Europe par **Cave Rover**. Pensée spécifiquement pour les **étudiants en filières techniques, d'ingénierie et d'électronique** (BTS CIEL/SN, BUT GEII, écoles d'ingénieurs, licences, FabLabs), la Cave Uno modernise en profondeur l'incontournable **Arduino Uno Rev3**.

Elle conserve une **compatibilité mécanique et électrique à 100% avec les shields et accessoires de l'Arduino Uno R3**, tout en éliminant ses limites historiques grâce à une architecture moderne : **connectique USB-C réversible avec puce USB-UART native sans installation de pilote**, convertisseur Buck synchrone haute efficacité, gestion d'alimentation à diodes idéales (zéro perte de tension), régulateur 3.3V haute puissance, rail d'alimentation logique commutable, périphériques étendus du microcontrôleur **ATmega328PB**, et sérigraphie d'art vectoriel haute précision basée sur les relevés LiDAR des Gorges de l'Ardèche et de la Grotte Chauvet.

---

## 🖼️ Aperçu 3D de la Carte Assemblée (Rendu Raytracing KiCad)

![Bannière 3D Cave Uno Assemblée](cave_uno_3d_banner_github.png)

<p align="center">
  <img src="cave_uno_3d_top.png" alt="Cave Uno Vue 3D Dessus" width="49%"/>
  <img src="cave_uno_3d_bottom.png" alt="Cave Uno Vue 3D Dessous" width="49%"/>
</p>

---

## 🎓 Conçue pour l'Enseignement Technique & Supérieur

Les cartes 8-bits classiques en milieu éducatif souffrent fréquemment de régulateurs linéaires qui surchauffent, de ports USB obsolètes (USB-B ou micro-USB fragiles), de conflits de pilotes propriétaires (clones CH340 non reconnus) et d'un manque de bus de communication pour les projets modernes. La **Cave Uno** répond directement à ces problématiques :

* **Prise en main immédiate et universelle (Sans Pilote) :** La puce d'interface USB-UART **WCH CH9101R** est nativement reconnue par la classe CDC des systèmes d'exploitation récents (Windows 10/11, macOS, Linux). Aucun pilote externe ni droit d'administrateur scolaire requis : branchez en USB-C et téléversez instantanément depuis l'Arduino IDE.
* **Robustesse de laboratoire :** Étage d'alimentation à découpage protégé contre les inversions de polarité et les surtensions (jusqu'à 18V), réseau de diodes TVS ESD sur le port USB, et diodes idéales empêchant tout retour de courant dangereux entre le PC et l'alimentation externe.
* **Apprentissage des architectures multi-bus modernes :** Les étudiants peuvent expérimenter le double bus I2C matériel (`Wire` et `Wire1`), le double bus SPI et le double port série UART sans recourir à des émulations logicielles lentes.
* **Interfaçage logique sans encombre :** Grâce à l'interrupteur `SW1`, le rail `VDD` bascule instantanément entre **5V** et **3.3V**, permettant de connecter directement des capteurs et modules 3.3V modernes sans montage complexe de ponts diviseurs ou adaptateurs de niveaux.

---

## ⚡ Points Forts & Caractéristiques Matérielles

* **Ingénierie européenne & Patrimoine :** Conception et routage réalisés en Europe (France / Ardèche). Face arrière ornée des courbes de niveau LiDAR du canyon du Pont d'Arc et de la Grotte Chauvet (UNESCO).
* **Cœur AVR Microchip ATmega328PB cadencé à 16 MHz :**
  * **Double TWI / I2C matériel :** Bus indépendants `Wire` (broches A4/A5) et `Wire1` (connecteur J3).
  * **Double SPI matériel :** Idéal pour piloter simultanément un afficheur TFT rapide et une carte SD.
  * **Double USART matériel :** Port de téléversement/moniteur série + port dédié aux capteurs (GPS, Bluetooth, RS485).
  * **9 canaux PWM :** 3 sorties PWM supplémentaires par rapport à l'ATmega328P standard.
* **Alimentation Buck synchrone 1.5A (AP63205) :** Rendement supérieur à 90%, entrée étendue de **7V à 18V** sur fiche jack DC 5.5×2.1mm sans dégagement thermique excessif.
* **OR-ing à Diodes Idéales (Double LM66100) :** Commutation automatique entre alimentation USB et Jack externe sans chute de tension (chute quasi nulle < 20mV, contre ~500mV sur les diodes Schottky classiques).
* **Rail 3.3V puissant de 600mA (AP2112K) :** Alimente sereinement les modules Wi-Fi (ESP8266/ESP32), radio (NRF24L01, LoRa SX1276) et écrans couleur.
* **LED RVB intelligente adressable (WS2812B) :** Intégrée sur la broche `D23` (`PE0`) pour le retour d'état, les TP de programmation d'effets lumineux et le débogage visuel.
* **Connecteur I2C dédié (`J7`) :** 4 broches mâles (GND, 5V, SDA, SCL) pour brancher directement des capteurs et afficheurs OLED.
* **Connecteur UART dédié (`J8`) :** 4 broches mâles (RX0, TX0, GND, 5V) pour la télémétrie et les modules externes.

---

## 📐 Brochage Complet & Architecture des Connecteurs

![Schéma d'assignation des broches Cave Uno](cave_uno_pinout.png)

### Tableau Exhaustif Broche par Broche

Chaque broche de chaque connecteur de la carte est décrite ci-dessous :

| Connecteur | N° Broche | Sérigraphie | Registre Port | Broche Physique TQFP | Fonction par Défaut | Fonctions Secondaires & Alternatives |
|:---|:---:|:---|:---:|:---:|:---|:---|
| **J4** (Numérique Haut) | 10 | **SCL0** | PC5 | Broche 28 | Wire / TWI0 SCL | Entrée analogique A5, PCINT13 |
| | 9 | **SDA0** | PC4 | Broche 27 | Wire / TWI0 SDA | Entrée analogique A4, PCINT12 |
| | 8 | **AREF** | — | Broche 20 | AREF | Tension de référence du convertisseur ADC |
| | 7 | **GND** | — | — | Masse (GND) | Référence 0V numérique |
| | 6 | **13** | PB5 | Broche 17 | E/S Numérique | SCK0 (Horloge SPI0), LED témoin L |
| | 5 | **12** | PB4 | Broche 16 | E/S Numérique | MISO0 (Données entrantes SPI0) |
| | 4 | **~11** | PB3 | Broche 15 | E/S Numérique | MOSI0 (Données sortantes SPI0), PWM ~ |
| | 3 | **~10** | PB2 | Broche 14 | E/S Numérique | SS0 (Sélection esclave SPI0), PWM ~ |
| | 2 | **~9** | PB1 | Broche 13 | E/S Numérique | Sortie PWM ~ (Timer1 OCA) |
| | 1 | **8** | PB0 | Broche 12 | E/S Numérique | CLKO / ICP1 (Capture d'entrée Timer1) |
| **J6** (Numérique Bas) | 8 | **7** | PD7 | Broche 11 | E/S Numérique | AIN1 (Comparateur analogique -) |
| | 7 | **~6** | PD6 | Broche 10 | E/S Numérique | AIN0 (Comparateur analogique +), PWM ~ |
| | 6 | **~5** | PD5 | Broche 9 | E/S Numérique | T1 (Horloge externe Timer1), PWM ~ |
| | 5 | **4** | PD4 | Broche 2 | E/S Numérique | XCK0 (Horloge synchrone USART0), T0 |
| | 4 | **~3** | PD3 | Broche 1 | E/S Numérique | INT1 (Interruption externe 1), PWM ~ |
| | 3 | **2** | PD2 | Broche 32 | E/S Numérique | INT0 (Interruption externe 0) |
| | 2 | **TX → 1** | PD1 | Broche 31 | UART TX0 | Transmission série asynchrone |
| | 1 | **RX ← 0** | PD0 | Broche 30 | UART RX0 | Réception série asynchrone |
| **J5** (Alimentation) | 1 | **NC** | — | — | Non Connecté | Broche réservée |
| | 2 | **IOREF** | — | — | +5.0V | Référence de niveau logique pour shield |
| | 3 | **RESET** | PC6 | Broche 29 | Reset Actif-Bas | Réinitialisation matérielle du MCU |
| | 4 | **3.3V** | — | — | Sortie +3.3V | Régulateur AP2112K (600mA continu) |
| | 5 | **5V** | — | — | Sortie +5.0V | Régulateur Buck AP63205 / USB (1.5A max) |
| | 6 | **GND** | — | — | Masse (GND) | Masse générale du système |
| | 7 | **GND** | — | — | Masse (GND) | Masse générale du système |
| | 8 | **VIN** | — | — | Entrée Brute (7V–18V)| Entrée fiche Jack DC 5.5×2.1mm |
| **J2** (Analogique) | 1 | **A0** | PC0 | Broche 23 | Entrée Analogique 0 | Canal ADC 0, PCINT8 |
| | 2 | **A1** | PC1 | Broche 24 | Entrée Analogique 1 | Canal ADC 1, PCINT9 |
| | 3 | **A2** | PC2 | Broche 25 | Entrée Analogique 2 | Canal ADC 2, PCINT10 |
| | 4 | **A3** | PC3 | Broche 26 | Entrée Analogique 3 | Canal ADC 3, PCINT11 |
| | 5 | **A4** | PC4 | Broche 27 | Entrée Analogique 4 | Canal ADC 4 / Bus I2C TWI0 SDA |
| | 6 | **A5** | PC5 | Broche 28 | Entrée Analogique 5 | Canal ADC 5 / Bus I2C TWI0 SCL |
| **J3** (E/S Supplémentaires) | 1 | **SDA1** | PE0 | Broche 25 | Wire1 / TWI1 SDA | GPIO D23, Entrée DIN WS2812B, RXD1 |
| | 2 | **SCL1** | PE1 | Broche 26 | Wire1 / TWI1 SCL | GPIO D24, MISO1 (SPI1), TXD1 |
| | 3 | **A6** | PE2 | Broche 19 | Entrée Analogique 6 | Canal ADC 6, SS1 (Sélection esclave SPI1) |
| | 4 | **A7** | PE3 | Broche 22 | Entrée Analogique 7 | Canal ADC 7, MOSI1 (Sortie maître SPI1) |
| **J7** (I2C_0 Dédié) | 1 | **GND** | — | — | Masse (GND) | Référence de masse capteur |
| | 2 | **5V** | — | — | Sortie +5.0V | Alimentation 5V pour périphériques I2C |
| | 3 | **SDA0** | PC4 | Broche 27 | Wire / TWI0 SDA | Données série bus I2C principal |
| | 4 | **SCL0** | PC5 | Broche 28 | Wire / TWI0 SCL | Horloge série bus I2C principal |
| **J8** (UART Dédié) | 1 | **D0** | PD0 | Broche 30 | UART RX0 | Ligne de réception série matériel |
| | 2 | **D1** | PD1 | Broche 31 | UART TX0 | Ligne d'émission série matériel |
| | 3 | **GND** | — | — | Masse (GND) | Référence de masse série |
| | 4 | **5V** | — | — | Sortie +5.0V | Alimentation 5V pour modules série |
| **J9** (Bus VDD Commutable) | 1 | **VDD** | — | — | Rail VDD 1 | Tension 5V ou 3.3V sélectionnée via SW1 |
| | 2 | **VDD** | — | — | Rail VDD 2 | Tension 5V ou 3.3V sélectionnée via SW1 |
| | 3 | **VDD** | — | — | Rail VDD 3 | Tension 5V ou 3.3V sélectionnée via SW1 |
| | 4 | **VDD** | — | — | Rail VDD 4 | Tension 5V ou 3.3V sélectionnée via SW1 |
| **J10** (Bus GND Additionnel) | 1 | **GND** | — | — | Masse 1 | Retour de masse plan continu |
| | 2 | **GND** | — | — | Masse 2 | Retour de masse plan continu |
| | 3 | **GND** | — | — | Masse 3 | Retour de masse plan continu |
| | 4 | **GND** | — | — | Masse 4 | Retour de masse plan continu |
| **J1** (Connecteur ICSP AVR) | 1 | **5V** | — | — | Sortie +5.0V | Alimentation de la cible de programmation |
| | 2 | **MOSI0** | PB3 | Broche 15 | SPI0 MOSI | Données de programmation in-situ |
| | 3 | **MISO0** | PB4 | Broche 16 | SPI0 MISO | Données de retour du programmateur |
| | 4 | **SCK0** | PB5 | Broche 17 | SPI0 SCK | Signal d'horloge de programmation |
| | 5 | **RESET** | PC6 | Broche 29 | Reset Actif-Bas | Ligne de reset pilotée par programmateur |
| | 6 | **GND** | — | — | Masse (GND) | Référence de masse programmateur |

---

## 🔬 Points de Test Matériels & Diagnostic Laboratoire (`TP1` – `TP15`)

Pour faciliter les mesures à l'oscilloscope, le diagnostic au multimètre et les séances de travaux pratiques (TP d'électronique), la Cave Uno intègre **15 pastilles de test CMS** (diamètre Ø 1.0 mm dorées ENIG sur la face supérieure `F.Cu`) :

| Point de Test | Sérigraphie / Valeur | Net Schématique | Signal / Tension Nominale | Rôle & Utilisation en Laboratoire |
|:---:|:---:|:---|:---:|:---|
| **TP1** | `USBVCC` | `USBVCC` | +5.0V DC | Tension brute $V_{BUS}$ issue du port USB-C (en amont de la diode idéale `U3`) |
| **TP2** | `VOUT` | `VOUT` | +5.0V DC | Sortie régulée du convertisseur Buck synchrone `U4` (`AP63205`, en amont de la diode idéale `U2`) |
| **TP3** | `+5V` | `+5V` | +5.0V DC | Rail système principal `+5V` (en aval de l'étage de couplage OR-ing à diodes idéales `U2`/`U3`) |
| **TP4** | `CE` | `Net-(U2-ST)` | Signal Logique | Ligne d'interverrouillage et d'état (`ST`/`CE`) entre les contrôleurs de diodes idéales `U2` et `U3` |
| **TP5** | `VCC` | `VCC` | 7V – 18V DC | Tension d'entrée DC protégée contre les inversions de polarité (en aval de `D1`, entrée de `U4`) |
| **TP6** | `VIN` | `Net-(D1-A)` | 7V – 18V DC | Tension d'entrée brute sur le connecteur Jack DC `U1` (en amont de la diode de protection `D1`) |
| **TP7** | `RX` | `D0` | UART TTL 5V | Ligne de réception série matérielle principale (`RX0` / `PD0`) entre le `CH9101R` et l'`ATmega328PB` |
| **TP8** | `TX` | `D1` | UART TTL 5V | Ligne d'émission série matérielle principale (`TX0` / `PD1`) entre l'`ATmega328PB` et le `CH9101R` |
| **TP9** | `GND` | `GND` | 0V (Masse) | Pastille de masse de référence (zone Alimentation / Analogique) pour pince de sonde d'oscilloscope |
| **TP10** | `GND` | `GND` | 0V (Masse) | Pastille de masse de référence (zone USB / Numérique) pour pince de sonde d'oscilloscope |
| **TP11** | `+3.3V` | `+3.3V` | +3.3V DC | Sortie régulée +3.3V faible bruit issue du LDO `U7` (`AP2112K-3.3`, 600 mA max) |
| **TP12** | `VDD` | `VDD` | +5.0V ou +3.3V | Rail d'alimentation logique commutable sélectionné via l'interrupteur à glissière `SW1` |
| **TP13** | `RESET` | `RESET` | +5.0V (Actif-Bas) | Ligne de Reset matériel du MCU (`PC6`) et observation de l'impulsion d'auto-reset capacitif DTR |
| **TP14** | `RX_LED` | `RX_LED` | Actif-Bas | Commande de la LED d'activité de réception série du pont USB-UART (`U6` `CH9101R`) |
| **TP15** | `TX_LED` | `TX_LED` | Actif-Bas | Commande de la LED d'activité d'émission série du pont USB-UART (`U6` `CH9101R`) |

---

## 🛠️ Configuration Logicielle (Arduino IDE & MiniCore)

La **Cave Uno** fonctionne immédiatement avec l'Arduino IDE, PlatformIO, VS Code et les chaînes de compilation AVR-GCC standards.

### 1. Installation du gestionnaire de cartes (MiniCore)

Pour exploiter l'ensemble des registres et périphériques matériels supplémentaires de l'**ATmega328PB** (notamment `Wire1`, `SPI1`, et les broches `PE0`/`PE1`), il est recommandé d'utiliser le core open-source **MiniCore** :

1. Ouvrez l'**Arduino IDE**, puis rendez-vous dans **Fichier → Préférences**.
2. Dans le champ **URL de gestionnaires de cartes supplémentaires**, insérez l'URL :
   ```
   https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json
   ```
3. Rendez-vous dans **Outils → Type de carte → Gestionnaire de carte...**, recherchez `MiniCore` par MCUdude, et cliquez sur **Installer**.
4. Configurez ensuite vos options sous le menu **Outils** :
   * **Type de carte :** `ATmega328`
   * **Variante :** `328PB`
   * **Horloge :** `External 16 MHz`
   * **BOD :** `2.7V` (ou `4.3V` pour tolérance stricte 5V)
   * **Compiler LTO :** `Enabled`
   * **Port :** Sélectionnez le port série USB CH9101 automatiquement détecté.

---

### 2. Exemples de Code Prêts à l'Emploi

#### Démonstration du Double Bus I2C Matériel
```cpp
#include <Wire.h>

void setup() {
  Serial.begin(115200);
  
  // Initialisation du bus I2C principal (A4/A5 et connecteur J7)
  Wire.begin();
  
  // Initialisation du bus I2C secondaire indépendant (J3: PE0/PE1)
  Wire1.begin();
  
  Serial.println(F("Cave Uno - Double bus I2C matériel prêt !"));
}

void loop() {
  // Communication avec l'afficheur OLED sur Wire
  Wire.beginTransmission(0x3C);
  // ...
  Wire.endTransmission();

  // Communication avec un capteur d'accélération sur Wire1 sans conflit d'adresse
  Wire1.beginTransmission(0x68);
  // ...
  Wire1.endTransmission();
  
  delay(1000);
}
```

#### Pilotage de la LED RVB Intégrée WS2812B (`D23`)
```cpp
#include <Adafruit_NeoPixel.h>

#define RGB_PIN   23  // Broche PE0 / D23
#define NUMPIXELS 1

Adafruit_NeoPixel statusLed(NUMPIXELS, RGB_PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  statusLed.begin();
  statusLed.setBrightness(40);
}

void loop() {
  // Respiration orange (thème Cave Rover)
  statusLed.setPixelColor(0, statusLed.Color(249, 115, 22));
  statusLed.show();
  delay(800);
  
  statusLed.setPixelColor(0, statusLed.Color(0, 0, 0));
  statusLed.show();
  delay(200);
}
```

---

## ⚙️ Caractéristiques Électriques

| Grandeur | Min | Typique | Max | Unité | Remarques |
|:---|:---:|:---:|:---:|:---:|:---|
| **Tension d'entrée ($V_{IN}$ Jack DC)** | 7.0 | 9.0 – 12.0 | 18.0 | V | Fiche 5.5 × 2.1mm centre positif |
| **Alimentation USB ($V_{BUS}$)** | 4.75 | 5.0 | 5.25 | V | Port réversible Type-C |
| **Tension de fonctionnement interne ($V_{CC}$)** | 4.90 | 5.0 | 5.10 | V | Rail système principal |
| **Rail commutable ($V_{DD}$)** | — | 3.3 ou 5.0 | — | V | Sélection matérielle par `SW1` |
| **Courant continu max Buck AP63205** | — | — | 1.5 | A | Rendement élevé (> 90%) |
| **Courant continu max LDO 3.3V AP2112K**| — | — | 600 | mA | Ultra faible bruit ($V_{DROP} = 250\,\text{mV}$) |
| **Courant max par broche d'E/S** | — | — | 20.0 | mA | Limite absolue 40mA |
| **Courant total maximal MCU** | — | — | 200.0 | mA | Somme des courants $V_{CC}$ / GND |
| **Fréquence du quartz externe** | — | 16.0 | — | MHz | Oscillateur quartz $\pm 30\,\text{ppm}$ |

---

## 🏭 Recommandations de Fabrication PCB & Aperçu Carte Nue

Le circuit imprimé est conçu sous **KiCad 10** en 2 couches FR4 avec passage sans avertissement du DRC (0 erreur, 0 net non routé).

* **Dimensions de la carte :** 68.6 mm × 53.4 mm (gabarit standard Arduino Uno R3).
* **Empilement :**
  * Face supérieure : Cuivre 35 µm (1 oz) (`F.Cu`)
  * Diélectrique : Cœur FR4 1.5 mm ($\varepsilon_r \approx 4.5$)
  * Face inférieure : Cuivre 35 µm (1 oz) (`B.Cu`)
* **Finition recommandée :** **ENIG** (Or immersion chimique) pour garantir une coplanarité optimale des pastilles QFN-32 et TSOT-23.
* **Vernis épargne :** Noir mat / Anthracite (`#1c1d21`).
* **Sérigraphie :** Blanc haute définition (`#f4f5f7`).
* **Largeur / Espacement minimal des pistes :** 0.15 mm / 0.15 mm (6/6 mil).

![Bannière PCB Nu Cave Uno](cave_uno_banner_github.png)

---

## 🗺️ Ingénierie Européenne & Patrimoine Ardéchois

Le dos du PCB intègre un tracé topographique haute définition issu de relevés LiDAR aériens du **Pont d'Arc**, arche calcaire naturelle monumentale marquant l'entrée des Gorges de l'Ardèche et voisine de la **Grotte Chauvet** (joyau d'art pariétal préhistorique classé au patrimoine mondial de l'UNESCO).

* **Coordonnées géographiques :** $44^{\circ}\,23'\,15''\,\text{N},\ 04^{\circ}\,24'\,59''\,\text{E}$
* **Traitement vectoriel :** Interpolation de splines sans facettage, avec soustraction automatique des ouvertures de vernis pour préserver les plages d'accueil dorées.

![Face arrière Cave Uno](cave_uno_face_arriere_github.png)

---

## 📜 Nomenclature des Composants Clés (BOM)

| Référence | Désignation | Boîtier | Rôle & Fonction |
|:---|:---|:---|:---|
| **U8** | ATmega328PB-MN / AU | QFN-32 (5×5mm) | Microcontrôleur AVR 8-bits @ 16 MHz |
| **U4** | AP63205WU-7 | TSOT-23-6 | Régulateur Buck synchrone 5V / 1.5A |
| **U7** | AP2112K-3.3TRG1 | SOT-25-5 | Régulateur LDO faible bruit 3.3V / 600mA |
| **U2, U3** | LM66100DCKR | SC-70-6 | Contrôleurs de diode idéale (OR-ing d'alimentation) |
| **U6** | CH9101R | QSOP-16 | Pont USB-UART natif sans pilote |
| **U5** | USBLC6-2SC6 | SOT-23-6 | Réseau de protection TVS ESD double ligne |
| **USB1** | GT-USB-7025 | USB-C SMD | Connecteur réversible USB Type-C |
| **U1** | XDJK-0051-025 | THT Jack DC | Embase d'alimentation Jack DC 5.5 × 2.1mm |
| **LED1** | WS2812B-2020-V6 | 2020 SMD | LED RVB adressable intelligente (`D23`) |
| **SW1** | K3-1296S-J1 | Glissière SMD | Sélecteur de tension VDD (5V / 3.3V) |
| **SW2** | Bouton poussoir 4 broches | 5.2×5.2mm | Bouton poussoir de Reset actif à l'état bas |

---

## 📄 Licences & Propriété Intellectuelle

* **Conception Matérielle (Schémas & Routage) :** Sous licence [CERN-OHL-P v2](https://ohwr.org/cern_ohl_p_v2.txt) (CERN Open Hardware Licence - Permissive).
* **Documentation & Visuels :** Sous licence [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).
* **Ingénierie & Design :** **Cave Rover** (Europe, 2026).
