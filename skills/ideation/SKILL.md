---
name: ideation
description: >
  Brainstorm UI options cho feature mới, dựa trên 22 DS components hiện có. Mỗi option đi kèm
  ASCII wireframe, DS components used, pros/cons, và template page fit. Trigger khi nói
  "feature idea", "brainstorm UI", "explore options", "what could we build", "new feature",
  "UI options for", "how should we design", hoặc muốn ideate trước khi prototyping.
version: "1.0"
status: active
owner: "@thangpv"
group: Strategy & Thinking
---

# Ideation Skill — DS-Aware Feature Brainstorming

> Generate UI options for new features using only existing Chợ Tốt Design System components.
> Every suggestion is buildable with current DS components and tokens.

---

## When to Use

Trigger phrases: "feature idea", "brainstorm UI", "explore options", "what could we build",
"new feature", "get idea", "UI options for", "how should we design".

**Stage:** Discovery / Ideation — before prototyping.

---

## Step 1: Understand the Request

Ask user:

- What problem or user need does this feature solve?
- Which vertical(s)? (GDS, PTY, JOB, VEH, or cross-vertical)
- Which platform? (Web, App, or both)
- Which reference screen? (Homepage, Adlisting, Adview, or new page)

## Step 2: Inventory Available Building Blocks

Use the DS Components Quick Reference table and brand matrix below. This skill runs independently — no auto-loading from other skills.

**Brand matrix:**

```
             GDS          PTY          JOB          VEH
primary      #FFD400      #FA6819      #306BD9      #FFD400
text-brand   #CC8F00      #FA6819      #306BD9      #CC8F00
on-bg text   #222222      #FFFFFF      #FFFFFF      #222222
```

## Step 3: Generate 2-3 UI Options

For each option, provide:

### Option Title
Short descriptive name.

### Layout Sketch
ASCII wireframe showing component placement:

```
┌─────────────────────────┐
│  [Tab: Filter A | B | C]│
│  ┌───┐ ┌───┐ ┌───┐     │
│  │Card│ │Card│ │Card│   │
│  └───┘ └───┘ └───┘     │
│  [Button: primary]      │
└─────────────────────────┘
```

### DS Components Used
List every component the option needs:

- Component name + variant (e.g. "Button / primary", "Input Field / Search Bar")
- Icons by exact component name (e.g. `Filter-outline`, `Search-outline`)
- Token references for brand-dependent styling

### Pros / Cons
Tradeoffs covering:

- Implementation complexity
- UX implications (discoverability, cognitive load, consistency)
- Cross-vertical considerations

### Template Page Fit
Which template (Homepage, Adlisting, Adview) can integrate, or if a new page pattern is needed.

## Step 4: Recommend and Next Step

Recommend one option with rationale. Suggest next step — always ask user to confirm before switching to another skill.

---

## DS Components Quick Reference

| Component | Best for |
|-----------|----------|
| Button | CTAs, actions, form submit |
| Icon Button | Icon-only actions (share, favourite, close) |
| Bottom Button | Sticky footer CTAs (checkout, contact seller) |
| Input Field (13 variants) | Search, forms, filters, currency, chat, unit input |
| Chip | Filter selection, tags |
| Tab | Section switching, category navigation |
| Drawer | Detail panels, filters panel, bottom sheets |
| SnackBar | Feedback, confirmation, undo |
| Slider | Range selection (price, area) |
| Announcer | List items with price, badges, stepper |
| Checkbox / Radio / Toggle | Selection controls |
| Tooltips | Contextual help |
| Date Picker | Date/range selection |
| Pagination | List navigation |
| Top Navigation | App headers (inner pages + main screen) |
| Bottom Navigation | App tab bar |
| Search Bar | Standalone search component |
| AI Pattern | AI-powered suggestions, smart features |
| Chat Field | Buyer-seller messaging input |

---

## Template Pages

| Template | Use case | Variants |
|----------|----------|----------|
| Homepage | Entry point, category browsing, promotions | 4 verticals x 2 platforms |
| Adlisting | Search results, filtered listings | 4 verticals x 2 platforms |
| Adview | Single item detail, seller info, actions | 4 verticals x 2 platforms |

---

## Rules

1. **Only use existing DS components** — never invent new ones. Flag clearly if "requires new DS component".
2. **Reference icons by exact component name** — say `Heart-outline` not "a heart icon".
3. **Respect vertical differences** — note when brand tokens differ across verticals.
4. **Show token names** — reference `button-primary`, `text-brand`, etc., not raw hex values.
5. **Keep options distinct** — each option must be a meaningfully different UX approach.

---

## Tips

- Self-contained skill — has inline brand matrix and component list, no need to load from other skills.
- Always ask user to confirm before suggesting a switch to build or design-system skill.
- Each option should include an ASCII wireframe for quick team visualization.
- Cross-vertical features need extra attention — note when on-background colours differ (GDS/VEH dark vs PTY/JOB white).

---

## Resources

- Figma DS file: https://www.figma.com/design/DfQM6G9p8PSNEoOzNGRjWD/v3.0-CHOTOT-Design-System
- Plugin source: product-design
