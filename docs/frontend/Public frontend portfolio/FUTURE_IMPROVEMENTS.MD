suppose laptop screnn is x-y plane. and Z(+z - outside of laptop screen and -z - inside of laptop screen) is depth. 

# FUTURE IMPROVEMENTS - 03-02-2026
- HERO SECTION: one highlight effect should be appear on card border all four edges like with animations
- first entry: hero card should be come from -z - +x plane and when it show user in +y - +x plane.
- exit: when user scroll up it goes in +z - +x plane.

- apply for other like projects 

# PRESENT IMPROVEMENTS - 

# Home page: 
-done:  3D is not showing why ?

- text 

# color combinations problem
- 3D effect color combinations and text color combinations, not good
- text like "Hi, I'm Your Name
Full Stack Developer crafting beautiful and performant digital experiences"
there is too much diffculties to analysize this. 

- what i want : when HR, founder see my portfolio, they can scan as fast as possible and get all information about me immediately.

- problem 2: 
in the ss there is problme only introduction part. it's not visible clearly only this part.

so what is solution for this ? 
for other I have anlysised that when we scroll up an background glassmorphism appear and it's show text upon this very clearly. 

can we add this solution or other also avaialbe tell me first

- problem 3: opposite of my thinking 
present: a blur background card show text upon this very clearly.

future what i want: first of all 3D effect should be appear, after that if user scroll up (not down, ) then blur background card appear and it's show text upon this very clearly.


- problem 4:  
present: show hero section, when i scroll too much it's bacground appear 

future what i want: i want to show completely 3D effect first, after that when user scroll up (how i can control how much user scroll ? i want mnimum scroll: at last tell me for manaully control) then blur background card appear and it's show text upon this very clearly.


