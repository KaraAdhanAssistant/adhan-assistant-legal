# Terms of Use

**Adhan Assistant - Alexa Skill**

---

These terms of use apply to the Alexa Skill **Adhan Assistant** and all associated services.

By using the skill, you agree to these terms.

---

## 1. Purpose and Functionality

The skill serves to provide prayer times, create automatic prayer reminders, and deliver religious reminder content.

### 1.1 Core Features

- **Prayer Times:** Display and query of prayer times (Fajr, Dhuhr, Asr, Maghrib, Isha)
- **Automatic Reminders:** Prayer reminders (optionally with spoken Adhan/Ezan via text-to-speech)
- **MP3 Playback:** Adhan/Ezan playback on request (separate feature via voice command)
- **Religious Reminders:** Output of short religious reminders (Hadith from recognized collections with source references, translated in meaning)
- **Islamic Holidays:** Reminders for Ramadan (Suhoor, Iftar), Friday, and special Islamic nights

### 1.2 Supported Calculation Methods

The skill supports 14 internationally recognized prayer calculation methods, including:
- Diyanet (Turkey)
- Muslim World League
- ISNA (Islamic Society of North America)
- Umm al-Qura (Saudi Arabia)
- Egyptian General Authority of Survey
- And more (see skill description)

### 1.3 Supported Languages

- **Skill Interface:** German, English
- **Voice Commands:** German, English, Turkish (independent of skill language setting)

All content serves to support daily religious practice and personal reminders.

---

## 2. Religious Content and Disclaimer

### 2.1 Hadith Content

