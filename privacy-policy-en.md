# Privacy Policy

**Adhan Assistant - Alexa Skill**

---

## Controller

**Data Controller:**  
Adhan Assistant  
Contact: [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

**Legal Basis for Processing:**
- Art. 6(1)(b) GDPR (Contract performance: Skill functionality)
- Art. 6(1)(a) GDPR (Consent: Permission for reminders)

---

## 1. What Data is Processed?

The skill processes and stores **only data necessary for the skill's functionality**. This includes:

- **Selected language** (German, English, or Turkish)
- **Country and city**, plus the **coordinates and time zone of the city** derived from them (for prayer time calculation)
- **Selected prayer calculation method** (e.g., Diyanet, Muslim World League, ISNA)
- **Reminder settings** (with or without spoken Adhan/Ezan, iftar dua yes/no)
- **Technical identifiers of the created reminders** (so they can be changed or deleted later)
- **Cached prayer times** for the selected city (at most 3 months)

This data is stored in **Amazon DynamoDB** to accurately calculate prayer times and create automatic reminders (about 10 days in advance).

### What is NOT Processed

The skill does **not process sensitive personal data** such as:
- Name
- Email address
- Phone number
- Home address (only city and country are stored; the device address is not requested)
- Health data
- Detailed user profiles

**No personal or religious profiling** takes place. No behavioral data, usage statistics, or tracking information is collected.

---

## 2. Permissions and Device Information

The skill requires the following Alexa permissions for certain functions:

### 2.1 Alexa Reminders (`alexa::alerts:reminders:skill:readwrite`)

This permission is required for:
- Creating automatic prayer reminders (Fajr, Dhuhr, Asr, Maghrib, Isha)
- Creating Ramadan reminders (Suhoor, Iftar)
- Creating Friday reminders
- Creating Islamic holiday reminders
- Updating and deleting existing reminders

**Important:** Reminders can be deleted at any time via the Alexa app or by using the skill command "set new prayer times."

Users can grant this permission by voice and revoke it at any time in the Alexa app.

### 2.2 No Device Address

The skill does **not request the device address**. Country and city are provided by the user.

---

## 3. External Services

### 3.1 Prayer Times API (AlAdhan)

For prayer time calculation, the skill uses the free public API from **AlAdhan**:

- **Service:** [https://api.aladhan.com/v1](https://api.aladhan.com/v1)
- **Purpose:** Calculation of prayer times based on geographic coordinates and calculation methods

**Data Transmitted:**
- Coordinates of the selected city (e.g., 49.14 / 9.22 for Heilbronn)
- Calculation method (e.g., "13" for Diyanet)
- Date and month (for calendar queries)

**Not Transmitted:**
- Names
- Contact details
- Complete addresses
- Device IDs or user IDs

**Privacy:** According to their statements, AlAdhan does not store personal data from API requests. More information: [AlAdhan Privacy](https://aladhan.com/privacy-policy)

### 3.2 Location Search (Open-Meteo, OpenStreetMap Nominatim)

To convert the city name into coordinates and a time zone, the **city name and country** are sent **once during setup or when the city is changed** to:

- **Open-Meteo Geocoding API** ([open-meteo.com](https://open-meteo.com/)) – primary
- **OpenStreetMap Nominatim** ([nominatim.openstreetmap.org](https://nominatim.openstreetmap.org/)) – only if Open-Meteo is unavailable

No user or device IDs are transmitted.

**Attribution:** Geodata from [Open-Meteo.com](https://open-meteo.com/) (CC BY 4.0) and © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) (ODbL).

### 3.3 Amazon Web Services (AWS)

The skill is hosted on **Amazon Web Services**:

- **Lambda (EU-West-1, US-East-1, US-West-2):** Skill logic
- **DynamoDB:** Storage of user settings (city, country, method, language)
- **S3 (EU-West-1):** MP3 files for Adhan/Ezan playback

AWS processes data according to [AWS Data Privacy](https://aws.amazon.com/compliance/data-privacy/) guidelines and acts as a data processor under GDPR.

---

## 4. Religious Content (Hadith)

Hadith content comes from recognized collections (Sahih al-Bukhari, Sahih Muslim, Jami' at-Tirmidhi, Sunan Abi Dawud) and is provided with source references as **our own translations of the meaning**, **stored locally** (within the Lambda function).

**Important:**
- **No external Hadith APIs** are used.
- **No translation services** are used.
- **No Hadith texts or religious content are transmitted to third parties**.
- Hadith texts are **randomly selected** and included in reminders.

The translations convey the meaning and are not word-for-word quotations of a specific translation.

---

## 5. Is Data Shared with Third Parties?

**No.**

The skill does not use:
- **Advertising services**
- **Tracking services** (e.g., Google Analytics, Facebook Pixel)
- **Analytics services**
- **Profiling technologies**

**No sharing of personal data with third parties for advertising or profiling purposes** takes place.

### Technical Service Providers (Data Processors)

As part of technical provision, the following services are used:

- **Amazon Web Services (AWS):** Hosting, Lambda, DynamoDB, S3
- **AlAdhan API:** Prayer time calculation (only the city's coordinates transmitted)
- **Open-Meteo / OpenStreetMap Nominatim:** Location search (only city name and country transmitted)

These services process data exclusively as data processors under GDPR.

---

## 6. Data Storage and Deletion

### 6.1 Storage Duration

Stored settings (city, country, method, language, reminder settings) remain until the user:

- Deletes prayer reminders (voice command: "delete the reminders") or resets the setup ("reset setup"),
- Reconfigures settings in the skill,
- Deactivates or uninstalls the skill, or
- Requests deletion via email.

**Reminders:** Alexa reminders are created for **about 10 days in advance** and are automatically deleted by Amazon after expiration.

### 6.2 Automatic Deletion

After **uninstalling the skill**:
- No further data is processed by the skill
- DynamoDB entries initially remain (for reinstallation)
- Alexa reminders are automatically deleted by Amazon (after expiration)

### 6.3 Manual Deletion

Users can at any time:
- Use the voice command **"delete the reminders"** to delete all reminders, or **"reset setup"** to reset all settings
- Request **complete deletion of all data** by contacting via email (see below)

---

## 7. Your Rights Under GDPR

You have the following rights regarding your data:

### 7.1 Right of Access (Art. 15 GDPR)
You can request information about stored data (city, country, method, language, reminder settings).

### 7.2 Right to Rectification (Art. 16 GDPR)
You can request correction of incorrect data (also via the skill, e.g. "set the city to London" or "reset setup").

### 7.3 Right to Erasure (Art. 17 GDPR)
You can request complete deletion of your data.

### 7.4 Right to Object (Art. 21 GDPR)
You can object to processing (practically: uninstall skill).

### 7.5 Right to Data Portability (Art. 20 GDPR)
You can receive your data in structured format (JSON export upon request).

### Exercising Your Rights

To exercise your rights, please contact:

**Email:** [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

**Required Information for Access/Deletion:**
- Your Alexa User ID (available in Alexa app under Settings → Privacy)
- Or: Period of use + approximate city

We respond within **48 hours** and implement legitimate requests **immediately** (maximum 30 days according to Art. 12(3) GDPR).

### 7.6 Right to Lodge a Complaint

You have the right to lodge a complaint with a **data protection supervisory authority** regarding our processing of your personal data.

**Competent Authority in Germany:**  
The Federal Commissioner for Data Protection and Freedom of Information (BfDI)  
[https://www.bfdi.bund.de](https://www.bfdi.bund.de)

---

## 8. Security Measures

To protect your data, we implement the following measures:

- **Encryption:** HTTPS/TLS for all API connections
- **AWS Security:** DynamoDB with IAM permissions, no public access
- **Minimization:** Only necessary data is stored
- **No Access:** Developers have no direct access to production user data (only aggregated logs)

---

## 9. Contact

For questions about data protection or data processing:

**Adhan Assistant**  
Email: [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

We strive to respond to inquiries within **48 hours**.

---

## 10. Changes to This Privacy Policy

This privacy policy may be updated in case of functionality changes, legal requirements, or technical infrastructure changes.

The **current version** is always available at:  
[https://karaadhanassistant.github.io/adhan-assistant-legal/privacy-policy-en.md](https://karaadhanassistant.github.io/adhan-assistant-legal/privacy-policy-en.md)

For significant changes, users will be informed via the Alexa app or skill announcement.

---

**Last Updated:** October 27, 2026

---

[Deutsche Version](privacy-policy-de.md) | [Terms of Use](terms-en.md) | [Home](README.md)
