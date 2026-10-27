# Datenschutzerklärung

**Adhan Assistant - Alexa Skill**

---

## Verantwortlicher

**Verantwortlich für die Datenverarbeitung:**  
Adhan Assistant  
Kontakt: [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

**Rechtsgrundlage der Verarbeitung:**
- Art. 6 Abs. 1 lit. b) DSGVO (Vertragserfüllung: Skill-Funktion)
- Art. 6 Abs. 1 lit. a) DSGVO (Einwilligung: Berechtigung für Erinnerungen)

---

## 1. Welche Daten werden verarbeitet?

Der Skill verarbeitet und speichert **ausschließlich solche Daten, die für die Funktion des Skills notwendig sind**. Dazu gehören:

- **ausgewählte Sprache** (Deutsch, Englisch oder Türkisch)
- **Land und Stadt** sowie die daraus ermittelten **Koordinaten und Zeitzone der Stadt** (für die Gebetszeitberechnung)
- **gewählte Gebetsberechnungsmethode** (z. B. Diyanet, Muslim World League, ISNA)
- **Einstellungen zu Gebetserinnerungen** (mit oder ohne gesprochenen Adhan/Ezan, Iftar-Dua ja/nein)
- **technische Kennungen der angelegten Erinnerungen** (damit sie später geändert oder gelöscht werden können)
- **zwischengespeicherte Gebetszeiten** der eingestellten Stadt (höchstens 3 Monate)

Diese Daten werden in **Amazon DynamoDB** gespeichert, um Gebetszeiten korrekt zu berechnen und automatische Erinnerungen (etwa 10 Tage im Voraus) bereitzustellen.

### Was wird NICHT verarbeitet

Der Skill verarbeitet **keine sensiblen personenbezogenen Daten** wie:
- Name
- E-Mail-Adresse
- Telefonnummer
- Wohnadresse (es werden nur Stadt und Land gespeichert; die Geräteadresse wird nicht abgefragt)
- Gesundheitsdaten
- detaillierte Nutzerprofile

Es findet **keine Erstellung eines personenbezogenen oder religiösen Profils** statt. Es werden keine Verhaltensdaten, Nutzungsstatistiken oder Tracking-Informationen erhoben.

---

## 2. Berechtigungen und Geräteinformationen

Für bestimmte Funktionen benötigt der Skill folgende Alexa-Berechtigungen:

### 2.1 Alexa-Erinnerungen (`alexa::alerts:reminders:skill:readwrite`)

Diese Berechtigung wird benötigt zur:
- Erstellung automatischer Gebetserinnerungen (Fajr, Dhuhr, Asr, Maghrib, Isha)
- Erstellung von Ramadan-Erinnerungen (Sahur, Iftar)
- Erstellung von Freitags-Erinnerungen
- Erstellung von Erinnerungen an islamische Feiertage
- Aktualisierung und Löschung bestehender Erinnerungen

**Wichtig:** Erinnerungen können jederzeit in der Alexa App oder durch den Skill-Befehl „neue Gebetszeiten einstellen" gelöscht werden.

Die Berechtigung kann der Nutzer per Sprache erteilen oder in der Alexa App jederzeit widerrufen.

### 2.2 Keine Geräteadresse

Der Skill fragt **keine Geräteadresse** ab. Land und Stadt werden vom Nutzer selbst genannt.

---

## 3. Externe Dienste

### 3.1 Gebetszeiten-API (AlAdhan)

Zur Berechnung der Gebetszeiten nutzt der Skill die öffentliche, kostenlose API von **AlAdhan**:

