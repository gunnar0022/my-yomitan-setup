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
Copy the following templates into your Anki cards setup:

#### **Front Template:**
```html
<div style="margin-top: 60px; text-align: center;">
  <div style='font-family: BIZ UDGothic; font-size: 48px;'>{{Front}}</div>
  <br>
  {{#Sentence}}
    <div style='font-family: BIZ UDGothic; font-size: 24px;'>{{Sentence}}</div>
  {{/Sentence}}
</div>

```


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



