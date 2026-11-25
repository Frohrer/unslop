---
name: unslop
description: Design and review UI so it looks made by a careful designer, not generated. Use whenever building, styling, or reviewing any interface - web pages, landing pages, dashboards, components, forms, apps, artifacts, HTML/CSS/React/Tailwind - and whenever the user says "unslop", "de-slop", "this looks AI-generated", "make it look less generic", or asks for a design review. Applies UX laws, concrete craft rules, and a list of AI design tells to avoid.
---

# Unslop

Generated UI tends to look the same everywhere: cream backgrounds, pills above the headline, three icon cards, sparkle icons, glows. People spot it at once and trust the product less. This skill has three parts:

1. **UX principles** to use deliberately while deciding what goes on the screen.
2. **Craft rules** that make the details look right.
3. **Slop tells**: defaults to avoid unless the user asks for them.

Use all three on every UI task. They are not a checklist to run once at the end. They should shape the first draft.

## Modes

- **Build mode** (making or editing UI): before writing markup, decide the main task of the screen, the primary action, and what can be hidden (Pareto, progressive disclosure). Write the code following the craft rules. Before handing over, run the review checklist at the bottom on your own output and fix what fails.
- **Review mode** (the user asks you to review or unslop something): read the code or look at a screenshot. Report findings grouped as **Slop tells**, **Craft fixes**, and **UX issues**. Each finding names the element, the rule it breaks, and the concrete fix (for example "`.hero h1` line-height 1.6 → 1.1"). Then offer to apply them, or apply them if the user said "unslop this".

When a user request conflicts with a rule here (they want a cream background, or a sparkle icon), the user wins. These are defaults, not laws.

---

## Part 1: UX principles

For each principle: what it means, then how to apply it while building.

### Layout and grouping

**Law of proximity.** Things placed close together are read as a group.
- Space within a group should be clearly smaller than space between groups (roughly 1:2 or more). A label sits close to its field; the next field sits farther away.
- Don't space everything evenly. Even spacing makes everything look unrelated.

**Law of common region.** Things inside the same box or background are read as a group.
- Use a shared background or border only when grouping isn't already clear from spacing. Proximity first, then a region.
- Don't put everything in its own card (see slop tells). A region means something only if most things aren't in one.

**Uniform connectedness.** Things joined by a line or frame read as more related than things that aren't.
- Use connecting lines for steps, timelines, and parent/child relations. Use dividers sparingly, since they connect what they sit between as well as separating it.

**Law of similarity.** Things that look alike are read as related and expected to work alike.
- Everything clickable shares one style per level (primary, secondary, link). Never style a non-clickable element like a button or link.
- If two things behave differently, make them look different.

**Law of Prägnanz.** People read complex images as the simplest shape they can.
- Prefer simple, clear shapes and alignments. A layout should reduce to a few rectangles on a strong grid.
- Fewer alignment lines: every element should line up with something else.

### Attention and memory

**Von Restorff effect.** Among similar things, the one that differs is the one people notice and remember.
- Spend this on one thing per view: the primary action or the key number. If three things are highlighted, none is.
- The recommended pricing plan, the primary button, the critical alert get the contrast. Everything else stays calm.

**Serial position effect.** People remember the first and last items in a list best.
- Put the most important nav items, features, or options first and last. Bury the least important in the middle.
- On a landing page, the opening and closing sections carry the message; the closing section should repeat the primary CTA.

**Peak-end rule.** People judge an experience by its best moment and by its end, not the average.
- Design the finish deliberately: success states, confirmation screens, the "done" moment after checkout or signup. Make them clear and satisfying, and tell people what happens next.
- Find the one moment that can delight (instant result, a useful preview) and polish that first.

**Zeigarnik effect.** Unfinished tasks stick in people's heads more than finished ones.
- Show unfinished state honestly: "2 of 5 steps done", unsaved drafts, incomplete profile prompts. Use it to bring people back, never to nag or guilt.

**Goal-gradient effect.** The closer people are to a goal, the harder they push to finish.
- Show progress in multi-step flows. Start progress above zero when part is already done (account created counts as step 1).
- Keep the remaining steps short and visible.

### Effort and complexity

**Cognitive load.** The mental effort a screen takes. Cut anything that costs effort without helping.
- Every element must earn its place. Remove decorative icons, duplicate labels, redundant helper text, and text that restates the heading.
- One primary action per screen. Limit choices; group the rest.

**Recognition over recall.** Picking from what's on screen is easier than remembering it.
- Show options instead of asking people to type them: dropdowns, recent items, suggestions, visible shortcuts, previews.
- Keep context visible: show what was selected, where the user is, what a setting currently is.