- problem 5: 
 - what i want : completly remove text from hero section.     and  show only 3D effect. 
 - when user come on home screen it's see only 3D effect. and useer will be able to play with 3D effect.

 - when user scroll up (how i can control how much user scroll ? i want mnimum scroll: at last tell me for manaully control) then blur background card appear (a glass  come from 3d effect and it's show hero section : i want this type of animation) and it's show text upon this very clearly.

    - i want this animation for all other glass card also like - project, let build something amazing, educaiton etc.

- card come from multiple directions north, south, east, west and other also.

- prbolem 6:
- present: not going south-east direction, not clearly visible on screen, not proper coming.
- you have check using open browser.
- future update: going south-east direction
    - coming north-west direction (proper: take 10 degree clockwise direction angle)

- take accordingly to you that you could do 

# update - 
# 🧩 Problem 6 — Directional Animation Debug & Correction (Elite Prompt)

You are acting as a **Principal UI/UX Engineer and Motion Systems Architect** with strong
debugging discipline and real-world production experience.

## Problem Context
There is an existing **directional scroll animation** for a glass card / section that is
**not behaving as intended**.

You must first **analyze the current behavior by checking it in an open browser**
before proposing any changes.

---

## Present Issues (Observed)
- The animation is **not moving toward the South-East direction**
- The element is:
  - Not clearly visible on screen
  - Not entering the viewport properly
  - Lacking spatial clarity and intent
- The motion feels incorrect and visually confusing

---

## Expected Future Behavior (Target State)

### Entry Direction
- The element must **enter from the North-West direction**
- The direction must be:
  - Precise
  - Intentionally angled
  - Offset by **approximately 10° clockwise** from the pure diagonal
- The motion should feel **clean, controlled, and spatially logical**

### Exit Direction
- After visibility and focus, the element must:
  - Move toward the **South-East direction**
  - Maintain consistent depth, opacity, and clarity during motion

---

## Motion Quality Requirements
- Entry must be **clearly visible within the viewport**
- No clipping, partial visibility, or awkward positioning
- Movement should feel:
  - Smooth
  - Physically believable
  - Cinematic rather than mechanical

---

## Debugging & Correction Expectations
- Identify why the current animation:
  - Misses the intended direction
  - Fails to stay visible
- Isolate whether the issue is:
  - Coordinate system
  - Direction vector
  - Scroll mapping
  - Easing or timing
- Propose a **corrected motion strategy** aligned with the target behavior

---

## Control & Adjustability
- Allow for **manual tuning**, including:
  - Direction angles
  - Entry and exit vectors
  - Visibility thresholds
  - Animation speed and easing

---

## Constraints & Philosophy
- No guesswork
- No random tweaks
- Every change must be **reasoned and justified**
- Think like an owner fixing a production issue

Respond with:
- Clear analysis
- Explicit reasoning
- A correction strategy aligned with real-world frontend systems


# You should see:

✨ 3D Galaxy star field background with moving particles
🔮 Glass-style cards with blur effects
🌈 Gradient text on headings
🎭 Smooth animations on scroll


# other problems:
- remeember : global.css file can also effect /admin/  routes ui/ux ?
- what i want: i want to type of color combination: 
    - for admin: i want purple that is already exist.
    - for public: i want green that is already exist.


# 3D effect:
- future: i want to add a button, like play button when i click this button the 3d effect rotate in all axis like x, sometime y and sometime z axis.

- give me suggestion where i can add this button.

- i want 3d-effect button in bottom right side.

- present: when i hover on button, it's show only arrow.
  - when i click on button, not active anything.

- future: when i hove on button, it's show hand.
  - when i click on button, active all 3d effect.

-  add "min 5 sec" text in 3d effect button. in bottom with small text
  - if this button click for play then minimum 5 second it's disable to pause effect.
  - after 5 second it's enable to pause effect.

- future: card animation match the vibe with this 3D effect when card fade in or fade out. so change animation


# music - 

- i want to add a music in this portfolio also. 
  - add a button play and pause button above of 3d effect button.
  -  when i hover this button:
      - give hint: 1. minminum time 10 sec (modify in future by admin)
                  2. take earphone or alone type hint



# Home section -

## Hero section 
present: currently it coming and control with mouse
future: i want when user scroll up then it should come continuosly, not half, not stop in b/w screen with same animation. but not control with mouse. 
  -  user again scroll then go with same animation. 
  - first it should come continuously ---> show on screen ---> go with same animation continuosly

## other sections -
- i want this effect for other section also like featured project.
  - use different direction for each card.

# Timeline section -

- use proper spacing b/w company name and description.

## for card layout - 

ROLE
You are acting as a Senior Product Designer and Staff Software Engineer.

Your task is to design a WORK / EXPERIENCE CARD SYSTEM using a
TIMELINE-BASED LAYOUT with ALTERNATING SIDES.

This system must be:
- recruiter-friendly
- visually balanced
- scalable for multiple experiences
- consistent with industry-standard resume patterns

------------------------------------------------------------

CORE CONCEPT — ALTERNATING TIMELINE LAYOUT

Each experience card is split into TWO VERTICAL SECTIONS:

- One side: Timeline (visual guide only)
- Other side: Main Content (primary information)

The side placement ALTERNATES based on experience order.

------------------------------------------------------------

ALTERNATING RULE (MANDATORY)

Experience Index (1-based):

1st Experience:
- Timeline → LEFT
- Content  → RIGHT

2nd Experience:
- Content  → LEFT
- Timeline → RIGHT

3rd Experience:
- Timeline → LEFT
- Content  → RIGHT

4th Experience:
- Content  → LEFT
- Timeline → RIGHT

Pattern:
ODD  → Timeline Left, Content Right
EVEN → Content Left, Timeline Right

------------------------------------------------------------

CONTENT HIERARCHY (STRICT)

Order of importance:

1. Job Title
   - Largest text
   - Highest contrast

2. Company Name
   - Secondary emphasis

3. Duration
   - Muted color
   - Smaller size
   - Optional calendar icon

4. Description
   - Max 1–2 lines
   - Impact-driven
   - No filler sentences

------------------------------------------------------------

RESPONSIVE CONSTRAINT (IMPORTANT)

On MOBILE:
- Timeline always moves to LEFT
- Content always on RIGHT
- NO alternation on small screens

Reason:
- Preserve readability
- Avoid zig-zag scanning

------------------------------------------------------------

SCALABILITY REQUIREMENT

This system must support:
- Any number of experiences
- Future roles without redesign
- Clean stacking and spacing

------------------------------------------------------------

QUALITY CHECK (MANDATORY)

Before finalizing, confirm:
- Job title is the most dominant element
- Timeline never competes with content
- Alternation improves readability, not noise
- Recruiter can scan all roles in under 10 seconds

------------------------------------------------------------

FINAL PRINCIPLE

"Time shows progression.
Content proves competence.
Alternation creates balance."

Design accordingly.

## timeline, tag
 - remove time perios from main content and take it outsidde of box in opposite direction.
      main content: left,  time-periods: right
      main content: right, time-periods: left

- also add tag for work, education. 

- for work: time periods text should be green color.
- for education: time periods text should be violet type. already prent in education tag color.

- draw a line from main timeline to show time periods
  - for work: it sould be start from black and end with green , already present in main timeline
  - apply same for eduction, change color etc.

  - update design and small text: Work, Educcation tag of the work and education. give more attractive look.

- update:
for work: 
icon color: lab(87 -97.83 54);
time period text color: color(a98-rgb 0.44 0.95 0.6);
time period text size: large

for experience:
icon color: lab(51 34.29 -80.89);

- i want a hight light in time-period(icon+text).
- is there any solution to show time period clearly like background add glassmorphis or any other. tell me all possible solution, then i decide

- present : tag is not good condition: layout, text, padding etc.
- work and education tag: you have align in best way and best layout for these tag in card. give all suggestion first. and then implement.


- present: time period box and tag: work, education - is much bigger. make it small and attractive.


- present: for last card, there is no main time line show.
- future: show a main time line for last card also.

- present : no animation when user scroll.
- future: add animation for each card when user scroll screen.
