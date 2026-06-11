# Geography Lesson Converter — setup

Converts 60-minute Geography lesson PowerPoints into the 2026 house style
(100-minute) for Exmouth Community College, using Claude. This repo exists so the
**House Style template** can be pulled into any Claude chat by URL (Claude
Projects can't hold a `.pptx` as knowledge, but it can `curl` one from here).

## Repo layout

```
geog-lesson-converter/
├── README.md
├── Lesson_Converter_Rules_v1_5.md         # the converter playbook (also lives in the Project)
└── house-style/
    └── house_style_v4.pptx                 # the 30-template house style (v4)
```

Notes:
- Keep the template filename **space-free** (`house_style_v4.pptx`, not
  `House Style v4.pptx`) so the raw URL needs no `%20` encoding.
- The repo must be **public** for the raw URL below to work without a token. If
  the template shouldn't be public, use the Google Drive route instead (see
  "Private alternative" at the bottom) — don't paste GitHub tokens into chat.

## The raw URL

```
https://raw.githubusercontent.com/philoutram/geog-lesson-converter/main/house-style/house_style_v4.pptx
```

(Swap `philoutram` / repo name / branch if yours differ.)

## Project setup (do once)

1. Create a Claude Project.
2. Add **`Lesson_Converter_Rules_v1_5.md`** as Project knowledge (this is the
   detailed reference — the "how").
3. Paste the block below into the Project's **custom instructions** (this is the
   always-on behaviour — the "do this every time", plus the fetch step and the
   pointer to the rules).

### Project custom instructions (paste this)

```
This project converts 60-minute Geography lesson PowerPoints into the 2026 house
style (100-minute) for Exmouth Community College.

The authority for HOW to convert is the file "Lesson Converter Rules v1.5" in
this project's knowledge. Follow it.

Default workflow for every lesson:
1. Download the House Style v4 template into your environment from:
   https://raw.githubusercontent.com/philoutram/geog-lesson-converter/main/house-style/house_style_v4.pptx
2. Read the attached source lesson.
3. Produce the FULL slide-by-slide mapping table (source slide -> template + note).
4. CHECK IN on any unclear match (source slide + 1-3 candidate templates +
   rationale) and wait for my sign-off before building. Never guess an
   ambiguous match.
5. Build source-first with STRICT CHROME / FLEXIBLE BODY: title bars and styling
   follow the template exactly; adapt the body to the actual lesson content
   rather than shoe-horning it, and flag anything adapted.
6. Run the pre-ship validation gate (no animation orphans, no empty timing
   shells, no dangling refs, no changesInfo/revisionInfo) and visual QA before
   delivering. PowerPoint is the only definitive open-test — flag anything risky.
```

## Using it (each lesson)

Open a new chat **inside the Project**, attach the source lesson `.pptx`, and say:

```
Convert this lesson.
```

That's it — the instructions fetch the template, the knowledge file carries the
detail, and the converter will come back with the mapping table + any check-ins
before it builds.

### One-off (no Project)

If you ever run it outside a Project, attach the source and paste:

```
Convert this 60-min Geography lesson into the 2026 house style, following the
attached Lesson Converter Rules v1.5. Download the House Style v4 from
https://raw.githubusercontent.com/philoutram/geog-lesson-converter/main/house-style/house_style_v4.pptx
first. Source-first, strict chrome / flexible body. Give me the mapping table and
check in on unclear matches before building; run the pre-ship gate before
delivering.
```
(…and attach `Lesson_Converter_Rules_v1_5.md` too, since there's no Project knowledge.)

## Versioning

When a new failure mode or template appears, bump the ruleset (v1.6, …), commit
it here, and update the copy in Project knowledge. The template and rules stay
version-controlled together.

## Private alternative (no public repo)

Put `house_style_v4.pptx` in Google Drive instead, keep the same Project
instructions but replace step 1 with "fetch House Style v4 from my Google Drive."
Claude pulls it via the Drive connector — same one-step result, stays private.