**Progressive disclosure.** Show the essentials first and reveal advanced options only when asked.
- Put advanced settings behind "More options", an expandable section, or a second step. Keep the default path short.
- Never hide something most users need just to make the screen look clean.

**Tesler's law.** Some complexity can't be removed, only moved, so the app should carry it instead of the user.
- Do the work for people: autodetect formats, infer defaults from context, validate inline, format input as they type (phone numbers, cards, dates). Accept messy input instead of demanding exact formats.

**Pareto principle.** Roughly 80% of use comes from 20% of features.
- Identify the few core actions and make them the biggest, fastest, and most visible. Everything else gets less space.

**Occam's razor.** When two options work equally well, choose the one with fewer parts.
- Fewer components, fewer colors, fewer font sizes, fewer wrappers. If removing an element loses nothing, remove it.

**Default effect.** Most people keep whatever is already selected.
- Choose defaults that are best for the user: the most common choice, the safe choice, the privacy-respecting choice. Never pre-select upsells or opt-ins against the user's interest.

**Parkinson's law.** A task stretches to fill the time it's given, so make it quicker than people expect.
- Shorten flows: fewer fields, autofill, one-click options, sensible defaults. If a form can be done in under a minute, say so.

**Paradox of the active user.** Nobody reads the manual; people just start using the product, so teach in context.
- No tutorial walls or long onboarding tours. Use inline hints, good empty states, tooltips on first use, and examples in placeholders of the right format (but never as the label).

**Aesthetic-usability effect.** People think a good-looking design is easier to use and forgive its small flaws.
- Polish is not optional; it changes how usable the product feels. But don't let looks hide real usability problems. Fix both.

---

## Part 2: Craft rules

### Typography

- **Left-align long text.** Never center paragraphs longer than two lines. Centering is for short headings and single lines only.
- **Body text stays regular weight.** Use bold only for things that must stand out. If everything is bold, nothing is.
- **Headlines get tighter line height than body.** Body around 1.5-1.6; headlines around 1.05-1.2, tighter as size grows. Large headlines can also take slightly negative letter-spacing.
- **Sentence case for labels, buttons, headings, and menu items.** "Create new project", not "Create New Project".
- **Align mixed text sizes on the baseline**, not the vertical center (`align-items: baseline` in flex rows with a price and a unit, a title and a meta label).
- **Stacked text: space by the smaller text's height.** When a heading sits above a smaller line (title + subtitle, name + role), the gap between them is roughly the font size of the smaller text.
- **Headings get more space above than below.** A heading belongs to the content after it, so it sits closer to that content (for example 2× space above, 1× below).
- Limit to a few font sizes on a clear scale and one or two typefaces.

### Color

- **Don't use pure gray.** Neutrals tinted slightly blue (or tinted toward the brand hue) look alive; pure `#888` looks dull.
- **Keep the same hue across every shade of a color.** A palette from 50 to 900 should not drift hue; change lightness and saturation, not hue. (If any drift, darker shades may shift very slightly warmer or cooler on purpose, never by accident.)
- **On colored backgrounds, tint the text** with a dark or light version of the background hue instead of using pure black or white-on-gray.
- **In dark mode, tone down brand colors.** Lower saturation and adjust lightness so they don't glow or vibrate on dark surfaces. Don't just invert.
- Use color for meaning (primary action, status, error) and keep the rest neutral.

### Spacing and layout

- **More padding on the sides than on top.** Buttons, inputs, tags, and cards: horizontal padding roughly 1.5-2× vertical.
- Use a spacing scale (for example 4/8/12/16/24/32/48/64) and stick to it.
- Group with spacing first (proximity), regions second, lines last.

### Buttons and actions

- **Button text is about half the button's height.** A 32px button takes roughly 14-16px text; a 48px button roughly 18-20px text plus more padding. Don't put tiny text in a tall button.
- **Label buttons with what they do.** "Save changes", "Send invite", "Create account", never "Submit", "OK", or "Click here".
- **Keep destructive actions far from safe ones.** Delete goes away from Save: other side of the dialog, separated by space, styled differently, and confirmed if it can't be undone.
- **Landing pages: make the primary CTA much bigger than feels normal.** Larger text, generous padding, strong contrast. It should be the most obvious thing on the screen.

### Depth

- **Layer several small shadows instead of one big one.** For example: `0 1px 2px rgba(0,0,0,.06), 0 2px 4px rgba(0,0,0,.06), 0 8px 16px rgba(0,0,0,.06)`. One large blurry shadow looks fake. Tint shadows toward the background hue rather than pure black.

### Forms

- **Labels go above fields.** Placeholders vanish when typing, so never use them as the only label. Placeholders may show an example format.
- Show errors inline next to the field, in plain language, saying how to fix it.

### Tables and data

