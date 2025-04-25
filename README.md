# Anki + AnkiConnect + Yomitan Setup Guide  
_For Japanese Study – Step-by-Step_

---

## Introduction

This guide will walk you through setting up a powerful Japanese study workflow using Anki, AnkiConnect, Yomitan, and subtitle mining tools. With this setup, you can quickly make custom flashcards from words you find in your browser or in anime subtitles, all connected seamlessly to your Anki decks.

_Some steps may look a bit technical, but take them one at a time and you’ll be good!_

---

## 1. Prepare Anki

### a. Install AnkiConnect

- Open Anki.
- Go to **Tools → Add-ons → Get Add-ons…**
- Paste this code: **2055492159** and click "OK".
- Restart Anki.

### b. Create/Set Up Your Yomitan Note Type

- Go to **Tools → Manage Note Types**.
- Click **Add → Add: Basic** (or similar) and name it **Yomitan** (or whatever you want).
- Select your note type and click **Fields**.
- Add these fields (one per line):

- Click **Save**.

> ![Screenshot of Anki fields setup](./anki-fields-setup.png)  
> *Example: How your Anki fields setup should look*

### c. Configure Card HTML

#### Front template:

```html
<div style="margin-top: 60px; text-align: center;">
<div style='font-family: BIZ UDGothic; font-size: 48px;'>{{Front}}</div>
<br>
{{#Sentence}}
<div style='font-family: BIZ UDGothic; font-size: 24px;'>{{Sentence}}</div>
{{/Sentence}}
</div>


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
  <!-- Full Glossary Output (Styled for readability) -->
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

