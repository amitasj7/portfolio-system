Below is the pre-UI/UX definition tree you should lock before designing your login page (or any screen).

Read this as a decision checklist, not theory.

0. Product Intent (ROOT)
Product Intent
├─ Purpose of screen
│  ├─ Login / Access control
│  ├─ Speed > Delight
│  └─ Trust > Experiment
├─ Primary user
│  ├─ Recruiter
│  ├─ Hiring manager
│  └─ You (admin)
└─ Context
   ├─ Desktop-first
   ├─ Professional environment
   └─ Low cognitive load

1. Design System Foundations (MUST DEFINE FIRST)
Design Foundations
├─ Color System
│  ├─ Primary color (brand)
│  ├─ Secondary color (support)
│  ├─ Neutral palette
│  │  ├─ Background
│  │  ├─ Surface
│  │  └─ Border
│  ├─ Semantic colors
│  │  ├─ Success
│  │  ├─ Error
│  │  └─ Warning
│  └─ Contrast rules (accessibility)
│
├─ Typography System
│  ├─ Font family
│  │  ├─ Heading font
│  │  └─ Body font
│  ├─ Font scale
│  │  ├─ H1 → H6
│  │  └─ Body / Caption
│  ├─ Line height rules
│  ├─ Font weight usage
│  └─ Text color hierarchy
│
├─ Spacing System
│  ├─ Base unit (4 / 8)
│  ├─ Vertical rhythm
│  ├─ Padding scale
│  └─ Margin rules
│
└─ Layout Grid
   ├─ Page width
   ├─ Columns
   ├─ Gutters
   └─ Alignment rules

2. Interaction Rules (HOW UI BEHAVES)
Interaction Design
├─ Input behavior
│  ├─ Focus state
│  ├─ Error state
│  ├─ Disabled state
│  └─ Success state
│
├─ Button behavior
│  ├─ Primary button rules
│  ├─ Secondary button rules
│  └─ Hover / Active / Disabled
│
├─ Feedback
│  ├─ Loading indicators
│  ├─ Error messages
│  └─ Success confirmation
│
└─ Motion (optional)
   ├─ Transition duration
   ├─ Easing style
   └─ When motion is allowed

3. Visual Language (LOOK & FEEL)
Visual Language
├─ Shape language
│  ├─ Border radius
│  ├─ Sharp vs soft UI
│  └─ Consistency rules
│
├─ Elevation
│  ├─ Shadow levels
│  ├─ When to use shadow
│  └─ Flat vs layered
│
├─ Iconography
│  ├─ Icon style (outline/solid)
│  ├─ Icon size rules
│  └─ Icon color rules
│
└─ Imagery
   ├─ Illustration vs photos
   ├─ Tone (abstract / realistic)
   └─ Usage limits

4. Accessibility & Quality Gates
Accessibility
├─ Color contrast compliance
├─ Keyboard navigation
├─ Focus indicators
├─ Screen reader labels
└─ Error clarity

5. Content & Copy Rules
Content Strategy
├─ Voice
│  ├─ Professional
│  ├─ Calm
│  └─ Clear
├─ Tone
│  ├─ Neutral
│  └─ Reassuring
├─ Text length limits
├─ Error message format
└─ CTA wording rules

6. Constraints (VERY IMPORTANT)
Constraints
├─ Device targets
│  ├─ Desktop
│  └─ Tablet (optional)
├─ Browser support
├─ Performance budget
├─ Scalability
│  ├─ Future auth methods
│  └─ Theming support
└─ Engineering simplicity

One brutal truth (remember this)

UI without defined systems is decoration.
UI with systems is product design.




## We’ll define Color System + Typography
(only decisions, no UI yet)

STEP 1 — COLOR SYSTEM (FOUNDATION)
Rule before starting

👉 One brand color. Everything else supports it.

Color System Tree
Color System
├─ Brand Colors
│  ├─ Primary
│  │  ├─ Used for: CTA, focus, links
│  │  └─ Emotion: Trust / Confidence
│  └─ Secondary
│     ├─ Used sparingly
│     └─ Never compete with primary
│
├─ Neutral Palette (MOST IMPORTANT)
│  ├─ Background
│  │  ├─ Page background
│  │  └─ Subtle contrast only
│  ├─ Surface
│  │  ├─ Cards
│  │  └─ Modals
│  ├─ Border
│  └─ Divider
│
├─ Text Colors
│  ├─ Primary text
│  ├─ Secondary text
│  ├─ Muted text
│  └─ Inverse text
│
├─ Semantic Colors
│  ├─ Success
│  ├─ Error
│  ├─ Warning
│  └─ Info
│
└─ Usage Rules
   ├─ Primary color max usage %
   ├─ Never use semantic colors as brand
   └─ Contrast minimums

Senior shortcut 🧠

If you get confused →
90% Neutral + 10% Brand

STEP 2 — TYPOGRAPHY SYSTEM
Rule before starting

👉 Typography does more design work than colors.