- **Right-align numbers in tables** so digits line up, and use tabular figures (`font-variant-numeric: tabular-nums`). Left-align text columns. Right-align the header of a numeric column too.

### Empty states

- **Every empty state gets a CTA.** Say what will appear here, and give the button that makes it appear ("No projects yet" + "Create project").

---

## Part 3: Slop tells to avoid

These mark a design as generated. Don't use them by default. If one is truly the best choice for this design, use it on purpose and once.

### Layout and components
- **Everything in a card.** Most content should sit on the page, grouped by spacing. Use cards only for repeated, distinct objects.
- **Three icon cards in a row** (icon, bold title, one line of text, ×3). Present features with real screenshots, examples, or a different structure.
- **Numbered sections** (01 / 02 / 03 labels on sections that aren't real steps).
- **Colored left borders** on cards, callouts, or quotes as decoration.
- **Bento grids** of mismatched tiles used as default feature layout. *(suggested addition)*
- **Logo marquees and "Trusted by" rows** with placeholder or invented logos. *(suggested addition)*

### Headline area
- **Pills above the headline** ("✨ New: AI-powered…" badges).
- **Overused eyebrows** (small uppercase labels above every heading). One at most, if it carries information.
- **One italic word in the headline** (often in a serif) for emphasis.
- **Blurry glows behind the hero** (colored blobs, radial gradients, aurora effects).
- **Gradient text on headlines**, especially purple-to-blue. *(suggested addition)*

### Decoration and icons
- **Arrows on every button** (→ or ↗ after every label). Only where it signals navigation away, and rarely.
- **Sparkle icons** (✨) to signal AI or "magic".
- **Pulsing green dots** ("live", "online", "available") unless it shows real live status.
- **Dithering** and grain overlays as texture.
- **Little dots between words** ("Fast · Simple · Secure").
- **Emoji as bullet points or section icons.** *(suggested addition)*
- **Glassmorphism** (frosted translucent panels) as the default surface. *(suggested addition)*

### Color and type
- **Cream / beige / off-white "paper" backgrounds** as the default.
- **Instrument Serif** (and the generic elegant-serif-headline + sans-body combo it stands for).
- **Default purple/indigo-to-blue gradients** as the brand color. *(suggested addition)*
- **Huge corner radius on everything.** Pick a radius that suits the product and keep it consistent. *(suggested addition)*

### Motion
- **Sections fading or sliding in on scroll.** Content should be there when the user arrives. Keep motion for feedback on actions.

### Copy
- **The word "quiet"** ("quiet confidence", "quietly powerful").
- **The word "real"** ("real results", "real people", "for real work").
- **Made-up stats** ("10,000+ teams", "99.9% faster", "4.9★ rating") unless the user supplied the number. Use a clear placeholder like `[stat]` instead.
- **Two-word sentences** as punchy rhythm ("Fast. Simple. Yours." / "No setup. No fuss.").
- **Hype verbs**: unlock, elevate, supercharge, seamless, effortless, game-changing, reimagine. *(suggested addition)*
- **Fake testimonials** with invented names and headshots. Use placeholders. *(suggested addition)*
- **Generic CTAs** like "Get started" when a specific one fits ("Start free trial", "Book a demo"). *(suggested addition)*

---

## Review checklist

Run this before handing over any UI. Fix anything that fails.

**UX**
- [ ] One clear primary action per screen, visually the most prominent thing (Von Restorff).
- [ ] Spacing makes groups obvious without needing boxes (proximity before common region).
- [ ] Core 20% of actions are the most visible; advanced options are disclosed progressively.
- [ ] Defaults are the best choice for the user.
- [ ] Multi-step flows show progress; end states are designed (goal-gradient, peak-end).
- [ ] Nothing on screen that costs effort without helping (cognitive load, Occam).
- [ ] The app does the formatting and inference, not the user (Tesler).

**Craft**
- [ ] No centered paragraphs; body regular weight; sentence case.
- [ ] Headline line height tighter than body; headings closer to what follows.
- [ ] Mixed sizes baseline-aligned; stacked text spaced by the smaller size.
- [ ] Neutrals tinted, not pure gray; color shades keep one hue; text on color is tinted.
- [ ] Dark mode brand colors toned down.
- [ ] Horizontal padding > vertical; button text ≈ half the button height.
- [ ] Buttons say what they do; destructive actions far from safe ones.
- [ ] Layered small shadows, not one big one.
- [ ] Labels above fields; numbers right-aligned with tabular figures.
- [ ] Every empty state has a CTA; landing CTA is oversized.

**Slop**
- [ ] None of the Part 3 tells, unless the user asked for one or it's a deliberate, single use.
- [ ] No invented stats, logos, or testimonials.
