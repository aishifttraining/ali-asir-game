# حماة الديرة — Village Guardians

## What it does

**Defend the village… race for the treasure! / احمِ الديرة… واسبقهم للغنيمة!**

A cheerful, single-screen top-down action game inspired by a warm Asir village square. One human player competes with optional local computer rivals while defending the square, collecting treasure, and chasing a best score in a 60-second round.

Everything is drawn and generated in the browser: the village, mountains, decorations, expressive six-variant adventurers, creature types, effects, and optional sounds. It has no network connection, accounts, server, online multiplayer, installation step, or outside assets.

## How to run it

1. Open this project folder.
2. Double-click `index.html`, or right-click it and choose a modern browser.
3. Choose a difficulty and **0–5 computer bots**, then select **Start round** / **ابدأ الجولة**.

On the first Start in a browser visit, a short skippable three-scene opening plays before the 60-second clock begins. The visible **Skip / تخطّي** control (or Escape) reaches the short countdown immediately. **Story / القصة** replays the opening from the menu and returns to the menu without starting a scored round. Restart goes straight to the countdown. Demo ×3 accelerates gameplay only, never the opening.

It works when opened directly from a folder; no server is required. A modern browser with JavaScript enabled (Chrome, Edge, Firefox, or Safari) is enough.

Language, master sound, Music, Sound Effects, the selected setup, demo preference, and separate best scores are saved only in the current browser using local storage. If local storage is unavailable, the game continues for the current visit without saving preferences.

## Audio

The optional soundtrack and effects are original, lightweight Web Audio generated in the browser—no recordings, downloads, APIs, or network requests are used. The festival loop combines a soft plucked melody, warm bass, and light percussion at a lower level than gameplay cues. Browser audio begins only after an explicit interaction such as **Start**, **Story**, **Resume**, or enabling a sound control. The HUD note button is the master mute; the menu has separately saved **Music / الموسيقى** and **Sound Effects / المؤثرات الصوتية** choices. Music fades out while the game is paused, in results or menus, or when the tab is hidden, and resumes only through the appropriate active interaction.

## Controls

### Desktop

- **WASD** or **arrow keys** — move
- **Mouse** — aim
- **Hold primary mouse button** — fire
- **Space** — dash
- **E** — use the carried item
- **1** — switch between your slingshot and collected special weapon
- **Escape** or the pause button — pause / resume

Only the primary mouse button fires, so right-click keeps its normal browser meaning outside the active playfield.

### Mobile

- **Left joystick** — move
- **Right joystick** — aim and fire
- **Dash button** — dash
- **Use item button** — use the carried item

The touch controls support simultaneous movement, aiming, firing, and actions. Landscape orientation gives the largest play area on smaller phones.

## Character art and movement polish

The menu keeps a closed **Character & monster preview** disclosure below the primary controls, so the title, settings, and Start action remain immediately reachable. Expand it to see the exact procedural artwork used in play: six distinct fictional Saudi/Asir-inspired adventurers plus chunky slow creatures, lean fast creatures, and armed couriers at both actual gameplay size and enlarged detail size—without downloading artwork.

Characters use motion tied to their actual movement: walking feet, garment and arm sway, separate weapon aim, firing recoil, hit feedback, idle breathing, and brief dash trails. The combat circles and gameplay speed stay unchanged. Bots now keep goals briefly, steer around nearby obstacles, use a gentler fighting standoff, and separate from nearby rivals to reduce target jitter and visible stacking. Bots also use the same pickup eligibility rules as collection, so they do not chase an extra item while already carrying one or a weapon while an active theft blocks it.

## Stage 2 gameplay

### Difficulty and local rivals

- **Easy** (default) has gentler monsters, lower pressure, and more forgiving bot reactions.
- **Normal** keeps the standard village challenge.
- **Hard** makes monster pressure and rival mischief more intense.
- Choose **0–5 computer bots**. They are local rule-based rivals only: no network, accounts, room codes, or external AI. They use the same movement, health, dash, weapon, pickup, and item rules as the human player.
- The in-round panel and results screen show a live, deterministic ranking by score, treasure, defeats, respawns, then creation order.

A mode’s best score is separate for each difficulty, bot count, and run kind. **Demo ×3** is off by default, shows a clear in-round badge when enabled, and its records never overwrite normal-speed records.

### Weapons

Everyone always keeps a balanced **Slingshot**.

- **Rapid dart launcher** — fast shots with lower damage.
- **Color-burst launcher** — slower projectiles that splash nearby monsters.

Special weapons appear as pickups and replace only the currently carried special weapon; the slingshot is never lost. Ordinary shots do not damage companions.

### Carry-one items

You can carry exactly one item at a time. Pick up a **Trap** or **Hook**, then use it with **E** or the visible mobile button. Using an item consumes it.

- **Trap:** arms after a short visible delay. It slows monsters or a rival companion, never its owner. A rival caught by a trap drops a small capped amount of score as matching collectible treasure, then receives brief protection from repeat traps.
- **Hook:** launches a short, manually aimed projectile. It is spent even if it misses. A hook can steal a rival’s special weapon but cannot hurt their health. If a target only has the basic slingshot, the game clearly says that no special weapon exists.

### Weapon recovery

A successful weapon theft marks the thief with a **10-second** countdown. The original owner can get the weapon back by touching the thief or hitting them with a directly aimed ordinary shot. Recovery does not hurt the companion and shows **“رجع الحق!” / “Got it back!”**.

On recovery, the weapon returns, the thief falls back to their slingshot, and any replacement special weapon is safely dropped. On timeout, the thief keeps the weapon and the victim receives a compensation hook; if their item slot is full, a reserved hook pickup is placed for them. Defeat and round end safely return any unresolved stolen weapon, so no participant can lose their ability to fight.

### Solo rounds

With **0 bots**, an occasional visible **armed elite courier** carries a special weapon. A hook can take that weapon, or defeating the courier normally makes it drop. In solo rounds traps slow monsters instead of companions.

### Scoring, respawns, and pace

Slow stone sprites arrive from the start. Fragile fast sprites join later. Defeat monsters, collect their treasure, and score points. At 20 and 40 active seconds the village becomes busier. If a character loses all health, they respawn after a short delay with temporary protection. The human loses up to 75 points—never more than their current score. The round freezes exactly at zero and shows final rankings.

## Try it with sample data

`sample-data/data.js` contains a fictional showcase configuration loaded with a normal script tag, so it also works when `index.html` is opened directly.

Click **Load demo example** / **حمّل مثال العرض** to explicitly choose **Easy**, **2 bots**, and **Demo ×3 speed**. Demo speed accelerates the simulation so reviewers can see pressure changes, pickups, rankings, and final results in under one real minute; the active-round badge confirms that it is on. A standard round still lasts exactly 60 active game seconds.

All gameplay is local to the browser. No player-entered data, identity, or scores are sent anywhere.

Built with Claude Code during the KKU Claude Code hackathon.

Started on 2026-10-01
