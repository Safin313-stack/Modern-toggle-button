<div align="center">

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100:0f3460&height=200&section=header&text=Modern+Toggle+Button&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=A+day+and+night+toggle+switch+built+in+pure+HTML+and+CSS&descAlignY=60&descSize=15&descColor=94a3b8" width="100%"/>

<br/>

[![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![MIT License](https://img.shields.io/badge/License-MIT-22c55e?style=flat-square)](LICENSE)
[![Deployed](https://img.shields.io/badge/Deployed-GitHub%20Pages-0ea5e9?style=flat-square&logo=github)](https://safin313-stack.github.io/Modern-toggle-button/)
[![No JS](https://img.shields.io/badge/JavaScript-None-gray?style=flat-square)]()

<br/>

<a href="https://safin313-stack.github.io/Modern-toggle-button/">
  <img src="https://img.shields.io/badge/-%F0%9F%8C%99%20%20LIVE%20DEMO%20%20%E2%86%92-0f3460?style=for-the-badge&logoColor=white" alt="Live Demo" height="42"/>
</a>

<br/>
<sub>✦ No login &nbsp;·&nbsp; No install &nbsp;·&nbsp; Opens instantly in your browser ✦</sub>

<br/><br/>

</div>

---

<div align="center">

### 🌙 Features

| ☀️ Day Mode | 🌙 Night Mode | 🎞️ Smooth Animation | 🌅 Background Switch | 🔵 Knob Slide | ⚡ Pure CSS |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Sunny sky background with glowing sun | Dark night sky with crescent moon | CSS keyframe animations on every state | Full background image transition | Knob stretches and slides on toggle | Zero JavaScript — entirely CSS driven |

</div>

---

## 🖥️ Live Preview

```
┌──────────────────────────────────────────────────────┐
│                                                      │
│   ☀️  DAY MODE                   🌙  NIGHT MODE      │
│                                                      │
│   [ 🌞 ————— ]     ←toggle→     [ ————— 🌙 ]        │
│                                                      │
│   Light radial                  Dark radial          │
│   gradient bg                   gradient bg          │
│                                                      │
└──────────────────────────────────────────────────────┘
```

> ✦ Click the toggle — watch the knob animate, background switch, and sun/moon transition

---

## 🎨 CSS Highlights

### Day / Night Background Switch

```css
/* Day mode — sunny sky image embedded as base64 */
.switch {
  background-image: url('...day-sky-base64...');
  background-size: cover;
  transition: background-image .7s ease-in-out;
}

/* Night mode — dark starry sky */
.switch:checked {
  background-image: url('...night-sky-base64...');
  transition: background-image 1s ease-in-out;
}
```

### Animated Knob — Stretches and Slides

```css
/* Knob slides RIGHT on toggle (day to night) */
@keyframes on {
  0%   { transform: translateX(0px);  width: 46px; }
  50%  { width: 75px; border-radius: 25px; }
  100% { transform: translateX(80px); width: 46px; }
}

/* Knob slides LEFT on toggle (night to day) */
@keyframes off {
  0%   { transform: translateX(80px); width: 46px; }
  50%  { width: 75px; border-radius: 25px; }
  100% { transform: translateX(0px);  width: 46px; }
}
```

### Sun Glow Effect

```css
@keyframes sun {
  90%, 100% {
    background-color: #f5daaa;
    box-shadow:
      0px 0px 10px #f5deb4,
      0px 0px 20px #f5deb4,
      0px 0px 30px #f5deb4,
      inset 0px 0px 2px #efd3a3;
    filter: blur(1px);
  }
}
```

### Moon Crescent Effect

```css
@keyframes moon {
  90%, 100% {
    background-color: transparent;
    box-shadow: 5px -1px 0px #fff;
    filter: blur(0px);
    transform: rotate(170deg);
  }
}
```

### Dark Mode Body

```css
body           { background: radial-gradient(#ffffff, #868686); }
body.dark-mode { background: radial-gradient(#2c2c2c, #000000); }
```

---

## 🧠 How It Works — Zero JavaScript

The entire interaction is powered by a **CSS checkbox** trick:

```html
<input type="checkbox" class="switch" id="toggle"/>
<label for="toggle">Day / Night</label>
```

```css
.switch          { /* day styles  — unchecked state */ }
.switch:checked  { /* night styles — checked state  */ }

/* ::before = sun / moon icon */
.switch:before         { animation: moon; }
.switch:checked:before { animation: sun;  }

/* ::after = sliding knob */
.switch:after         { animation: off; }
.switch:checked:after { animation: on;  }
```

No event listeners. No DOM manipulation. Just the `:checked` pseudo-class doing all the work.

---

## 📁 Project Structure

```
Modern-toggle-button/
│
├── 📄 modern-toggle-btn.html   ← Full project: HTML + CSS in one file
└── 📄 README.md                ← Project documentation
```

---

## 🚀 Run It Yourself

**Option 1 — Live (instant, no setup)**

> 🔗 **[https://safin313-stack.github.io/Modern-toggle-button/](https://safin313-stack.github.io/Modern-toggle-button/)**

**Option 2 — Clone and open locally**

```bash
git clone https://github.com/Safin313-stack/Modern-toggle-button.git
open modern-toggle-btn.html
```

---

## 🛠️ Tech Stack

```
┌──────────────────────────────────────────────────────┐
│           Frontend · Single File · No JavaScript     │
├─────────────────┬────────────────────────────────────┤
│  HTML5          │  Checkbox input + label            │
│  CSS3           │  Keyframes + pseudo-elements       │
│  Technique      │  :checked pseudo-class toggle      │
│  Background     │  Base64 encoded images             │
│  Animation      │  @keyframes · cubic-bezier timing  │
└─────────────────┴────────────────────────────────────┘
```

---

## 📚 Key CSS Concepts Used

```
:checked pseudo-class  → detects toggle state without JavaScript
::before / ::after     → sun and moon rendered as pseudo-elements
@keyframes             → smooth knob slide + stretch animation
cubic-bezier()         → custom easing for bouncy feel
box-shadow             → sun glow and moon crescent effects
radial-gradient        → day/night body background
base64 images          → background images embedded directly in CSS
filter: blur()         → soft glow on the sun element
transform: rotate()    → moon crescent rotation animation
```

---

## 💡 Credits & Inspiration

Special thanks to **TCW - AI & coding resources** (Telegram Community)
for ideas, guidance, and coding support throughout this project. 🙏

---

<div align="center">

## 👤 Developer

<br/>

**Saharia Hassan Safin**
Front-end Developer

<br/>

[![GitHub](https://img.shields.io/badge/GitHub-Safin313--stack-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Safin313-stack)
&nbsp;
[![Live Project](https://img.shields.io/badge/Live%20Project-Visit%20Now-0f3460?style=for-the-badge&logo=vercel&logoColor=white)](https://safin313-stack.github.io/Modern-toggle-button/)

<br/>

*"Who needs JavaScript when CSS can do magic?"* 🌙

<br/>

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f3460,50:16213e,100:1a1a2e&height=120&section=footer" width="100%"/>

<sub>MIT License · © 2025 Saharia Hassan Safin · ⭐ Star this repo if it helped you!</sub>

</div>
