# Suno Workflow: Multi-Character Cypher

How we build a song where 3+ characters have distinct voices and interact. Based on current community best practices (Suno v4.5/v5.5/v6 era).

## The Core Problem

Suno does not reliably hold multiple distinct voices inside a single generation. Voices bleed together or swap lines. The fix is structure + passes.

## Step 1: Meta Tags in Lyrics

Label every line with the character's name in brackets, placed immediately before their lines:

```
[Relentless Raven]
Yo, welcome to Hip Hop 101...

[Dynamic Dino]
I'm ready to go, let's rock the show!

[Perfect Persian Cat]
Perfection takes time — but I'm already fine.
```

This is the single biggest lever for character separation.

## Step 2: Style Prompt

Describe the arrangement AND the vocal split explicitly. Example:

```
boom bap hip hop cypher, 92 BPM, dusty vinyl drums, warm bass,
three distinct vocalists: deep gravelly male baritone teacher,
bright energetic male, smooth cool female alto,
call and response verses, all three on the hook
```

Set **style influence to 100%** in Custom Mode so the prompt drives the output.

## Step 3: Build in Passes

1. Generate a 10–20 second stem with Voice 1 only. Discard anything flawed. Spend credits to find a keeper.
2. Extend that stem 2–4 lines at a time for phrasing control.
3. Introduce Voice 2 by changing something audible (vocal tag + different delivery) and start the new audio immediately after the previous voice ends — place it to the hundredth of a second in the edit window.
4. Repeat for Voice 3.
5. Assemble all stems in **Suno Studio** by dragging clips into one project.

## Step 4: Inspiration Tracks (Optional)

Use up to 4 Inspiration slots: 2 tracks per vocalist so Suno learns each voice separately. For 3 personas, use 1 strong reference per persona and don't fill all 4 slots — overloading makes one voice dominate.

## Step 5: Persona Lock

For recurring characters, save a Persona from a clean generation and reuse it. Write a tight vocal anchor and paste it byte-for-byte:

```
[Vocal: deep gravelly male baritone, breathy, slight rasp on high notes, teacher energy]
```

## Failure Modes We Watch For

- Voices swapping each other's lines mid-song → fix with tighter meta tags and shorter sections.
- Persona drift between generations → re-anchor with the same vocal description.
- One voice dominating → reduce Inspiration slots, balance section lengths.
- Both characters saying the same kind of thing at the same length → write genuinely different parts.

## Tools

- Suno Custom Mode (v5.5 or v6)
- Suno Studio for assembly
- Suno Speech (beta) — alternative for pure dialogue/skit sections with background music