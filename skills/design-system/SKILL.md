---
name: design-system
description: >
  Tra cứu đầy đủ Chợ Tốt DS v3: color tokens, typography, 22 components, 137+ icons, và brand
  matrix cho 4 verticals. Trigger khi hỏi về "design tokens", "color tokens", "brand colors",
  "typography scale", "font weights", "DS reference", "token table", "vertical colors",
  "component specs", "icon name", "icon mapping", hoặc cần bất kỳ thông tin DS nào.
version: "1.0"
status: active
owner: "@thangpv"
group: UI Design
---

# Design System Skill — Chợ Tốt DS v3

> Single reference for all DS lookups: tokens, components, icons.
> Source: Figma DS v3.0 file DfQM6G9p8PSNEoOzNGRjWD

---

## Verticals

| Code | Name | Brand Primary |
|------|------|--------------|
| GDS | Goods (default) | #FFD400 |
| PTY | Property | #FA6819 |
| JOB | Jobs | #306BD9 |
| VEH | Vehicle | #FFD400 |

---

## Brand Color Matrix

```
             GDS          PTY          JOB          VEH
primary      #FFD400      #FA6819      #306BD9      #FFD400
text-brand   #CC8F00      #FA6819      #306BD9      #CC8F00
icon-brand   #FFBA00      #FA6819      #306BD9      #FFBA00
on-bg text   #222222      #FFFFFF      #FFFFFF      #222222
on-bg icon   #222222      #FFFFFF      #FFFFFF      #222222
hover        #FFE884      #FB7328      #548AF0      #FFE884
pressed      #FFC800      #D14200      #1952BA      #FFC800
light-bg     #FFF8D6      #FFF1E3      #F2F6FC      #FFF8D6
```

---

## Typography

Font: Reddit Sans | Body (400), Tagline (500), Display/Header (600), Label (700)

| Style | Size | Weight | Line-height |
|-------|------|--------|-------------|
| Body / Annotation | 10 | 400 | 16 |
| Body / Caption | 12 | 400 | 18 |
| Body / Section | 14 | 400 | 20 |
| Body / Page | 16 | 400 | 24 |
| Display / Section | 24 | 600 | 32 |
| Display / Page | 32 | 600 | 40 |
| Header / Caption | 14 | 600 | 20 |
| Header / Section | 16 | 600 | 24 |
| Header / Page | 20 | 600 | 28 |
| Label / Annotation | 10 | 700 | 16 |
| Label / Caption | 12 | 700 | 18 |
| Label / Section | 14 | 700 | 20 |
| Label / Page | 16 | 700 | 24 |
| Tagline / Footext | 10 | 500 | 16 |
| Tagline / Annotation | 12 | 500 | 18 |
| Tagline / Caption | 14 | 500 | 20 |
| Tagline / Section | 16 | 500 | 20 |

Text link: color #306BD9, decoration-color #24A3A3

---

## Components (22)

| # | Component | Key Variants |
|---|-----------|-------------|
| 1 | Announcer | List item with price, badges, stepper |
| 2 | Button | Primary, secondary, tonal, neutral, disabled |
| 3 | Chip | Filter chips |
| 4 | Checkbox | Checked / unchecked |
| 5 | Radio | Selected / unselected |
| 6 | Toggle | On / off |
| 7 | SnackBar | Toast / notification |
| 8 | Slider | Range slider |
| 9 | Tab | Tab navigation |
| 10 | Drawer | Bottom / side drawer |
| 11 | Tooltips | Tooltip popover |
| 12 | Input Field | 13 variants: Input, Placeholder, Currency, Dropdown, MultiSelectDropdown, Search, Textarea, Textarea+Placeholder, Range, Group, Chat, Unit, Currency v2 |
| 13 | Date Picker | Calendar date selection |
| 14 | Pagination | Page navigation |
| 15 | Icon Button | Icon-only action button |
| 16 | Bottom Button | Sticky footer CTA |
| 17 | Top Navigation / Header | App header for inner pages |
| 18 | Top Navigation / Main Screen | App header for home |
| 19 | Bottom Navigation | App bottom tab bar |
| 20 | Search Bar | Standalone search input |
| 21 | AI Pattern | AI-powered interaction patterns |
| 22 | Chat Field | Buyer-seller messaging input |

---

## Icon System (137 general + 21 PTY)

Naming: {IconName}-{style} — styles: fill, outline, duotone, circle, active-fill
Size: All 24x24px | Default: outline for inactive, fill for active
PTY icons: prefixed pty- (e.g. pty-rooms-fill)

### Non-Standard Naming (common errors)

| Figma Label | Actual Component | Issue |
|-------------|-----------------|-------|
| Minor | minus-fill/outline | Name mismatch |
| arrowrefresh | arrowswitch-fill/outline | Name mismatch |
| Camera number | camera-fill/camera-outine | Typo: missing "l" |
| Smartphone | Smartphone-fill/stroke | Uses stroke not outline |
| Sort | Sort-Ascending/Default/Descending | No fill/outline |
| Shopping cart | shoppingcart-fill/outline | Lowercased |
| Current location | CurrentLocation-fill/outline | Space removed |
| Ticket percent | Ticket-percent-fill/outline | Hyphenated |
| Volume | Volume-mute-fill/outline | Only mute variant |

---

## Button Token Bindings

| Element | Token | GDS/VEH | PTY/JOB |
|---------|-------|---------|---------|
| Background | Button/Solid/button-primary | #FFD400 | #FA6819 / #306BD9 |
| Text | Text/text-on-background | #222222 | #FFFFFF |
| Icon | Icon/icon-on-background | #222222 | #FFFFFF |

Icons inside primary buttons MUST use icon-on-background (NOT icon-primary).

---

## Critical Corrections (v3)

| Issue | Wrong | Correct |
|-------|-------|---------|
| PTY brand | #FF8800 | #FA6819 |
| font-weight-medium | 700 | 500 |
| Display/Header weight | 700 | 600 |
| text-brand GDS | #FFD400 | #CC8F00 |
| icon-brand GDS | #FFD400 | #FFBA00 |
| background-appwrapper | varies | #FFD400 ALL verticals |
| text-on-background GDS/VEH | white | #222222 |
| Button icon PTY/JOB | icon-primary (#222) | icon-on-background (#FFF) |

---

## Figma Source Nodes

| Content | Node |
|---------|------|
| Color tokens | 12087:31655 |
| Typography | 11720:110489 |
| Components | 12310:166284 |
| Icons | 35:8818 |
| Templates | 16284:6027 |

---

## How to Respond

1. Identify: token lookup, component spec, or icon mapping
2. Always write token name first, hex in parentheses: button-primary (#FFD400 for GDS)
3. If Figma MCP available, pull live screenshots using node IDs above

---

## Resources
- Figma DS: https://www.figma.com/design/DfQM6G9p8PSNEoOzNGRjWD/v3.0-CHOTOT-Design-System
- DS Confluence: https://701search.atlassian.net/wiki/spaces/PROD/pages/3099230689
