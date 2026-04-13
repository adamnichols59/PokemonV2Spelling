# 🐾 Bella's Spelling Adventure

An interactive spelling game built for Mrs. Faux's 3rd grade class. Students spell their weekly word list to catch creatures, care for them, and build their Pokédex — all backed by Firebase with a full teacher admin dashboard.

**Live site:** *(update with your production URL)*  
**Admin panel:** `/admin.html` — login: `adamnichols59` / `LoveBella`

---

## 📁 Files

| File | Purpose |
|------|---------|
| `index.html` | Main game — login, spelling, creature catching |
| `admin.html` | Teacher dashboard — analytics, student management |
| `creature_care.html` | Creature habitat — care, accessories, evolution |

All three files are self-contained single-page apps with no build step, no npm, no dependencies beyond Firebase (loaded via CDN) and Chart.js.

---

## 🎮 How the Game Works

### For Students
1. **Login** — create a username + 4-digit PIN, or continue as guest
2. **Spell the word** — definition and example sentence shown; hear it spoken aloud via TTS
3. **Catch the creature** — swipe up to throw the Poké Ball
4. **Earn Shine Coins** — first try, no hint = 13 coins; streak bonuses up to +10
5. **Care for creatures** — visit the habitat to pet, feed, brush, cuddle, and dress up your team
6. **Evolve** — catch the same creature 3 times to unlock ⚡ EVOLVE!

### For the Teacher
- Open `/admin.html` and log in
- **Overview** — class stats, leaderboard podium, who hasn't played yet
- **Words** — per-word difficulty, avg attempts, hint/skip rates
- **Students** — expand any student to see their word-by-word breakdown; switch between word lists via dropdown; click any word for full play history + trend graph
- **Insights** — class mastery rate, hint dependency, struggling/rushing student flags, reteach recommendations
- **Trends** — score distribution, creature charts
- **Word List** — edit words/definitions/sentences and save to Firebase; students see the new list on next game start (no redeploy needed)
- **Export CSV** — download all student analytics as a spreadsheet
- **Print** — one-click printable report per student

---

## 🔥 Firebase Setup

**Project:** `bella-spelling`  
**Service:** Firestore (no Auth — students log in via username + PIN stored in Firestore)

### Firestore Rules
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /students/{studentId} {
      allow read, write: if true;
    }
    match /wordLists/{weekId} {
      allow read, write: if true;
    }
  }
}
```

### Data Structure
```
students/{username_lowercase}/
  username, pin, createdAt
  totalScore, totalCreatures, bestStreak
  shineCoins
  allCreatures[]        ← persists across word lists
  creatureCounts{}      ← for evolution tracking (3 = evolve)
  purchasedAccs{}       ← accessories owned per creature
  accPositions{}        ← drag-and-drop positions per creature
  weeks/
    {week_key}/
      score, wordsDone, lastPlayed, playCount
      wordAnalytics/
        {word}: attempts, hintUsed, skipped, timeMs, plays

wordLists/{week_key}/
  words: [{w, d, s}]   ← word, definition, sentence
  updatedAt, updatedBy
```

### Moving to a New Domain
Firebase does **not** need reconfiguring when you change GitHub Pages URLs. The game uses Firestore directly (not Firebase Authentication), so there are no authorized domain restrictions to update. Just push the three files to your new repo and it works.

---

## 🗓️ Weekly Workflow

1. Go to `admin.html` → **Word List** tab
2. Type the new words, definitions, and example sentences
3. Click **💾 Save to Firebase**
4. Students see the new list automatically on their next game — no code changes needed

The `WEEK_KEY` in the code (`week_apr_2026`) is used as a Firestore document key. When you save a new word list from the admin, it creates a new document under that key. To start a fresh week with a fresh key, update `WEEK_KEY` in both `index.html` and `admin.html` before deploying, or just use the Word List editor (the key is displayed in the editor tab).

---

## 🐾 Creatures

**20 base creatures:** Fluffkin, Sparklox, Puddlum, Fernbit, Glimcat, Coraluff, Driftail, Peppin, Starwhirl, Mossling, Twinkow, Boulbear, Zipplet, Dazzlphin, Flameow, Crystaloo, Dewdrop, Puffy, Shimmur, Lunabelle

**20 evolved forms:** Lumifur, Emberfox, Coralswim, Bloomhop, Shadowpurr, Prismbear, Stormwing, Chompking, Novaflare, Ancienshell, Galaxhorn, Jadepaw, Thunderwing, Tidalcrest, Infernokit, Prismraccoon, Bloomlotl, Truffleking, Solarmane, Cosmowl

Catch any creature **3 times** across multiple plays of the same word list to unlock its evolution.

---

## 💰 Shine Coins Economy

| Performance | Coins |
|-------------|-------|
| First try, no hint | 8 + 5 catch = **13** |
| Second try | 3 + 5 catch = **8** |
| Third try+ | 1 + 5 catch = **6** |
| Streak ×3 | +3 bonus |
| Streak ×5 | +6 bonus |
| Streak ×7+ | +10 bonus |
| Perfect game | +25 bonus |
| Daily login | +3 bonus |

Coins are spent in the accessory shop inside creature care. Common accessories: 15–25 coins. Rare/evolved: up to 220 coins.

---

## 🛠️ Technical Notes

- **No build step** — pure HTML/CSS/JS, deploy by copying files
- **Firebase SDK** loaded via `https://www.gstatic.com/firebasejs/10.8.0/`
- **Chart.js** loaded via cdnjs for admin analytics charts
- **Web Speech API** used for TTS word pronunciation
- **Responsive** — works on iPhone, Android, iPad, MacBook
- **Portrait lock** on small phones via CSS `@media (orientation:landscape)`
- All SVG creature art is generated programmatically — no image assets needed

---

*Built with Claude (Anthropic) — April 2026*
