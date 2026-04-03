---
name: build
description: >
  Chuyển design từ Figma thành code: HTML/CSS prototype nhanh hoặc React + Linaria v6 production
  code. Hỗ trợ single screen và multi-screen flow. Trigger khi nói "implement this", "hand off
  to dev", "code this component", "convert to React", "prototype a screen", "build a mockup",
  "create an HTML preview", "make a quick UI", hoặc cần turn design thành working code.
version: "1.0"
status: active
owner: "@thangpv"
group: UI Design
---

# Build Skill — Figma to Code

> Turn Figma designs into working code: rapid HTML/CSS prototypes or production React + Linaria v6 components.
> Self-contained skill with all Chợ Tốt DS tokens, vertical-aware colours, and typography scale.

---

## When to Use

Trigger phrases: "implement this", "hand off to dev", "code this component", "convert to React",
"Linaria tokens", "dev specs", "prototype a screen", "build a mockup", "create an HTML preview",
"make a quick UI", "prototype this page", "mock up a listing card", "implement from Figma".

---

## Step 1: Determine Build Mode

| Mode | Output | When |
|------|--------|------|
| **Prototype** | Single file HTML | Quick validation, stakeholder review, early exploration |
| **Dev handoff** | React + Linaria v6 code | Production implementation, Figma → code |

## Step 2: Detect Context

- **Vertical:** GDS/PTY/JOB/VEH. Default GDS.
- **Platform:** Mobile screen = App. Browser-like = Web.
- **Single vs Multi-screen:** One screen → full-screen view. Multiple → swipe/tap flow.

## Step 3: Build

Follow mode-specific guide below.

---

## Mode 1: HTML Prototype

### Build Rules
- Single file: HTML + inline style + script
- Font: Reddit Sans (weights: 300-800) from Google Fonts
- Colors: NEVER hardcode hex — use CSS variables (var(--brand), var(--text-brand))
- Apply vertical class on body: vertical-gds, vertical-pty, vertical-job, vertical-veh

### Multi-Screen Flow (CRITICAL)
- Each screen must be full-screen — like on a real device
- Navigation uses swipe gestures or tap transitions — no tabs, buttons, or dropdowns
- DO NOT add any UI not in the original Figma design

---

## Mode 2: React + Linaria Dev Handoff

### Stack
- Framework: React + TypeScript
- Styling: Linaria v6 (zero-runtime CSS-in-JS)
- Font: Reddit Sans (weights: 300–800)

### Implementation Pattern
```tsx
import { css } from '@linaria/core';
const button = css`
  background-color: var(--background-brand);
  color: var(--text-on-background);
  font-family: 'Reddit Sans', sans-serif;
  font-size: 14px; font-weight: 700; line-height: 20px;
  border: none; border-radius: 8px; cursor: pointer;
  &:hover { background-color: var(--interaction-brand-hover); }
  &:disabled { background-color: var(--button-disabled); color: var(--text-blank); }
`;
```

---

## Typography Scale

| Class | Size | Weight | Line-height |
|-------|------|--------|-------------|
| body-annotation | 10px | 400 | 16px |
| body-caption | 12px | 400 | 18px |
| body-section | 14px | 400 | 20px |
| body-page | 16px | 400 | 24px |
| display-section | 24px | 600 | 32px |
| display-page | 32px | 600 | 40px |
| header-caption | 14px | 600 | 20px |
| header-section | 16px | 600 | 24px |
| header-page | 20px | 600 | 28px |
| label-annotation | 10px | 700 | 16px |
| label-caption | 12px | 700 | 18px |
| label-section | 14px | 700 | 20px |
| label-page | 16px | 700 | 24px |
| tagline-footext | 10px | 500 | 16px |
| tagline-annotation | 12px | 500 | 18px |
| tagline-caption | 14px | 500 | 20px |
| tagline-section | 16px | 500 | 20px |

---

## Button Icon Color Rule (CRITICAL)

| Element | Token | GDS/VEH | PTY/JOB |
|---------|-------|---------|---------|
| Background | button-primary | #FFD400 | #FA6819 / #306BD9 |
| Text | text-on-background | #222222 | #FFFFFF |
| Icon | icon-on-background | #222222 | #FFFFFF |

Icons inside primary buttons MUST use icon-on-background (NOT icon-primary).

---

## Common Mistakes Checklist

- [ ] PTY brand = #FA6819 (NOT #FF8800)
- [ ] font-weight-medium = 500 (NOT 700)
- [ ] Display/Header weight = 600 (NOT 700)
- [ ] text-brand GDS = #CC8F00 (NOT #FFD400)
- [ ] icon-brand GDS = #FFBA00 (NOT #FFD400)
- [ ] background-appwrapper = #FFD400 for ALL verticals
- [ ] text-on-background: GDS/VEH = #222222, PTY/JOB = #FFFFFF
- [ ] Button icons use icon-on-background (NOT icon-primary)

---

## Resources
- Figma DS: https://www.figma.com/design/DfQM6G9p8PSNEoOzNGRjWD/v3.0-CHOTOT-Design-System
- Stack: React + Linaria v6 + TypeScript