- **Dienst:** [https://api.aladhan.com/v1](https://api.aladhan.com/v1)
- **Zweck:** Berechnung von Gebetszeiten basierend auf geografischen Koordinaten und Berechnungsmethoden

**Übermittelte Daten:**
- Koordinaten der eingestellten Stadt (z. B. 49,14 / 9,22 für Heilbronn)
- Berechnungsmethode (z. B. „13" für Diyanet)
- Datum und Monat (für Kalenderabfragen)

**Nicht übermittelt werden:**
- Namen
- Kontaktdaten
- Vollständige Adressen
- Geräte-IDs oder Nutzer-IDs

**Datenschutz:** AlAdhan speichert nach eigenen Angaben keine personenbezogenen Daten aus API-Anfragen. Weitere Informationen: [AlAdhan Privacy](https://aladhan.com/privacy-policy)

### 3.2 Ortssuche (Open-Meteo, OpenStreetMap Nominatim)

Um die genannte Stadt in Koordinaten und Zeitzone umzuwandeln, wird **einmalig bei der Einrichtung bzw. Änderung der Stadt** der **Name der Stadt und das Land** an folgende Dienste übermittelt:

- **Open-Meteo Geocoding API** ([open-meteo.com](https://open-meteo.com/)) – vorrangig
- **OpenStreetMap Nominatim** ([nominatim.openstreetmap.org](https://nominatim.openstreetmap.org/)) – nur falls Open-Meteo nicht erreichbar ist

Es werden keine Nutzer- oder Geräte-IDs übermittelt.

**Quellenangabe:** Geodaten von [Open-Meteo.com](https://open-meteo.com/) (CC BY 4.0) und © [OpenStreetMap-Mitwirkende](https://www.openstreetmap.org/copyright) (ODbL).

### 3.3 Amazon Web Services (AWS)

Der Skill wird auf **Amazon Web Services** gehostet:

- **Lambda (EU-West-1, US-East-1, US-West-2):** Skill-Logik
- **DynamoDB:** Speicherung der Nutzereinstellungen (Stadt, Land, Methode, Sprache)
- **S3 (EU-West-1):** MP3-Dateien für Adhan/Ezan-Wiedergabe

AWS verarbeitet Daten gemäß den [AWS Data Privacy](https://aws.amazon.com/de/compliance/data-privacy/) Richtlinien und fungiert als Auftragsverarbeiter im Sinne der DSGVO.

---

## 4. Religiöse Inhalte (Hadith)

Hadith-Inhalte stammen aus anerkannten Sammlungen (Sahih al-Buchari, Sahih Muslim, Jami' at-Tirmidhi, Sunan Abi Dawud), werden mit Quellenangabe als **eigene sinngemäße Übersetzungen** **lokal bereitgestellt** (innerhalb der Lambda-Funktion).

**Wichtig:**
- Es werden **keine externen Hadith-APIs** genutzt.
- Es werden **keine Übersetzungsdienste** verwendet.
- Es werden **keine Hadith-Texte oder religiösen Inhalte an Dritte übertragen**.
- Hadith-Texte werden **zufällig** ausgewählt und in Erinnerungen eingefügt.

Die Übersetzungen geben den Sinn wieder und sind keine wortgetreuen Zitate einer bestimmten Übersetzung.

---

## 5. Werden Daten an Dritte weitergegeben?

**Nein.**

Der Skill verwendet:
- **Keine Werbe-Dienste**
- **Keine Tracking-Dienste** (z. B. Google Analytics, Facebook Pixel)
- **Keine Analyse-Dienste**
- **Keine Profiling-Technologien**

Es findet **keine Weitergabe personenbezogener Daten an Dritte zu Werbezwecken oder für Profiling** statt.

### Technische Dienstleister (Auftragsverarbeiter)

Im Rahmen der technischen Bereitstellung werden folgende Dienste genutzt:

- **Amazon Web Services (AWS):** Hosting, Lambda, DynamoDB, S3
- **AlAdhan API:** Gebetszeiten-Berechnung (nur Koordinaten der Stadt übermittelt)
- **Open-Meteo / OpenStreetMap Nominatim:** Ortssuche (nur Stadtname und Land übermittelt)

Diese Dienste verarbeiten Daten ausschließlich im Rahmen der Auftragsverarbeitung gemäß DSGVO.

---

## 6. Speicherung und Löschung der Daten

### 6.1 Speicherdauer

Die gespeicherten Einstellungen (Stadt, Land, Methode, Sprache, Reminder-Einstellungen) bleiben so lange erhalten, bis der Nutzer:

- die Gebetserinnerungen löscht (Sprachbefehl: „Erinnerungen löschen") oder neu einrichtet („neu einrichten"),
- die Einstellungen im Skill neu konfiguriert,
- den Skill deaktiviert oder deinstalliert, oder
- die Löschung per E-Mail beantragt.

**Erinnerungen:** Alexa-Erinnerungen werden für **etwa 10 Tage im Voraus** erstellt und automatisch von Amazon nach Ablauf gelöscht.

### 6.2 Automatische Löschung

Nach der **Deinstallation des Skills** werden:
- Keine weiteren Daten durch den Skill verarbeitet
- DynamoDB-Einträge bleiben zunächst bestehen (für Reinstallation)
- Alexa-Erinnerungen automatisch von Amazon gelöscht (nach Ablauf)

### 6.3 Manuelle Löschung

Nutzer können jederzeit:
- Über den Sprachbefehl **„Erinnerungen löschen"** alle Erinnerungen löschen oder mit **„neu einrichten"** alle Einstellungen zurücksetzen
- Durch Kontaktaufnahme per E-Mail (siehe unten) die **vollständige Löschung aller Daten** veranlassen

---

## 7. Ihre Rechte nach DSGVO

Sie haben folgende Rechte bezüglich Ihrer Daten:

### 7.1 Auskunftsrecht (Art. 15 DSGVO)
Sie können Auskunft über gespeicherte Daten verlangen (Stadt, Land, Methode, Sprache, Reminder-Einstellungen).

### 7.2 Recht auf Berichtigung (Art. 16 DSGVO)
Sie können die Korrektur falscher Daten verlangen (auch per Skill, z. B. „stelle die Stadt auf Köln" oder „neu einrichten").

### 7.3 Recht auf Löschung (Art. 17 DSGVO)
Sie können die vollständige Löschung Ihrer Daten verlangen.

### 7.4 Recht auf Widerspruch (Art. 21 DSGVO)
Sie können der Verarbeitung widersprechen (praktisch: Skill deinstallieren).

### 7.5 Recht auf Datenübertragbarkeit (Art. 20 DSGVO)
Sie können Ihre Daten in strukturiertem Format erhalten (JSON-Export auf Anfrage).

### Ausübung Ihrer Rechte

Zur Ausübung Ihrer Rechte wenden Sie sich bitte an:

**E-Mail:** [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

**Erforderliche Angaben für Auskunft/Löschung:**
- Ihre Alexa-User-ID (abrufbar in der Alexa App unter Einstellungen → Datenschutz)
- Oder: Zeitraum der Nutzung + ungefähre Stadt

Wir antworten innerhalb von **48 Stunden** und setzen berechtigte Anfragen **unverzüglich** (maximal 30 Tage gemäß Art. 12 Abs. 3 DSGVO) um.

### 7.6 Beschwerderecht

Sie haben das Recht, sich bei einer **Datenschutz-Aufsichtsbehörde** über die Verarbeitung Ihrer personenbezogenen Daten durch uns zu beschweren.

**Zuständige Behörde in Deutschland:**  
Der Bundesbeauftragte für den Datenschutz und die Informationsfreiheit (BfDI)  
[https://www.bfdi.bund.de](https://www.bfdi.bund.de)

---

## 8. Sicherheitsmaßnahmen

Zum Schutz Ihrer Daten setzen wir folgende Maßnahmen ein:

- **Verschlüsselung:** HTTPS/TLS für alle API-Verbindungen
- **AWS-Sicherheit:** DynamoDB mit IAM-Berechtigungen, keine öffentlichen Zugriffe
- **Minimierung:** Nur notwendige Daten werden gespeichert
- **Kein Zugriff:** Entwickler haben keinen direkten Zugriff auf produktive Nutzerdaten (nur aggregierte Logs)

---

## 9. Kontakt

Bei Fragen zum Datenschutz oder zur Datenverarbeitung:

**Adhan Assistant**  
E-Mail: [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

Wir bemühen uns, Anfragen innerhalb von **48 Stunden** zu beantworten.

---

## 10. Änderungen dieser Datenschutzerklärung

Diese Datenschutzerklärung kann bei Änderungen der Funktionalität, rechtlicher Anforderungen oder technischer Infrastruktur angepasst werden.

Die **aktuelle Version** ist stets unter folgender URL verfügbar:  
[https://karaadhanassistant.github.io/adhan-assistant-legal/privacy-policy-de.md](https://karaadhanassistant.github.io/adhan-assistant-legal/privacy-policy-de.md)

Bei wesentlichen Änderungen werden Nutzer über die Alexa App oder per Skill-Ankündigung informiert.

---

**Stand:** 27. Oktober 2026

---

[English Version](privacy-policy-en.md) | [Nutzungsbedingungen](terms-de.md) | [Startseite](README.md)
