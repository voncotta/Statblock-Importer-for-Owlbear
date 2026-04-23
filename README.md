# Symbaroum GM Stat Block Viewer — Owlbear Rodeo Extension

A **GM-only** extension for Owlbear Rodeo. Import stat blocks directly from the **Symbaroum Stat Block Creator** (JSON export) and attach them to tokens on your battle map. Players never see any of this.

---

## Workflow

1. **Build your creature in the Symbaroum Stat Block Creator**
2. **Click "Save" in the creator** → downloads a `.json` file (e.g. `goblin-raider.json`)
3. **In Owlbear**, right-click the token → **Edit Stat Block** → **Import Symbaroum JSON**
4. Pick the `.json` file — done. The full stat block is now stored on the token permanently.
5. **Right-click → View Stat Block** anytime to see the full parchment-style block during play.

---

## What you see in View mode

The viewer renders all data natively from the Symbaroum JSON:
- Name, race, shadow colour
- Description / flavour text
- **Derived stats**: Toughness, Pain Threshold, Defense, Initiative (auto-calculated from attributes)
- **Armor**: protection value, shield bonus, armor qualities
- **All 8 attributes** (Accurate, Cunning, Discreet, Persuasive, Quick, Resolute, Strong, Vigilant) — colour-coded low/mid/high
- **Weapons**: name, attribute used, damage value, category, qualities and effects
- **Abilities** with level (Novice / Adept / Master)
- **Traits** with tier (I / II / III)
- **Boons & Burdens**
- **Equipment**
- **Tactics** text
- **GM Notes** (private, never in the JSON export)

---

## GM Notes

Each token also has a private **GM Notes** field — tactics for the session, corruption tracker, lore, anything. These are stored separately on the token and are never included in the JSON file, so you can share the same JSON across multiple sessions without overwriting your notes.

---

## Files

```
statblock-extension/
├── manifest.json          ← Extension entry point
├── action.html            ← Toolbar overview panel
├── statblock-popover.html ← Right-click → View
├── edit-statblock.html    ← Right-click → Edit / Import JSON
├── icon.svg
├── eye.svg
└── edit.svg
```

---

## Deployment (GitHub Pages — free, ~10 min)

### 1. Create a GitHub repo
- Go to github.com → New repository → name it `owlbear-symbaroum` → Public → Create

### 2. Upload all files
- Click **Add file → Upload files** → drag all 7 files → Commit

### 3. Enable GitHub Pages
- Repo **Settings** → **Pages** → Source: `main` branch, `/ (root)` → Save
- Wait ~2 minutes. Your URL will be:
  `https://YOUR-USERNAME.github.io/owlbear-symbaroum/`

### 4. Install in Owlbear Rodeo
- Open your room → Profile → Extensions → **Add extension**
- Paste: `https://YOUR-USERNAME.github.io/owlbear-symbaroum/manifest.json`
- Click Add

---

## Troubleshooting

- **Context menu doesn't appear**: Token must be on the **Character layer** (not Map or Prop)
- **Import fails "not a valid file"**: Make sure you're using the JSON from the Save button in the Symbaroum Stat Block Creator, not a PDF or screenshot
- **Extension doesn't load**: Try the manifest URL directly in your browser first to confirm it loads correctly

---

Designed for Symbaroum campaigns on Owlbear Rodeo 2.x.
