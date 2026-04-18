# Design Document — Assembly Shark Tank Case Study

## 1. Profile Baseline Declaration

- **Profile selection**: `profiles/business_insight.md`
- **Selection rationale**: This is a competitive analysis + strategic consulting case study examining Assembly's STP strategy and Shark Tank appearance. The business insight profile fits the analytical depth and data-driven nature.
- **Referenced dimensions**: High information density, conclusion-first narrative, structured expression through cards/grids, data source annotations, insight-driven content.
- **Deviation notes**:
  - The existing HTML presentation has a warmer, more editorial aesthetic (serif headings, forest green palette) vs. the cooler consulting style of the profile. We follow the reference source's warmer editorial style.
  - The profile prohibits shadows and gradients, but the reference source uses subtle gradient overlays and shadow effects on cards. We follow the reference source.
  - Body font size can go to 18px given the high density of some slides.

## 2. Style Baseline Declaration

- **Style anchor identification**: The Economist/Monocle editorial style crossed with premium D2C brand aesthetics (like Away, Bellroy). The reference source combines high editorial elegance (serif titles, generous whitespace) with structured business analysis.
- **Referenced dimension explanation**: We reference the color scheme (dark forest green + warm beige), the typography hierarchy (serif display + sans body), the card-based content containers, and the alternating dark/light page rhythm from the HTML presentation.
- **Reference scope declaration**: Style + Color scheme + Layout (not content — we enhance with additional slides)

## 3. Extract Style from Reference Source

### 3.1 Typographic Character
Premium editorial meets structured analysis. Elegant serif headings create authority, while clean sans-serif body text ensures readability. The overall impression is refined, thoughtful, and premium — matching Assembly's own brand positioning.

### 3.2 Color Extraction

| Role | Color | Usage |
|------|-------|-------|
| primary | #0F3D35 | Dark forest green — cover backgrounds, section headers, dark slide backgrounds, key structural elements |
| secondary | #6E8F8B | Muted teal — secondary labels, accent borders, supporting text, chart elements |
| accent | #A56A3A | Warm tan — verdict flags, highlight boxes, key insights, important data callouts |
| background | #F3EDE5 | Warm beige/cream — light slide backgrounds, card interiors |
| text | #2E2E2E | Charcoal — body text on light backgrounds |
| textLight | #F3EDE5 | Beige — text on dark backgrounds |
| surface | #FFFFFF | White — cards on light backgrounds |
| surfaceDark | rgba(255,255,255,0.04) | Subtle card backgrounds on dark slides |
| border | #D6CEC4 | Warm border color for cards and dividers on light backgrounds |
| borderDark | rgba(255,255,255,0.08) | Subtle borders on dark backgrounds |

### 3.3 Font Hierarchy Extraction

| Level | Font | Size | Treatment |
|-------|------|------|-----------|
| Cover title | SortsMillGoudy | 48-56px | Light weight, italic for emphasis words |
| Section heading | SortsMillGoudy | 36-44px | Light weight, line-height ~1.1 |
| Page eyebrow/label | QuattrocentoSans | 11-12px | All caps, letter-spacing 0.2em, secondary color |
| Body text | QuattrocentoSans | 18-20px | Light weight, line-height 1.6-1.8 |
| Card heading | SortsMillGoudy | 20-24px | Regular weight |
| Card body | QuattrocentoSans | 14-16px | Light weight, line-height 1.6 |
| Data/metrics | SortsMillGoudy | 32-42px | Light weight for large numbers |
| Annotations | QuattrocentoSans | 11-12px | Muted color, small caps |

### 3.4 Text Box and Container Styles
- **Cards**: Rounded rectangles with 6-8px border radius, subtle borders (1px solid), no heavy shadows
- **Separation**: Cards for grouped content, thin divider lines between sections, whitespace between major elements
- **Decorative elements**: Subtle noise texture overlay (very low opacity), thin accent borders on left side of quote boxes
- **Dark page cards**: rgba(255,255,255,0.04) background with rgba(255,255,255,0.08) border
- **Light page cards**: White or #F8F6F2 background with #D6CEC4 border

### 3.5 Image Style
- **Icons**: Emoji-style icons or minimal line icons, used sparingly for value proposition cards
- **Tables**: Minimal style — thin borders, alternating subtle backgrounds, no heavy styling
- **Charts**: Bubble chart for positioning map; muted color palette following theme colors; minimal grid lines
- **Illustrations**: None needed — this is a text and data-driven analytical presentation

## 4. Layout System

### 4.1 Global Layout Characteristics
- **Page size**: 1280 x 720 (16:9)
- **Page margins**: 60px left/right, 50px top, 40px bottom
- **Unified elements**:
  - Section number label (top-left area): "01 / 08" style, mono font, muted
  - Section eyebrow label: all caps, letter-spaced, secondary/accent color
  - No persistent navigation bar — clean editorial style

