# Anki + AnkiConnect + Yomitan Setup Guide  
_For Japanese Study – Step-by-Step_

---

## Introduction

This guide will walk you through setting up a powerful Japanese study workflow using **Anki**, **AnkiConnect**, **Yomitan**, and subtitle mining tools (**ManabiDojo**). With this setup, you can easily create custom flashcards from your browser or anime subtitles.

*Some steps might seem technical, but just take your time, and you'll get it!*

---

## Step 1: Prepare Anki

### 1.1 Install AnkiConnect
- Open Anki.
- Go to **Tools → Add-ons → Get Add-ons…**
- Paste this code: **2055492159** and click **OK**.
- Restart Anki.

### 1.2 Create Your Yomitan Note Type
- Go to **Tools → Manage Note Types**.
- Click **Add → Add: Basic** and name it **Yomitan**.
- Select your note type and click **Fields**.
- Add these fields exactly as listed below:


> ![Anki fields setup example](anki-fields-setup.png)  
> **Example**: Your Anki fields should look similar to this screenshot.

### 1.3 Configure Card HTML Templates and CSS
**Tools → Manage Note Types** and click on your new **Yomitan card type → Cards**
Copy the following templates into your Anki cards setup:

### **Front Template:**
```html
<div style="margin-top: 60px; text-align: center;">
  <div style='font-family: BIZ UDGothic; font-size: 48px;'>{{Front}}</div>
  <br>
  {{#Sentence}}
    <div style='font-family: BIZ UDGothic; font-size: 24px;'>{{Sentence}}</div>
  {{/Sentence}}
</div>

```
### **Back Template:** 

```html
<div style="margin-top: 60px; text-align: center;">
  <!-- Reading -->
  <div style='font-family: BIZ UDGothic; font-size: 48px;'>{{Reading}}</div>
  {{#Sentence}}
    <div style='font-family: BIZ UDGothic; font-size: 24px; margin-top: 10px;'>{{Sentence}}</div>
  {{/Sentence}}
  {{#Audio}}
    <div style='margin-top: 20px;'>{{Audio}}</div>
  {{/Audio}}
  <hr id="answer">
  <!-- Glossary Output -->
  {{#Back}}
    <div style='font-family: BIZ UDGothic; font-size: 20px; text-align: left; white-space: pre-wrap;'>{{Back}}</div>
  {{/Back}}
  <!-- Cloze-style sentence -->
  {{#Sentence no word}}
    <div style='font-family: BIZ UDGothic; font-size: 20px; margin-top: 20px;'>{{Sentence no word}}</div>
  {{/Sentence no word}}
  <!-- Frequency -->
  {{#Frequency}}
    <div style='font-family: BIZ UDGothic; font-size: 18px; margin-top: 10px;'>{{Frequency}}</div>
  {{/Frequency}}
</div>

```
### **CSS Template:** 

```css
.card {
  font-family: 'BIZ UDGothic', sans-serif;
  font-size: 20px;
  text-align: center;
  color: black;
  background-color: white;
}
hr#answer {
  margin: 30px auto;
  width: 50%;
  border: 1px solid #ccc;
}
```

## Step 2: Set Up Yomitan (Chrome Extension)

### 2.1 Install Yomitan

- Install the extension from the [Yomitan Chrome Web Store](https://chrome.google.com/webstore/detail/yomitan/jipdnfibhldikgcjhfnomkfpcebammhp).

### 2.2 Import Dictionaries

- Click the Yomitan icon in Chrome and go to **Settings → Backup**.
- Download the [Yomitan Dictionaries Bundle](https://drive.google.com/file/d/1ExmPI7cDwWpsCO6g8YBslAAdF92BwJqx/view?usp=sharing).
- Import the file using Yomitan’s import feature.
- **Enable dictionaries** at the top of the page.
  - *(If you don’t want native Japanese definitions, uncheck the one labeled "Japanese".)*

### 2.3 Configure Anki Integration

- Open Yomitan Settings and navigate to the **Anki** tab.
- Ensure Anki is open with AnkiConnect running.
- Use the following settings for field mappings:

| Anki Field          | Yomitan Value             |
|---------------------|---------------------------|
| Front               | `{expression}`            |
| Back                | `{glossary}`              |
| dictionary          | `{dictionary}`            |
| Audio               | `{audio}`                 |
| Add Reverse         | *(Some of this works, not too sure why. Don't mess with it.)* |
| Sentence            | `{sentence}`              |
| Sentence no word    | `{pitch-accent-graphs}`   |
| Reading             | `{reading}`               |
| Frequency           | `{frequencies}`           |

> ![Yomitan Anki mapping screenshot 1](yomitan-mapping-1.png)  
> **Example**: Yomitan field mapping (part 1)

> ![Yomitan Anki mapping screenshot 2](yomitan-mapping-2.png)  
> **Example**: Yomitan field mapping (part 2)

---

## Step 3: Set Up ManabiDojo (Crunchyroll Subtitle Miner)

- Install **ManabiDojo** from the [Chrome Web Store](https://chromewebstore.google.com/detail/manabidojo-learn-japanese/efbhkecfjhcpmepgbpogiiaidkmjhojl).
- Once installed, subtitles can be clicked directly within Crunchyroll videos to create Anki cards automatically.
- If Crunchyroll does not have Japanese subtitles for a particular anime, download subtitles from [kitsunekko.net](https://kitsunekko.net/dirlist.php?dir=subtitles%2Fjapanese%2F).
- Upload these manually into the ManabiDojo interface (bottom right of your Crunchyroll video).

---

## Final Tips

- Ensure **Anki is open** when sending cards from Yomitan or ManabiDojo.
- If you encounter issues, verify AnkiConnect is active and not blocked by antivirus or firewall.
- Confirm all field names and mappings exactly match those in Anki.
- For troubleshooting, search your specific issue online or consult Japanese-learning community forums.



