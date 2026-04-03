---
name: ux-review
description: >
  Đánh giá design theo 4 layers: Information Architecture, Usability, Accessibility, và Marketplace
  UX Patterns. Mỗi issue được rated severity và kèm suggestion cụ thể. Trigger khi nói "review
  this design", "check UX", "UX review", "is this usable", "accessibility check", "usability
  review", "critique this screen", "đánh giá UX", "review flow này", hoặc khi design cần
  evaluation trước khi finalise.
version: "1.0"
status: active
owner: "@thangpv"
group: Strategy & Thinking
---

# UX Review Skill — Chợ Tốt Design Quality Check

> Evaluate designs across 4 UX quality layers: Information Architecture, Usability, Accessibility,
> and Marketplace UX Patterns. Each issue is severity-rated with concrete suggestions.
> Built for the Chợ Tốt marketplace context — 4 verticals, buyer/seller journeys, mobile-first
> Vietnamese market.

---

## When to Use

Trigger phrases: "review this design", "check UX", "UX review", "is this usable",
"review trải nghiệm", "check IA", "information architecture", "accessibility check",
"usability review", "critique this screen", "đánh giá UX", "review flow này",
"có vấn đề gì về UX không".

**Why it matters:** In the Delta Force pipeline, designs go from Figma → spec → Claude Code →
production very fast. Little room for "we'll catch it in QA." This review catches problems while
they're still cheap to fix — in Figma, not in code.

---

## Step 1: Gather Input

Ask user to provide:

- **Design to review** — Figma link, screenshot, or description
- **Context** — which screen/feature? What is the user trying to do?
- **Vertical** — GDS, PTY, JOB, VEH (affects marketplace patterns)
- **Platform** — Web, App, or both
- **User role** — Buyer flow, Seller flow, or both

If Figma MCP connected and link provided → pull screenshot and design context automatically.

## Step 2: Run 4-Layer Review

Run all 4 layers. For each issue found, rate severity:

| Severity | Meaning | Action |
|----------|---------|--------|
| 🔴 Critical | Blocks task completion or causes serious confusion | Must fix before ship |
| 🟡 Major | Noticeably degrades experience but user can work around | Should fix this sprint |
| 🟢 Minor | Polish item, not blocking | Fix when convenient |

## Step 3: Generate Report

Compile results using the Output Format below, including scoring for each layer.

---

## Layer 1 — Information Architecture

Evaluate how information is structured, prioritised, and navigated.

### Content Hierarchy

- Does visual hierarchy match importance hierarchy? Most important action/info must be most visually prominent
- Is there a clear primary action on this screen? Multiple competing CTAs = problem
- Is information grouped logically? Related items close together, unrelated items clearly separated

### Navigation & Wayfinding

- Does user know where they are? (breadcrumb, highlighted tab, page title)
- Does user know where they can go? (visible navigation, clear links)
- Can user go back? (back button, close, cancel — especially important in multi-step flows)
- Multi-step flows: is progress visible? (step indicator, progress bar)

### Content Density

- Too much on screen? "Squint test" — squint at design, can you identify the primary action?
- Any elements that should be progressive-disclosed (show on demand) instead of upfront?
- Mobile: is the most important content visible without scrolling?

### Chợ Tốt-Specific IA Checks

