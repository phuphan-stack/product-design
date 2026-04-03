---
name: handoff
description: >
  Tạo handoff spec từ Figma design với đầy đủ DS token names, component variants, interaction
  states, edge cases, và known gotchas — sẵn sàng cho engineer implement qua Claude Code.
  Trigger khi nói "handoff", "hand off to dev", "create dev spec", "design spec", "design to dev",
  "generate handoff", "spec sheet from Figma", "prep for engineering", "ready for build",
  "dev-ready", "implementation spec".
version: "1.1"
status: active
owner: "@thangpv"
group: Collaboration & Handoff
---

# Handoff Skill — Design-to-Dev Spec Generator

> Generate structured developer handoff documents from Figma designs using Chợ Tốt DS tokens.
> Output slots directly into the Product Delta Force spec-driven development pipeline.

---

## When to Use

"handoff", "hand off to dev", "create dev spec", "design spec", "design to dev",
"generate handoff", "spec sheet from Figma", "prep for engineering", "ready for build",
"dev-ready", "implementation spec".

---

## Steps

### Step 1: Gather Input
- Figma link or screenshot
- Vertical: GDS, PTY, JOB, VEH, or cross-vertical
- Platform: Web, App, or both
- Spec context (optional): PM spec or acceptance criteria link

### Step 2: Audit Figma File

**MCP Readiness:**
- [ ] Layer depth ≤ 5 levels, no overlapping frames
- [ ] All layers named descriptively (not "Rectangle 42")
- [ ] Parent-child naming: parent post → children post-thumbnail, post-title, post-price
- [ ] No unnecessary duplicate states

**Design Completeness:**
- [ ] All interactive states (default, hover, loading, error, empty, disabled)
- [ ] All colours use DS tokens (no hardcoded hex)
- [ ] All text uses typography scale (Reddit Sans, correct weight group)
- [ ] Primary button icons use icon-on-background (NOT icon-primary)
- [ ] Edge cases designed (empty state, max content, error state)

### Step 3: Generate Spec (use template below)

### Step 4: Inject Per-Vertical Token Values

Use Brand Matrix to fill actual values. For cross-vertical, add comparison column.

```
             GDS          PTY          JOB          VEH
primary      #FFD400      #FA6819      #306BD9      #FFD400
text-brand   #CC8F00      #FA6819      #306BD9      #CC8F00
on-bg text   #222222      #FFFFFF      #FFFFFF      #222222
on-bg icon   #222222      #FFFFFF      #FFFFFF      #222222
hover        #FFE884      #FB7328      #548AF0      #FFE884
pressed      #FFC800      #D14200      #1952BA      #FFC800
```

### Step 5: Final Review
- [ ] All colours use DS token names (not raw hex as primary reference)
- [ ] All icons use exact Figma component names
- [ ] Per-vertical values correct (especially text-on-background and icon-on-background)
- [ ] Typography uses correct weight group
- [ ] Edge cases section complete
- [ ] Spec is self-contained

---

## Handoff Spec Template

```markdown
# Handoff Spec: [Feature/Screen Name]

**Vertical:** [GDS / PTY / JOB / VEH]  **Platform:** [Web / App]  **Figma:** [link]
**Designer:** [name]  **Date:** [date]  **Pod:** [pod name]

## Overview
[1-2 sentences: what this screen does and the user context]

## Layout Structure
[Layout hierarchy — containers, stacking, grid behaviour]

## DS Components Used
| # | Component | Variant | Token Dependencies | Notes |
|---|-----------|---------|-------------------|-------|
| 1 | Button | Primary | button-primary, text-on-background | |

## Design Tokens Map

### Backgrounds
| Element | Token | [Vertical] Value |
|---------|-------|------------------|

### Text
| Element | Token | Typography Class | Size/Weight/Line-height |
|---------|-------|-----------------|------------------------|

### Icons
| Element | Icon Name (Figma) | Style | Token |
|---------|------------------|-------|-------|

## Interaction States
| Element | State | Visual Change | Token(s) |
|---------|-------|--------------|----------|
| CTA Button | Default | | button-primary, text-on-background |
| CTA Button | Hover | Lightens | interaction-brand-hover |
| CTA Button | Pressed | Darkens | interaction-brand-pressed |
| CTA Button | Disabled | Grey | button-disabled, text-blank |
| CTA Button | Loading | Spinner | button-primary |

## Edge Cases
| Case | Behaviour |
|------|-----------|
| Empty state | |
| Loading | |
| Error | |
| Max content | |
| Offline | |

## Figma File Quality
| Check | Status |
|-------|--------|
| Layer depth ≤ 5 | ✅/❌ |
| Layers named descriptively | ✅/❌ |
| Related naming applied | ✅/❌ |

## Integration
**PM (spec-pm):** Paste into Section 6 (Design Reference) of the product spec.
**Engineer (prompt-engineer):** Feed this + Figma link to Claude Code.
**QE (spec-qe):** Each interaction state and edge case is a test assertion.
```

---

## Known DS Gotchas

- [ ] PTY brand = #FA6819 (NOT #FF8800)
- [ ] font-weight-medium = 500 (NOT 700)
- [ ] Display/Header weight = 600 (NOT 700)
- [ ] text-brand GDS = #CC8F00 (NOT #FFD400)
- [ ] icon-brand GDS = #FFBA00 (NOT #FFD400)
- [ ] background-appwrapper = #FFD400 for ALL verticals
- [ ] text-on-background: GDS/VEH = #222222, PTY/JOB = #FFFFFF
- [ ] Button icons use icon-on-background (NOT icon-primary)

---

## Rules

1. Token names are primary reference, hex values secondary: button-primary (#FFD400 for GDS)
2. Never skip gotchas section. Filter to vertical-relevant gotchas only.
3. Flag missing states — don't invent: "Error state: NOT DESIGNED — needs design before build"
4. Use Delta Force language: "acceptance criteria", "spec drift", "Claude Code"
5. One spec per screen or feature.
6. Check Figma file quality before generating.

---

## Resources
- Figma DS: https://www.figma.com/design/DfQM6G9p8PSNEoOzNGRjWD/v3.0-CHOTOT-Design-System
- Design Token Naming for MCP: https://701search.atlassian.net/wiki/spaces/PROD/pages/4765188117
