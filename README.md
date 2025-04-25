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