### 4.2 Special Page Layouts
- **Cover**: Dark forest green background, left-right split (title left, stats grid right), large serif title with italic emphasis
- **Closing**: Dark background, centered layout, large serif headline, tag pills at bottom

### 4.3 Content Page Layout Patterns
- **Two-column split**: Left text content + right cards/visuals (used for Product, Segmentation slides)
- **Full-width stacked**: Title + full-width content area with cards in rows (used for STP Evaluation, Key Actions)
- **Grid layout**: Title + multi-column card grid (used for Recommendation 3-horizon)
- **Left-right comparison**: Two-column comparison with central divider (used for Competitive Positioning)
- **Bubble chart layout**: Title + bubble chart with legend below (NEW for Positioning Map)

## 5. Style Usage Rules

- **Dark slides** (Cover, Shark Critique, Competitive Positioning, Recommendation): Use primary (#0F3D35) or darker (#0a2921) background, textLight for body, beige for headings, teal-light for accents
- **Light slides** (Product, Segmentation, STP Evaluation, Key Actions): Use background (#F3EDE5) or offwhite (#F8F6F2), text (#2E2E2E) for body, charcoal for headings
- **Verdict/flag elements**: Use accent (#A56A3A) for important callouts, with rgba(165,106,58,0.15) background
- **Critical/negative indicators**: Red (#C0392B) with rgba(192,57,43,0.15) background
- **Positive indicators**: Forest green (#0F3D35) or teal (#6E8F8B) with tinted backgrounds

## 6. Risk Prohibitions

- [ ] Do NOT use bright, saturated colors — keep the muted forest/teal/beige palette throughout
- [ ] Do NOT use shadows on text or heavy drop shadows on cards — keep it flat and editorial
- [ ] Do NOT use gradient fills on shapes (except for subtle image masks on cover/closing)
- [ ] Do NOT use rounded rectangle shapes with excessive corner radius — keep 6-8px max
- [ ] Do NOT let body text go below 18px — minimum body font size is 18px
- [ ] Do NOT use generic stock photos or decorative illustrations — this is a data/text-driven case study
- [ ] Do NOT forget the alternating dark/light page rhythm — it creates visual variety
- [ ] Do NOT use different card styles on the same slide — keep card treatments consistent within each page
- [ ] Minimum annotation/footnote font: 11px; minimum card body font: 14px; minimum table/chart label: 11px

## 7. Theme Definition

```yaml
theme:
  colors:
    primary: "#0F3D35"
    primaryDark: "#0a2921"
    primaryMid: "#1B5A50"
    secondary: "#6E8F8B"
    secondaryLight: "#7FA3A0"
    accent: "#A56A3A"
    accentLight: "#B07A4F"
    background: "#F3EDE5"
    backgroundDark: "#E8E1D8"
    offwhite: "#F8F6F2"
    text: "#2E2E2E"
    textLight: "#3A3A3A"
    border: "#D6CEC4"
    red: "#C0392B"
    redLight: "#E88"
    gold: "#C9A84C"
  textStyles:
    coverTitle:
      fontSize: 52
      color: "$background"
      fontFamily: "SortsMillGoudy"
      lineHeight: 1.05
    sectionHeading:
      fontSize: 40
      color: "$text"
      fontFamily: "SortsMillGoudy"
      lineHeight: 1.1
    sectionHeadingLight:
      fontSize: 40
      color: "$background"
      fontFamily: "SortsMillGoudy"
      lineHeight: 1.1
    eyebrow:
      fontSize: 11
      color: "$secondary"
      fontFamily: "QuattrocentoSans"
      letterSpacing: 2
    body:
      fontSize: 18
      color: "$text"
      fontFamily: "QuattrocentoSans"
      lineHeight: 1.7
    bodyLight:
      fontSize: 18
      color: "#F3EDE5CC"
      fontFamily: "QuattrocentoSans"
      lineHeight: 1.7
    cardHeading:
      fontSize: 22
      color: "$primary"
      fontFamily: "SortsMillGoudy"
      lineHeight: 1.3
    cardBody:
      fontSize: 15
      color: "$textLight"
      fontFamily: "QuattrocentoSans"
      lineHeight: 1.6
    metric:
      fontSize: 36
      color: "$background"
      fontFamily: "SortsMillGoudy"
      lineHeight: 1
    annotation:
      fontSize: 11
      color: "#2E2E2E80"
      fontFamily: "QuattrocentoSans"
      letterSpacing: 1
  tableStyles:
    default:
      fontSize: 14
      fontFamily: "QuattrocentoSans"
      headerFill: "$primary"
      headerColor: "$background"
      headerBold: true
      bodyFill: ["#FFFFFF", "$offwhite"]
      bodyColor: "$text"
      border:
        style: solid
        width: 1
        color: "$border"
```