Hadith texts provided in the skill come from recognized collections (Sahih al-Bukhari, Sahih Muslim, Jami' at-Tirmidhi, Sunan Abi Dawud) and are given with source references as **our own translations of the meaning**.

**This content:**
- Serves exclusively for religious inspiration and reminders
- Is **not a word-for-word quotation** of a specific translation
- Does **not represent theological interpretation**
- Does **not represent binding religious guidance**
- Is **not scholarly references**
- Does **not replace** consultation of primary sources (Quran, authentic Hadith collections)

### 2.2 Theological Responsibility

For binding religious information, fatwas, or theological questions, please consult:
- Qualified Islamic scholars
- Recognized Islamic institutions
- Local mosques and community centers

---

## 3. Prayer Times: Disclaimer and Accuracy

### 3.1 No Guarantee of Accuracy

Use of the skill is **at your own risk**.

Prayer times are calculated using **internationally recognized calculation methods** but may **differ** from local mosques, religious authorities, or regional traditions.

**No warranty is provided** for:
- Absolute accuracy of prayer times
- Agreement with local mosque times
- Accuracy at extreme geographic latitudes (e.g., polar regions)
- Consideration of local adjustments (e.g., manual corrections by communities)

### 3.2 Technical Limitations

Prayer times are based on:
- **Geographic coordinates** (city/country via AlAdhan API)
- **Astronomical calculations** (sun position)
- **Selected calculation method** (e.g., Diyanet, MWL)

**Possible deviations due to:**
- Inaccuracies in geocoding API
- Different interpretations of Fajr/Isha angles
- Local visibility conditions (horizon, topography)
- Daylight saving time changes (automatically considered, but delays possible)

### 3.3 Recommendation

**Please verify prayer times** with local sources, especially:
- For critical prayers (e.g., Fajr start)
- In new cities
- During Ramadan

---

## 4. Reminders: Technical Availability

### 4.1 No Delivery Guarantee

The skill creates Alexa reminders via the Amazon Reminders API. **No guarantee** that:
- Reminders are delivered on time
- Reminders are delivered later if device is offline
- Reminders work during Amazon server issues

### 4.2 Possible Limitations

**Reminders may fail or be delayed due to:**
- Internet connection problems
- Alexa device is turned off or muted
- Amazon server maintenance
- Exceeding Alexa reminder limits (max. 100 active reminders per skill)
- Technical errors in Alexa infrastructure

### 4.3 Reminder Limit

Alexa only allows skills to create new reminders while the skill is being used. The skill therefore creates reminders for **about 10 days in advance** and extends them automatically whenever the skill is opened.

**Important:** Users should open the skill about **once a week**. The skill reminds users in good time before the reminders run out.

### 4.4 Turkish Language Output

Turkish is currently **not an officially supported system language of Amazon Alexa**.

**Therefore:**
- Pronunciation of Turkish content may differ from natural speech
- Text-to-speech (TTS) for Turkish is limited
- Content is still delivered correctly and serves for religious reminders

---

## 5. General Disclaimers

### 5.1 "As-Is" Provision

The skill is provided **free of charge** and **without warranty**.

The content and calculations provided serve exclusively for **informational and inspirational purposes** and do not constitute **religious, legal, medical, or other advice**.

### 5.2 Limitation of Liability

Liability for damages arising from the use or non-use of the skill is **excluded** to the extent legally permissible.

This applies in particular to:
- Missed prayer times due to technical errors
- Inaccuracies in calculations or religious content
- Damages due to misinterpretation of religious content
- Data loss
- Indirect damages or consequential damages

**Exception:** Liability for intent, gross negligence, or injury to life, body, or health remains unaffected.

### 5.3 External Services

The skill uses external APIs (e.g., AlAdhan). **Failures, errors, or changes** to these services are beyond our control and do not establish liability.

---

## 6. Technical Availability and Maintenance

### 6.1 No Availability Guarantee

The skill is provided **without guarantee of permanent availability**.

**No guarantee** that the skill is available at all times without errors or interruptions.

### 6.2 Possible Limitations

The following factors may temporarily limit functionality:
- Technical changes or updates
- Maintenance (Lambda, DynamoDB, S3)
- External dependencies (AlAdhan API, Amazon Alexa Platform)
- Device-specific limitations (older Alexa devices)
- Changes in Alexa Skills Kit API

---

## 7. Changes and Discontinuation of Skill

### 7.1 Functional Changes

The skill's functionality may be **changed, expanded, restricted, or discontinued at any time** without prior notice.

### 7.2 No Entitlement to Features

There is **no legal entitlement** to:
- Specific features
- Permanent availability of individual content
- Continuation of the skill
- Updates or bug fixes

### 7.3 Discontinuation

The skill may be discontinued at any time by the developer or Amazon, e.g., due to:
- Technical or legal issues
- Changes to Amazon policies
- Economic reasons

**Upon discontinuation:** Users will be informed via the Alexa app if possible. Stored data will be deleted according to the privacy policy.

---

## 8. Usage Requirements

To use the skill, the following are required:

- An **Amazon Alexa-enabled device** (Echo, Echo Dot, Echo Show, etc.)
- An **active Amazon account**
- **Internet connection** (Wi-Fi)
- Optional: **Permission** for reminders (for automatic reminders)

---

## 9. Intellectual Property

### 9.1 Copyright

The skill's code and original texts are protected by copyright. The hadith texts are our own translations of the meaning. The audio recording (MP3 Adhan) is subject to the rights of its rights holder.

### 9.2 Permitted Use

Users may use the skill **exclusively for personal, non-commercial purposes**.

**Prohibited:**
- Decompilation or reverse engineering
- Commercial use without permission
- Redistribution of content
- Automated mass queries

---

## 10. Changes to These Terms of Use

These terms of use may be updated in case of functionality changes, legal requirements, or technical infrastructure changes.

The **current version** is always available at:  
[https://karaadhanassistant.github.io/adhan-assistant-legal/terms-en.md](https://karaadhanassistant.github.io/adhan-assistant-legal/terms-en.md)

For significant changes, users will be informed via the Alexa app.

---

## 11. Contact

For questions about these terms of use or the skill:

**Adhan Assistant**  
Email: [kara.adhan.assistant@gmail.com](mailto:kara.adhan.assistant@gmail.com)

We strive to respond to inquiries within **48 hours**.

---

**Last Updated:** October 27, 2026

---

[Deutsche Version](terms-de.md) | [Privacy Policy](privacy-policy-en.md) | [Home](README.md)
