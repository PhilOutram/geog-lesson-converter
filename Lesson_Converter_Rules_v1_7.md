# Lesson Converter — Conversion Rules v1.7 (generic)

*The generic conversion rule-set for the Geography lesson converter. Defines (0) philosophy, (1) the slide-type → template taxonomy **and the match-confidence/user-check-in step (§1.1)**, (2) content & styling rules, (3) structural-integrity / repair gates, and (4) pipeline placement. Definitive house style: **`Geog_2026_House_Style_PPTX_v4`** (30 templates; §1 table numbered to the actual deck). v1.7 (from the NH3 Volcano-distribution run) makes three content fixes: **maximise image size** by default (§2.4 — fill the content area, don't just fit a small slot), the **Enquiry-Question-bar 28pt + shrink-on-overflow** rule (§2.11), and a **table-formatting default** (§2.12 — fill space, Calibri 18, bold centred header, white fill). v1.6 resynced the §1 table to v4 numbering and split the two Frayers (§2.8); v1.5 added "strict chrome, flexible body" (§0) and the ambiguous-match check-in (§1.1); v1.4 added the empty-timing-shell gate (§3.2) and the `spPr/xfrm/ext` resize rule (§3.7). Everything here applies to any source deck.*

---

## 0. Philosophy

- **Source-first.** Pour the source's lesson content **faithfully**. Do not generate, summarise, or "improve" it.
- **Strict chrome, flexible body.** The template's **chrome is binding**: title bar / banner wording-format, icon, colour palette, and layout furniture follow the house-style template **exactly**, every lesson — this is what makes the output look consistent. The template's **body content is a scaffold, not a cage**: use it only where the source content genuinely maps to it. Where it doesn't fit, **adapt the body to the actual content** rather than shoe-horning the content into the template's slots (don't truncate, pad, reword, or drop source content to make it fit). When the body is adapted beyond a straight pour, mark `⚠ ADAPTED: <what changed>` so the user can review.
- **Title bars are the strict exception.** Banner text follows the template's canonical format (e.g. `FRAYER MODEL: <topic>`, `Checks for understanding`, the I/We/You-do label band) even when the source phrased its heading differently — consistency of the title bar trumps source wording.
- **Insert only genuinely missing structural slides.** Flag content gaps as `⚠ PLACEHOLDER`, never invent.
- **Re-skin = transplant + pour (+ adapt).** Take the correct template slide, transplant it over the source slide, pour the source's verbatim text/media into the matching slots, and adapt the body where the fit isn't clean (per above).
- **Leave-as-is only as a last resort.** A slide is left untouched only when no template type matches *and* the slide already reads acceptably. The type-driven mapping in §1 should catch almost everything; genuinely unclear cases go to the §1.1 check-in.

---

## 1. Slide-type taxonomy → template map  *(the core decision procedure)*

For each source slide, detect its **type** from the signals below, then transplant the named house-style (HS) template. Detection is by content signal, **not by source slide position**.

*Template numbers are **House Style v3** (29 templates).*

| # | Source slide type | Detection signals | → HS template | Extra rules |
|---|---|---|---|---|
| 1 | **Title** | Topic + "Lesson N" + crest; first slide | **HS1** | — |
| 2 | **Do it Now (questions)** | "Do it Now"; numbered THIS/PREVIOUS UNIT + SKILLS FOCUS prompts | **HS2** | — |
| 3 | **Do it Now — Answers** | As above + "ANSWERS / purple pen"; answer overlays | **HS3** | §2.1 parity check; §2.9 reveal animation |
| 4 | **Enquiry Question / Learning Objectives** | "EQ:" bar + objective rows (🌍🏔📍) + "Key Words" box | **HS5** | §2.10 variable objective rows |
| 5 | **Topic Specification / spec table** | Titled slide whose body is the AQA spec table (Key idea \| Specification content) | **HS6** | pour table verbatim |
| 5b | **Generic titled two-block** | Titled slide with two parallel content blocks (not a spec table) | **HS4** (Title + lighter/darker box) | map each block → one box |
| 6 | **Information / knowledge slide — NO question or task** | explanatory content (prose and/or diagram/images), no question and no task. **A slide with no title is an information slide by default.** | **HS7** | §2.4 image sizing |
| 7 | **Think-Pair-Share** | THINK / PAIR / SHARE cards | **HS8** | — |
| 8 | **Discussion image-reveal** | "What do you think…?" + a dominant image + a big caption answer | **HS9** | §2.4 image sizing |
| 9 | **Video** | embedded video / "while watching" / a video link/URL | **HS10** | §2.2 keyword box; §2.3 video link |
| 10 | **Knowledge collage** | image collage + "how can we…/optional activity" | **HS11** | §2.4 |
| 11 | **Map/diagram TASK** | big map or diagram + partner task ("Window/Door partner", "what does this show") | **HS12** | §2.4 |
| 12 | **Information / knowledge slide — WITH a question or task** | same as HS7 content but carries a clear question or task instruction | **HS13** | §2.4 |
| 13 | **Collect-the-evidence (Consolidation)** | **hand-holding-jigsaw icon in the left of the title banner**; "circulate / collect evidence / read the resources" task | **HS14** | §2.4 |
| 14 | **Consolidation TASK + chart** | a graph/chart + numbered task + "Tip" box | **HS15** | — |
| 15 | **Knowledge prose + Keywords** | continuous explanatory prose + a Keywords list | **HS16** | §2.5 fit-to-box |
| 16 | **Silent-solo (Consolidation)** | image collage + "silent solo / mind map" task | **HS17** | §2.4 |
| 17 | **Frayer model (plain)** | 4-quadrant Definition/Characteristics/Examples/Non-examples, no side furniture | **HS18** | §2.8; table+oval resize §3.7 |
| 17b | **Frayer model + side furniture** | Frayer quadrants **plus** a side prompt/image (e.g. "What is a plate margin?") | **HS19** | §2.8 — dedicated template |
| 18 | **Checks for understanding (Q)** | "Checks for understanding" + Q only | **HS20** | — |
| 19 | **Checks for understanding (Q + A)** | as above + revealed answer | **HS21** | §2.7 answer in bold |
| 20 | **Booklet reference** | "Go to section pX of your booklet" + image + highlight box | **HS22** | §2.6 **no** banner; §2.7 answers bold |
| 21 | **Cold call** | "Cold call" + single Q | **HS23** | — |
| 22–24 | **I do / We do / You do** | the I/We/You-do label band | **HS24 / 25 / 26** | keep coloured label + pill |
| 25 | **Live marking** | "Live marking" + teacher notes | **HS27** | — |
| 26 | **Codes** | "Codes" + SPAG / marking key | **HS28** | — |
| 27 | **Exit Ticket** | "Exit Ticket" + leaving questions | **HS29** | — |
| 28 | **Activity Register** | icon legend grid | **HS30** | — |

**Gap-fill / cloze image exercises** (passages with `___` blanks delivered as baked-in images) have no single-line Q/A template. Route them to **HS22** (booklet-reference styling: image-led, no banner) per §2.6, with the answer variant in bold (§2.7). If the cloze is live text rather than an image, prefer HS16.

**Information / knowledge slide decision (the key clarifier).** Many source slides are explanatory diagrams or text. Classify them by *furniture*, not appearance:
1. **Hand-holding-jigsaw icon in the title banner?** → Collect-the-evidence → **HS14**.
2. **No title at all?** → it is an information slide (proceed to 3).
3. **Carries a clear question or task instruction?** → **HS13** (info slide *with* task). **Otherwise** → **HS7** (info slide, no question/task — the default knowledge slide).
4. Specific furniture overrides the above: a **partner task** ("Window/Door partner") → HS12; a **chart/graph + Tip** → HS15; a **Keywords-list prose** slide → HS16; a **single dominant captioned image to reveal** → HS9.

### 1.1 — Match confidence & the user check-in *(mandatory)*

Source decks are inconsistent and will not all map cleanly. For each source slide, assign a **match confidence**:

- **Clear** — one template is an obvious fit and the body content maps to its slots without distortion.
- **Ambiguous** — *any* of: no template fits well; two or more fit plausibly; the chrome matches but the body content only partially maps; or the slide is an odd one-off the taxonomy doesn't anticipate.

Then:

1. Produce the **full mapping table** (every source slide → proposed template + a one-line note), so the user sees the whole plan. Clear matches are listed for transparency and proceed without interrogation — **do not** make the user confirm obvious matches one by one.
2. **Surface only the ambiguous ones for a check-in.** For each, present: a one-line summary of the source slide, **1–3 candidate templates with the rationale for each**, and let the user **confirm one, choose another, request a generic info template (HS7/HS13), or mark it `⚠ PLACEHOLDER`**. Offer this as tappable options where the interface allows.
3. **Wait for the user's decision on every ambiguous slide before building.** Never silently guess an ambiguous match. The user may also override a "clear" call — the table is theirs to redirect.

This check-in is cheap (a short table + a few choices) and prevents the expensive failure of building a slide onto the wrong template.

---

## 2. Content & styling rules

**2.1 — Question → Answers content-parity check.** When a slide is immediately followed by its "Answers" slide (e.g. Do it Now → Do it Now Answers), the **base prompts must match** between the two. After conversion, diff the question text of the pair; if the prompts differ, raise `⚠ PARITY: Q/A base content differs` rather than silently shipping.

**2.2 — Video slides always keep a Keywords box.** Every video slide retains the template's Keywords box. If the source supplies keywords, pour them in. **If it does not, populate the box with a bold `Keywords:` header and `…` on the line below** — never leave the box empty or delete it. This keeps the font/size correct for the teacher to type into, and lets them delete the whole box in one action if unwanted.

**2.3 — Video link/URL always carried.** Preserve the source's video link. Render it under a bold `Video link:` label as a live hyperlink. If the source link is reference text (e.g. "Use this link: … 7 mins"), keep the wording but still wire it as a hyperlink. Never drop the URL.

**2.4 — Image sizing & placement — maximise, don't just fit.** Keep content images **as large as the slide allows** — this is a default, not an exception. The template slot gives the anchor/position, but a *content* image (the main map / photo / diagram — **not** the small banner icon) should be **scaled up to fill the available content area** (below the banner, inside the slide margins), preserving aspect ratio and centred, rather than left at the slot's default size. Whichever of width or height hits the content box first sets the scale.
- **Single content image:** fill the content area — roughly full slide width × the height between the banner and the bottom margin (on a 13.33×7.5″ slide that's ≈ up to 10–11″ × 5.5–6″, aspect-dependent).
- **Multiple images:** partition the content area (side-by-side or stacked) and size each to the largest that fits its share. Don't leave images small with empty space around them; rearrange to use the space.
- **Constraints:** preserve aspect ratio (never stretch), never overflow the slide edge, and don't scale a labelled diagram so far down that its labels become unreadable.
- If the source has more images than slots, enlarge/rearrange to use the space rather than dropping them; flag `⚠ EXTRA IMAGE` only if they genuinely can't fit.
- **Watch for template rotation:** clear any `rot` transform (`rot="0"`) before pouring a normally-oriented source image, or it displays sideways. Resize via `spPr/xfrm/ext` (§3.7).

(Reference: NH3 slides 6–10 and 17–20 — the converter under-sized these; the target is fill-the-space, e.g. a content image grown from 5.1×3.6″ to 10.6×5.9″.)

**2.5 — Fit-to-box / font sizing.** Body text boxes use the template's default size **but must fit**. Rule: start at template size; if the verbatim content overflows the box, step the font down (in 2pt steps) until it fits, to a floor of 16pt; below that, raise `⚠ OVERFLOW`. Prefer enabling shape **autofit** (`normAutofit`) so PowerPoint also reflows on edit. Where content is short, nudge **up** toward the template max so the box isn't sparse.

**2.6 — Booklet-reference slides (HS22) carry no green/Knowledge banner.** These are navigation slides; suppress the knowledge/coloured banner entirely. Gap-fill cloze exercises routed to HS21 follow the same rule.

**2.7 — Answers in bold.** On any answer variant (HS21 answer, HS22 answer / cloze-answer), the revealed answer text is **bold** to distinguish it from the question.

**2.8 — Frayer model: plain (HS18) vs with side furniture (HS19).** A plain 4-quadrant Frayer → **HS18**. A Frayer that also carries a side prompt and/or image (e.g. "What is a plate margin or boundary?") → **HS19**, the dedicated v4 template with a side text box + image beside the quadrants — use it rather than improvising side furniture on HS18. In both, the quadrants are a real **table + oval shape** (not a flattened image): when resizing, resize the table and the oval **together**, and squeeze the oval toward a circle as the table narrows so the proportions stay right. (§3.7 applies — resize via `spPr/xfrm/ext`.)

**2.9 — Reveal animations travel with their boxes.** *(See §3.2 — this is the structural counterpart.)* If a template's answer/keyword boxes are click-to-reveal, preserve the entrance animation when the box is kept, and add one (clone an existing click node) when a new reveal box is introduced.

**2.10 — Variable objective rows on the EQ/LO slide (HS5).** HS5's "Today's lesson involves" is a **multi-row layout** (default 2 rows). The objective rows are ordinary text-box shapes (emoji box + text box) over rounded-rectangle backgrounds; the **Key Words list is a SmartArt** (`diagrams/data1.xml` + `drawing1.xml`). To match a source with a different objective count, **clone or remove a row triple** (background + emoji box + text box, with fresh `cNvPr` ids) and re-space all rows evenly. Pour the source's Key Words into the SmartArt by editing the keyword text in **both** `data1.xml` and `drawing1.xml` (the cached drawing); if the source/template keyword counts differ, add/remove SmartArt nodes rather than overstuffing. Remember to copy all five diagram parts (`data1`, `layout1`, `quickStyle1`, `colors1`, `drawing1`), wire the `diagramData/Layout/QuickStyle/Colors/diagramDrawing` relationships, and add their `[Content_Types].xml` overrides — a transplant that copies only images will leave the SmartArt relationships dangling.

**2.11 — Enquiry Question bar (HS2/HS3) — 28pt + shrink-on-overflow.** The "Enquiry Question:" bar on the Do it Now slides uses **28pt** text with the box set to **shrink text on overflow** (`<a:normAutofit/>`). Pour the source's enquiry question at 28pt and let autofit shrink a long question, rather than manually downsizing or letting the text spill past the bar. This is baked into House Style v4 — on transplant, **preserve** the box's `normAutofit` and 28pt base; don't strip the autofit or rebase the font.

**2.12 — Table formatting.** When a source table is poured onto a slide (data table, comparison grid, etc.), default to: **fill the available content space** (size the table to the content area, not a small default); body text **Calibri 18**; **header row bold**, its text **centred horizontally and vertically**, on a **shorter** header-row height with **sensible (taller) body-row heights**; **white table background/fill**. Exception: where a template defines its own table style (e.g. the **HS6** spec table with its Key idea | Specification content header), keep the template's styling and just pour the content. (Reference: NH3 slide 16.)

---

## 3. Structural integrity & repair gates

These are **hard gates** — a converted deck must pass all of them before delivery. The first two issues cause PowerPoint "repair" prompts that LibreOffice-based QA does **not** catch.

**3.1 — Strip co-authoring `changesInfo`.** Decks edited in PowerPoint-web carry `ppt/changesInfos/changesInfo1.xml`, a change-log that references shapes by slide-id/shape-id. Re-skinning invalidates it. On every convert, remove: the `ppt/changesInfos/` part, its `_rels`, the relationship in `presentation.xml.rels`, and the `[Content_Types].xml` override.

**3.2 — Animation-orphan rule (the big one).** When a shape is **deleted** during conversion, also delete **every** animation reference to it:
- its `<p:par>` node(s) in `<p:timing>` (walk up from `<p:spTgt spid="…">` to the per-click `<p:par>` and remove it), **and**
- its `<p:bldP spid="…">` entry in `<p:bldLst>` (remove; if the `bldLst` becomes empty, remove the `bldLst` too).

An orphaned `spTgt`/`bldP` pointing at a missing shape is a guaranteed PowerPoint repair trigger. (This bites whenever a template carries reveal animations and you delete an unused box — e.g. an empty booklet text box on HS22.)

**Then collapse the empty timing shell.** Removing the last `<p:par>` from a slide's main sequence leaves a hollow `<p:timing>` — a `<p:seq nodeType="mainSeq">` whose `<p:childTnLst>` is now empty. That empty mainSeq is **itself** a repair trigger (and a silent one: orphan-spid checks pass because there are no targets left to be orphaned). Rule: after orphan removal, if a slide's `<p:timing>` contains no real animation (no `<p:par>` with an `<p:spTgt>` under the mainSeq), **delete the entire `<p:timing>` element**. A slide with no animations must have no `<p:timing>` at all. Add to the §3.5 gate: *no `<p:timing>` may contain an empty mainSeq `<p:childTnLst>`.*

**3.3 — Reveal preservation / cloning.** Keep a box → keep its `<p:par>` + `<p:bldP>` (they travel together). Add a reveal box → clone an existing click `<p:par>` + `<p:bldP>` and retarget the `spid`. Reveals are essentially free to preserve and cheap to add; the template carries the scaffold.

**3.4 — Diagram (SmartArt) & HD-photo parts travel whole.** When transplanting a template that uses SmartArt or `mc:AlternateContent` image layers, a copy-the-images-only transplant will leave parts dangling. Specifically: copy all SmartArt diagram parts and wire their relationships (§2.10); and if a picture has an `<a14:imgLayer r:embed>` HD-photo (`.wdp`) backing, copy the `.wdp`, add its relationship (type `…/2007/relationships/hdphoto`) and a `wdp` Default content-type — or remove the `imgLayer` and keep the plain blip.

**3.5 — Pre-ship validation gate.** Assert all of:
- every `spid` in `<p:timing>` / `<p:bldLst>` resolves to a live `<p:cNvPr id>` (no animation orphans);
- **no `<p:timing>` contains an empty mainSeq `<p:childTnLst>`** (the silent repair trigger from §3.2);
- every `r:id`/`r:embed`/`r:dm`/`r:lo`/`r:qs`/`r:cs` in slide XML exists in that slide's `.rels`, and every `.rels` target file exists (no dangling refs);
- no duplicate `<p:cNvPr id>` within a slide's `spTree`;
- no `changesInfo` **or `revisionInfo`** part or reference remains (§3.1);
- no orphaned notes slides (a `notesSlide` part referenced by no slide — remove the part, its rels and content-type override);
- every part is well-formed XML and `pack.py` validation passes.

**3.6 — QA caveat.** LibreOffice render QA does **not** surface §3.1/§3.2 problems — it tolerates orphaned animations and ignores `changesInfo`. Treat the §3.5 checks as mandatory programmatic gates *in addition to* visual QA. The only definitive open-test is PowerPoint itself.

**3.7 — Resize via `spPr/xfrm/ext`, never `.//ext`.** When moving or resizing any shape/picture, target the transform extent at `p:spPr/a:xfrm/a:ext` **explicitly**. A generic descendant search (`element.find('.//a:ext')`) returns the *first* `<a:ext>` in document order, which is frequently a blip/`extLst` extension (`<a:ext uri="…">`) rather than the transform — so the position updates but the size silently does not. Symptoms: a picture squeezed into its old frame (e.g. a landscape image left in a portrait box, which then overflows the slide and renders a blank thumbnail), or boxes that move closer together but keep their old height and overlap. This bug bit three times on the first deck (cloze frame, cloze size, slide-4 objective rows). Always resolve `xfrm = sp.find('p:spPr/a:xfrm')` then set on its direct `a:off`/`a:ext` children.

---

## 4. Pipeline placement

Run order per source slide: **detect type (§1) → assign match confidence (§1.1)**. Then per deck: **present the full mapping table + check in on every ambiguous match (§1.1) → wait for user sign-off**. Only then, per slide: **transplant template (with all diagram/HD-photo parts, §3.4) → pour content verbatim → adapt body where the fit isn't clean (§0, flag `⚠ ADAPTED`) → apply content rules (§2) → structural cleanup (§3.1–3.3) → fit-to-box (§2.5)**. Finally per deck: **validation gate (§3.5) → visual QA → deliver**.

This rule-set is the conversion authority for the master spec; the Activity Register and palette/layout sections of the spec are unaffected by it.