- **Listing screens:** Is price the most prominent info after photo? (price = #1 decision factor on Chợ Tốt)
- **Search/filter:** Can user narrow results without too many taps? Each added filter tap loses ~15% users
- **Seller flow:** Is "Đăng tin" path obvious and short? Seller friction directly impacts supply
- **Cross-vertical:** If this pattern exists in another vertical, is IA consistent?

---

## Layer 2 — Usability (Nielsen's 10 Heuristics)

### 1. Visibility of System Status

- Loading: Does user see feedback within 1 second after each action? (skeleton, spinner, progress)
- Submission: After posting ad or sending message, is there clear confirmation?
- Errors: Are error states visible and specific? ("Vui lòng nhập số điện thoại hợp lệ" — not just "Lỗi")

### 2. Match Between System and Real World

- Language: Natural Vietnamese, conversational? Avoid technical jargon
- Mental model match: Buyer (Browse → Compare → Contact → Negotiate → Meet), Seller (Photos → Price → Describe → Post → Manage)
- Currency/number format: "1.200.000 đ" — not "1,200,000 VND"

### 3. User Control and Freedom

- Can user undo? (unsend message, edit posted ad, remove photo)
- Can user exit without losing work? (save draft on "đăng tin" flow)
- Do destructive actions have confirm? ("Xóa tin?" with clear undo option)

### 4. Consistency and Standards

- Does this screen follow the same patterns as similar screens in the app?
- Are same actions named consistently? ("Liên hệ" vs "Gọi" vs "Nhắn tin" — pick one per context)
- Do icons mean the same thing everywhere?

### 5. Error Prevention

- Form inputs: Are there input masks/constraints preventing wrong formats? (phone: 10 digits, price: numbers only)
- Photo upload: Is there guidance about photo quality before user uploads 10 bad photos?
- Price input: Sanity check? (listing motorbike at 500đ is probably a mistake)

### 6. Recognition Rather Than Recall

- Category selection: Can user browse or must they type exact name?
- Saved searches / recent views: Does app remember what user was looking at?
- Form fields: Helpful defaults or examples? ("VD: iPhone 15 Pro Max 256GB" in title field)

### 7. Flexibility and Efficiency

- Power users: Can seller posting 50 ads/month work efficiently? (templates, duplicate previous ad)
- First-time users: Is "Đăng tin" flow guided enough for newcomers?
- Search: Search by keyword, category, location, price range without friction?

### 8. Aesthetic and Minimalist Design

- Does every element on screen earn its space? Remove what doesn't help user complete task
- Listing cards: photo, title, price, location, time — anything redundant?

### 9. Help Users Recognise, Diagnose, and Recover from Errors

- Error messages: Say what went wrong AND what to do about it?
- Empty states: When no results, does design suggest what to try differently?
- Network errors: Clear retry mechanism? (especially important for Vietnamese mobile networks)

### 10. Help and Documentation

- Complex flows ("Đẩy tin", payment, premium features): contextual help available?
- Tooltips or info icons for features that aren't self-explanatory?

---

## Layer 3 — Accessibility

### Visual Accessibility

- Color contrast meets WCAG AA (4.5:1 for normal text, 3:1 for large text). Pay attention to: white text on brand colours (PTY orange, JOB blue pass; GDS yellow fails for white text), light grey text on white backgrounds, text over photos
- Don't use colour as the only way to convey information (error = red + icon + text, not just red)

### Touch & Interaction

- Touch targets: Minimum **44x44pt** for all tappable elements
- Spacing between targets: at least 8pt gap between adjacent tappable elements
- Gesture accessibility: If using swipe (photo carousel), is there a tap alternative? (dots, arrows)

### Screen Reader & Assistive Tech

- Images: Do listing photos have meaningful alt text?
- Icons: Do icon-only buttons have labels? (heart icon needs "Lưu tin" label)
- Form inputs: Labels associated with inputs? (not just placeholder text that disappears on focus)
- Reading order: DOM order matches visual order?

### Situational Accessibility (Vietnam-specific)

- **Outdoor readability:** Many Chợ Tốt users browse outdoors. Is contrast sufficient for sunlight?
- **One-handed use:** Screens > 5.5", can primary action be reached with one thumb? (bottom half of screen)
- **Older users:** User base includes 40-60+ selling household items. Font size readable enough? (minimum 14px body text)
- **Slow connections:** Does design degrade gracefully on 3G? (skeleton loading, not blank screen)

---

## Layer 4 — Marketplace UX Patterns

### Trust & Safety Signals

- Seller credibility: Verification status (badge, reviews, response rate) visible before buyer initiates contact?
- Photo authenticity: Does design encourage real photos? (camera-first upload, not gallery-first)
- Price transparency: Price unambiguous? "Thương lượng" (negotiable) clearly marked
- Scam indicators: Does design help users spot suspicious listings?

### Conversion Friction

- **Listing-to-contact:** How many taps from viewing listing → contact seller? Target: ≤ 2 taps
- **Post-ad completion rate:** Count required fields. Each added required field reduces completion ~10%
- **Registration wall:** Is user forced to register before doing anything valuable?

### Supply vs Demand UX

- **Seller experience:** Posting an ad should be as easy as posting on social media. > 3 minutes = flow too complex
- **Buyer experience:** Finding the right listing should feel like browsing, not searching a database
- **Both sides:** After transaction, is there a prompt to rate/review? (builds marketplace trust loop)

### Vertical-Specific Patterns

| Vertical | Key UX considerations |
|----------|----------------------|
| GDS (Goods) | Quick browse, impulse-buy feel. Photo is king. Fast price comparison |
| PTY (Property) | High-consideration purchase. Detailed filters, map view, multiple photos |
| JOB (Jobs) | Two user types (employer/jobseeker). Simple application flow. Salary transparency |
| VEH (Vehicle) | Technical specs matter. Side-by-side compare. Trust signals extra important |

---

## Output Format — UX Review Report

```markdown
# UX Review: [Screen/Feature Name]

**Vertical:** [GDS/PTY/JOB/VEH] | **Platform:** [Web/App] | **User:** [Buyer/Seller/Both]
**Reviewed:** [date] | **Designer:** [name]

## Summary
[2-3 sentences: overall assessment. Ready to ship? Biggest concern?]

**Score: [X] / 20** (5 points per layer)

---

## 🔴 Critical Issues (must fix)

### [Issue title]
**Layer:** [IA / Usability / Accessibility / Marketplace]
**Where:** [specific element or area in the design]
**Problem:** [what's wrong and why it matters to the user]
**Suggestion:** [concrete fix, referencing DS components if applicable]

---

## 🟡 Major Issues (should fix)
### [Issue title]
**Layer:** / **Where:** / **Problem:** / **Suggestion:**

---

## 🟢 Minor Issues (polish)
- [Issue]: [one-line description + suggestion]

---

## ✅ What's Working Well
[List 2-3 things the design does well]

---

## Layer Scores

| Layer | Score | Notes |
|-------|-------|-------|
| Information Architecture | /5 | [one-line summary] |
| Usability | /5 | [one-line summary] |
| Accessibility | /5 | [one-line summary] |
| Marketplace Patterns | /5 | [one-line summary] |
```

---

## Scoring Calibration

### Information Architecture
- **5:** Clear hierarchy, obvious primary action, user always knows where they are
- **3:** Hierarchy mostly clear but competing elements or unclear navigation
- **1:** User confused about what to do or where to look first

### Usability
- **5:** Follows all heuristics, error prevention in place, efficient for new and returning users
- **3:** Most heuristics followed but gaps in error handling or efficiency
- **1:** Multiple heuristic violations causing user frustration or task failure

### Accessibility
- **5:** Meets WCAG AA, good touch targets, works in Vietnamese mobile contexts
- **3:** Most contrast ratios pass but touch target or labelling issues
- **1:** Significant contrast failures, small touch targets, no alt text

### Marketplace Patterns
- **5:** Trust signals present, conversion friction minimal, vertical-appropriate UX
- **3:** Basic marketplace patterns present but missing trust or efficiency optimisations
- **1:** Missing critical trust signals, high friction, or patterns don't fit vertical

---

## Quick Checklist

### Visual Consistency
- [ ] Colours from DS Color Tokens (no arbitrary hex)
- [ ] Typography follows type scale (H1, H2, Body, Caption...)
- [ ] Spacing uses 8pt grid (4, 8, 12, 16, 24, 32, 48...)
- [ ] Border radius consistent across same-type components
- [ ] Icons from DS icon library, correct size (16, 20, 24px)

### Component Usage
- [ ] Uses correct DS components, doesn't create new ones if existing ones work
- [ ] Variant matches context (primary/secondary, filled/outlined...)
- [ ] Button labels use action verbs ("Đăng tin" not "OK")

### Interaction States
- [ ] Default, Hover/Pressed, Focused, Disabled, Loading, Empty state, Error state, Success state

### Content & Copy
- [ ] No placeholder text ("Lorem ipsum")
- [ ] Microcopy clear, correct tone of voice
- [ ] Error messages describe issue and resolution
- [ ] CTA buttons unambiguous

### Design File Quality
- [ ] Frames named correctly
- [ ] Layer groups tidy and named
- [ ] No leftover hidden layers
- [ ] Auto Layout used for flexible components

---

## Rules

1. **Be specific, not vague.** "The CTA is unclear" → give exact component + fix.
2. **Reference DS components in suggestions.** When suggesting a fix, reference the exact Chợ Tốt DS component.
3. **Always include positives.** All-negative review is demoralising. Highlight what works.
4. **Prioritise by user impact.** Confusing CTA is more critical than border radius off by 2px.
5. **Consider the Vietnamese user.** Language, cultural context, device usage, network conditions.
6. **Don't redesign — review.** Flag issues and suggest directions. Designer makes the final decision.

---

## Resources

- CT Design Principles: https://701search.atlassian.net/wiki/spaces/PROD/pages/3414327730
- Design System: https://701search.atlassian.net/wiki/spaces/PROD/pages/3099230689
- WCAG Contrast Checker: https://webaim.org/resources/contrastchecker/
- Figma DS file: https://www.figma.com/design/DfQM6G9p8PSNEoOzNGRjWD/v3.0-CHOTOT-Design-System
- Plugin source: product-design
