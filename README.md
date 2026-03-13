# 🐾⭐ Bella's Spelling Adventure

A custom spelling game built for Bella and her class — this week's focus: **Compound Words**.

🎮 **[Play the Game](https://adamnichols59.github.io/PokemonV2Spelling/)**

> **Best experience:** Open in Safari on iPhone or iPad → tap Share → **Add to Home Screen** for full-screen app mode!

---

## 🎮 How to Play

### Step 1 — Spell the Word
- The word is spoken aloud automatically when the screen loads
- Tap 🔊 to hear it again at any time
- Type the word into the letter tiles
- Tap ✅ CHECK when ready
- First wrong answer shows a hint — no heart lost
- Second wrong answer loses a heart ❤️

### Step 2 — Catch the Creature!
- A kawaii creature appears — just like Pokémon Go!
- A colored ring shrinks around the creature
- **Swipe the ball upward** to throw it
- 🟢 **Green ring** = Great Throw! (+3 pts)
- 🟡 **Yellow ring** = Nice! (+1 pt)
- 🔴 **Red ring** = Normal catch
- ⚫ **Full size** = Miss — try again!
- After catching, give your creature a **nickname**!

### Step 3 — Map Moves Forward
- Your trainer walks to the next location
- 5 locations to explore across 20 words

---

## 🔥 Streak System

Spell words correctly in a row to build your streak:
- 2 in a row → 🔥
- 3 in a row → On fire!
- 5 in a row → UNSTOPPABLE! ⚡
- 7 in a row → YOU ARE A SPELLING STAR! ⭐

Your best streak is shown on the win screen!

---

## 🗺️ The Journey

| Location | Words |
|---|---|
| 🏡 Meadow Valley | Words 1–4 |
| 🌲 Whispering Woods | Words 5–8 |
| ⛰️ Crystal Cave | Words 9–12 |
| 💧 Rainbow Lake | Words 13–16 |
| 🌋 Star Summit | Words 17–20 |

---

## 📖 This Week's Words

**Compound Words**

`airplane` · `daytime` · `birthday` · `daylight` · `hairdo` · `somebody` · `birdhouse` · `barefoot` · `headlight` · `sometime` · `someone` · `newspaper` · `sidewalks` · `basketball` · `stagecoach` · `placed` · `office` · `giant` · `handwriting` · `windshield`

---

## 🏅 The $1.00 Prize

Spell all 20 words correctly on the **first try** with **no hints** and **no skipping** to unlock the special prize screen.

> Show the screen to Dad to claim **$1.00!** 🏆
>
> *(Max $5.00 per week — Dad keeps track 👀)*

---

## 🐾 The Creatures

20 original kawaii creatures — one per word. Each has its own:
- Unique design and personality
- Habitat (meadow, ocean, volcano, night sky, forest, mountain)
- Stats (HP, ATK, DEF, SPD)
- Favourite food
- Lore description

**The creatures:**
Fluffkin · Sparklox · Puddlum · Fernbit · Glimcat · Coraluff · Driftail · Peppin · Starwhirl · Mossling · Twinkow · Boulbear · Zipplet · Dazzlphin · Flameow · Crystaloo · Dewdrop · Puffy · Shimmur · Lunabelle

---

## 🏠 Creature Care

After completing the game, tap any caught creature to visit their **habitat care screen**:

- 🤚 **Pet** them
- 🍎 **Feed** them their favourite food
- 🪮 **Brush** or ✨ **Sparkle** them
- 💤 **Cuddle** them to sleep (pet to wake!)
- 🎀 **Dress up** with accessories — up to 10 per creature, stackable!
- Each creature has unique animations and idle behaviour
- Happiness bar tracks how well you care for them

---

## 🔊 Audio

- Each word spoken automatically: **word → sentence → word**
- Uses the **Web Speech API** — built into the browser, no account needed
- Background chiptune music
- Sound effects: encounter, throw, catch, correct, wrong, victory
- Tap 🔈 to mute/unmute

---

## 🛠️ Tech

- Two static HTML files — no build tools, no server, no installs
- All 20 creatures hand-drawn in SVG code
- Sound and music generated with Web Audio API (no audio files)
- Pokémon Go–style shrinking ring mechanic with `requestAnimationFrame`
- Keyboard handling uses `visualViewport` API for iPhone Safari
- Analytics via Google Analytics (GA4)
- Hosted free on GitHub Pages

---

## 📁 Files

```
index.html          ← the main spelling game
creature_care.html  ← creature habitat & care screen
README.md           ← you are here
.nojekyll           ← disables Jekyll processing on GitHub Pages
```

---

## 📱 Tips

- **Add to Home Screen** in Safari for the best full-screen experience
- Works on iPhone, iPad, Android, and desktop browsers
- No internet required after initial load — voice and music are built in
- Analytics require internet to report

---

*Made with ❤️ for Bella and her class — good luck on your spelling tests! You are all AMAZING! ⭐*
