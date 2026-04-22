---
name: username
description: Generate creative usernames for Thom Verheul based on his identity, interests, and style. Use this skill whenever the user types /username, asks for username suggestions, or wants new handles for gaming, coding, social media, sport, music, or any other platform. Always trigger on /username.
---

# Username Generator for Thom

When the user types `/username`, parse any arguments they provide and generate 6 username suggestions using the rules below.

## Step 1 — Show the interactive menu

When the user types `/username`, **always** use the `ask_user_input` tool first to show a choice menu. Use exactly these 3 questions:

**Question 1 — Name** (single_select):
"Naam in de username?"
- "Volledige naam"
- "Initialen / afkorting"
- "Geen naam"

**Question 2 — Number** (single_select):
"Nummer erin?"
- "Persoonlijk getal"
- "Willekeurig getal"
- "Geen cijfers"

**Question 3 — Vibe** (single_select):
"Vibe?"
- "Gaming"
- "Coding"
- "Persoonlijk"
- "Social media"
- "Sport"
- "Muziek"
- "Vibey"

After the user picks their options, map them to the internal values:
- Volledige naam → name=2 / Initialen → name=1 / Geen naam → name=0
- Geen cijfers → number=0 / Persoonlijk getal → number=2 / Willekeurig → number=1
- Map vibe label to: gaming/coding/personal/social media/sport/music/vibey

Then generate immediately — no extra confirmation needed.

---

## Who Thom is

Thom Verheul, Dutch, early 20s:
- MTB / cycling enthusiast
- Car lover: Porsche, Ferrari, Williams F1 (especially the FW14B)
- Music: Fred again.. (house/electronic), Lil Kleine, Jigitz (Dutch rap), synthwave/ambient
- PC building and tech
- Graphic design (synthwave/retro 80s-90s aesthetic)
- Developer background (builds tools, dashboards, scripts)
- Casual, informal Dutch internet personality

**Past usernames as style reference:**
- "Thomsol" → gaming, sleek, no number, invented compound word
- "Thommetje7" → personal/casual, Dutch diminutive (-tje suffix), uses 7
- "TxT14" → developer style, abbreviated, uses 14

---

## Parameter rules

### `name`
- 2 → full name allowed: Thom, Thommetje, ThomV, any creative variation
- 1 → initials/abbreviated only: T, Th, TV, TxV — no full "Thom"
- 0 → zero name reference. Not Thom, Tom, T, TV, Th. Nothing.

### `number`
- 2 → must include 7 or 14 in every username (pick one per username)
- 1 → include any number except 7 or 14
- 0 → no digits anywhere in any username

### `vibe`
- gaming → short, punchy, sleek or slightly aggressive
- coding → abbreviated, technical, camelCase or initials-style
- personal → warm, casual, Dutch-friendly, diminutives welcome (-je, -tje)
- social media → catchy, clean, brandable, memorable
- sport → energetic, speed/motion references, trail or racing feel
- music → vibe-y, house/rap/synthwave references
- vibey → aesthetic, stylized, abstract or poetic

---

## Output format

Present results as a clean numbered list directly in chat. No JSON, no preamble, no markdown headers. Just:

```
1. **ThomVoid** — synthwave + identity, clean gaming handle
2. **VeloDrift** — MTB speed energy, no name needed
...
```

Then a single line at the end showing the settings used, e.g.:
`↳ name=2 · number=0 · vibe=gaming`

---

## Quality rules

- Exactly 6 usernames every time
- Max 16 characters per username
- No xXx, no _official_, no "real"/"its"/"the" prefixes, no trailing underscores
- Variety: different lengths and constructions across the 6
- Pronounceable and memorable
- Feels like Thom, not a random generator
- **name=0**: double-check — zero name traces anywhere
- **number=0**: double-check — zero digits anywhere
- **number=2**: every username must contain 7 or 14

The reason for each username should be max 10 words, specific, no filler.