Typography Tree
Typography System
├─ Font Family
│  ├─ Primary font (UI + body)
│  └─ Fallback fonts
│
├─ Type Scale
│  ├─ H1 (Page title)
│  ├─ H2
│  ├─ H3
│  ├─ Body (default)
│  └─ Caption / Helper
│
├─ Font Weights
│  ├─ Regular
│  ├─ Medium
│  └─ Semibold
│
├─ Line Height Rules
│  ├─ Headings
│  └─ Body text
│
├─ Letter Spacing
│  ├─ Normal text
│  └─ Buttons / labels
│
└─ Text Usage Rules
   ├─ Max heading length
   ├─ Sentence case vs Title case
   └─ CTA text style

Login page typography truth

One heading

One sentence

No paragraphs

STEP 3 — COMBINED UI GUARDRails (VERY IMPORTANT)
Global UI Rules
├─ No more than 2 font sizes on login screen
├─ No more than 1 accent color
├─ No bold body text
├─ Buttons always use brand color
└─ Errors always use semantic error color





## UI / UX DEFINITIONS (FINAL PRE-DESIGN TREE)
0. Mode Strategy
Theme Strategy
├─ Default Mode
│  └─ Light Mode (first-class)
├─ Secondary Mode
│  └─ Dark Mode (derived, not redesigned)
└─ Theme Switching
   ├─ Token-based (no hard colors)
   └─ Same layout, same hierarchy

1. Color System (Dual Mode)
Color System
├─ Brand Colors
│  ├─ Primary
│  │  ├─ CTA buttons
│  │  ├─ Focus rings
│  │  └─ Links
│  └─ Accent (optional)
│     └─ Used only for highlights
│
├─ Neutral Palette
│  ├─ Light Mode
│  │  ├─ Background
│  │  ├─ Surface
│  │  ├─ Glass surface
│  │  └─ Border
│  └─ Dark Mode
│     ├─ Background
│     ├─ Surface
│     ├─ Glass surface
│     └─ Border
│
├─ Text Colors
│  ├─ Primary text
│  ├─ Secondary text
│  ├─ Muted text
│  └─ Inverse text
│
├─ Semantic Colors
│  ├─ Success
│  ├─ Error
│  ├─ Warning
│  └─ Info
│
└─ Color Usage Rules
   ├─ Brand color only for actions
   ├─ Glass never uses brand color
   ├─ Text contrast ≥ accessibility minimum
   └─ Same semantic meaning in both modes

2. Glassmorphism System (VERY IMPORTANT)

Glass is not decoration.
It is a material system.

Glassmorphism Rules
├─ Glass Surface Definition
│  ├─ Background blur level
│  ├─ Background opacity
│  └─ Frosted effect consistency
│
├─ Allowed Usage
│  ├─ Login card
│  ├─ Modal surfaces
│  └─ Floating panels
│
├─ Forbidden Usage ❌
│  ├─ Buttons
│  ├─ Inputs
│  ├─ Text backgrounds
│  └─ Error messages
│
├─ Border Treatment
│  ├─ Soft translucent border
│  └─ No heavy outlines
│
└─ Glass Safety Rules
   ├─ Must work without blur
   ├─ Must maintain readability
   └─ Dark mode glass uses LESS opacity


🧠 Senior rule

If glass reduces readability → remove glass.

3. Typography System (Mode-Safe)
Typography System
├─ Font Family
│  ├─ Single sans-serif family
│  └─ System fallback stack
│
├─ Type Scale
│  ├─ Page Title (Login heading)
│  ├─ Body text
│  └─ Helper / caption
│
├─ Font Weights
│  ├─ Regular (body)
│  ├─ Medium (labels)
│  └─ Semibold (heading)
│
├─ Line Height
│  ├─ Headings (tight)
│  └─ Body (comfortable)
│
└─ Text Rules
   ├─ No text on noisy backgrounds
   ├─ Same sizes in both modes
   └─ Color handles hierarchy, not size

4. Layout & Spacing System
Layout System
├─ Grid
│  ├─ Desktop-first
│  ├─ Centered container
│  └─ Max width constraint
│
├─ Spacing Scale
│  ├─ Base unit (8px logic)
│  ├─ Vertical rhythm
│  └─ Generous padding
│
└─ Alignment Rules
   ├─ Centered login card
   ├─ Left-aligned text inside card
   └─ Single-column form

5. Interaction & States
Interaction Design
├─ Inputs
│  ├─ Default
│  ├─ Focus
│  ├─ Error
│  └─ Disabled
│
├─ Buttons
│  ├─ Primary (brand color)
│  ├─ Hover / Active
│  └─ Disabled
│
├─ Feedback
│  ├─ Inline errors
│  ├─ Loading state
│  └─ Success state
│
└─ Motion Rules
   ├─ Subtle transitions only
   ├─ No entrance animations on login
   └─ Motion reduced when prefers-reduced-motion

6. Accessibility & Quality Gates
Accessibility
├─ Contrast safe on glass
├─ Keyboard navigation
├─ Visible focus states
├─ Screen-reader friendly labels
└─ Error clarity (no vague text)

7. Constraints (DO NOT IGNORE)
Constraints
├─ Performance
│  ├─ Blur should not block low-end devices
│  └─ Fallback for no-blur support
├─ Scalability
│  ├─ Same tokens reused everywhere
│  └─ Future pages inherit system
└─ Engineering Simplicity
   ├─ Token-driven design
   └─ No hardcoded colors

One brutal reminder (tattoo this mentally)

Glassmorphism is a spice, not the meal.
If everything is glass → nothing is premium.