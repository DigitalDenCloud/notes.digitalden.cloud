---
title: "After Effects Workflow — Vertical 4K Gym Videos"
date: 2026-01-18
categories: [Video, Docuementation]
tags: [After Effects, Video Editing, Gym Filming, Sony A6700, Vertical Video]
description: "A baseline After Effects workflow for vertical gym videos. Marker-driven rep counters, cinematic motion, and export settings that survive platform compression. Built for repeatability."
---

## Overview

This is my After Effects workflow for editing vertical gym videos. The goal is to make weight look heavy, make lifts look intentional, and produce something that holds up on TikTok and YouTube Shorts without looking overproduced.

One master composition. Marker-driven rep counters so viewers see what you're lifting. Subtle motion so the frame feels alive. A consistent look across clips. Export settings that survive platform compression.

This is a baseline. A foundation you can build every edit on top of. Once it's set up, you're not making creative decisions on every export. You're just dropping in footage and letting the workflow do its job.

> **Good for**  
> Anyone editing vertical gym content for social platforms. Works well if you want cinematic motion and automated rep counting without manual text keyframing.
{: .prompt-info }

---

## Project Setup

### Composition

Everything downstream depends on this being correct.

| Setting | Value |
|---------|-------|
| Resolution | 2160 × 3840 (4K vertical, 9:16) |
| Frame Rate | 25 fps |
| Pixel Aspect | Square |
| Duration | Match or exceed full edit |

I use 25 fps because I'm in the UK, where the mains electricity runs at 50Hz. Gym lights flicker at this frequency. Shooting at 25 fps (or 50 fps for slow motion) keeps the shutter in sync with the lights and avoids banding or pulsing in the footage. 30 fps would fight the flicker.

This is the delivery comp. All clips, text, and adjustments live here or in precomps nested inside it.

### Adding Footage

Drag camera footage directly into the master comp. Each clip sits as its own layer.

For simple edits (scale animation, markers, a rep counter) working directly on the footage layer is fine. No need to precomp.

**When precomping helps:**

- Complex effects stacked on a single clip (colour grading + stabilisation + masks)
- Reusing the same styled clip across multiple videos
- Timeline getting overwhelming with layers

To precompose: select the layer, press `Cmd + Shift + C` (Mac) or `Ctrl + Shift + C` (Windows), and name it clearly — `Squat_Clip_01`, `Deadlift_Clip_02`.

For this workflow, I keep clips as direct layers unless the timeline gets messy.

### Framing

I shoot native vertical 4K by rotating the camera 90°. This is the professional approach when you're only delivering to vertical platforms. Full sensor resolution, exact composition while filming, no cropping loss.

**Why not shoot horizontal and crop to vertical:**

The maths doesn't work. Horizontal 4K is 3840 × 2160. When you crop a vertical 9:16 slice from that, you're limited by the height. You get a 1215 × 2160 image. That's not even full HD vertical. To fill a 2160 × 3840 vertical 4K comp, you'd have to scale up nearly 180%. From 1080p horizontal, it's even worse. Around 330% scale, which destroys the image.

Native vertical gives you full resolution with no upscaling.

**When horizontal + crop makes sense:**

- You need both horizontal (YouTube) and vertical (Reels) from the same shoot
- Multi-platform delivery where flexibility matters
- You accept the resolution loss for convenience

For gym content going straight to Instagram or TikTok, native vertical is cleaner.

**Framing while filming:**

Position yourself centrally in the frame. Vertical has more headroom and floor space than horizontal. Use it. Distance matters: stand the tripod back far enough that the full movement (you + barbell + bar path) fits comfortably. Too close and you clip the top or bottom of the lift.

In After Effects, minor repositioning and scale adjustments tighten the frame or add motion. If you plan to add wiggle later, scale slightly larger (101% to 103%) to prevent edges from showing during movement.

---

## Rep Counter System

I add rep counters because it's useful for viewers to see what weights you're hitting. Without them, people are guessing. That's difficult, especially with plates that look similar on camera. My videos are about showcasing strength, so the numbers matter.

### Markers

Markers drive the rep counter expression. A marker is a reference point you place on the timeline to mark a specific moment. Like a bookmark. It doesn't affect the video, it's just a visual flag that says "something happens here." Expressions can read marker positions and respond to them. That's how the counter knows when to update.

To add a marker, select the footage layer, scrub to the rep moment, and go **Layer → Add Marker**.

| Marker | Purpose |
|--------|---------|
| Marker 1 | State ready / weight display |
| Marker 2 | First rep happens |

The counter knows exactly when to switch. No guessing.

### Text Layer Setup

The rep counter is a text layer that displays the weight and rep count on screen. It updates automatically based on the markers you placed on the footage layer. No manual keyframing.

Before the first rep, it shows the weight: `190kg`. When a rep happens, it switches to the count format: `1 x 190kg`. This is driven by an expression that reads the marker positions.

**Setup:**

1. Layer → New → Text
2. Position vertically downward from the top right corner (TikTok overlays clutter the bottom and left edges)
3. Apply styling directly to the text layer

**Layer Order:**

The text layer must sit directly above the footage layer. The expression references the layer below it by index.

```
Text Layer (Rep Counter)
↓
Footage Layer (Squat_Clip_01)
```

### Text Styling

The rep counter is designed to stay readable in dark gyms, survive social compression, and remain visually consistent across clips. All styling is applied directly to the text layer, not via effects or adjustment layers.

**Font & Character Settings**

| Setting | Value |
|---------|-------|
| Font | Chakra Petch |
| Weight | Bold / Semibold |
| Case | Upper or mixed (no italics) |
| Tracking | 0 to +20 (slight spacing helps readability in motion) |
| Alignment | Left or centred (be consistent) |

**Fill Colour**

Terminal green works well with industrial gym lighting: `#6CFF8D`. Avoid pure neon green. Slightly muted reads better after compression.

**Stroke (optional but recommended)**

| Setting | Value |
|---------|-------|
| Colour | Dark grey or near-black |
| Width | 1–2 px |
| Position | Outside |

This helps the text hold up against bright plates or reflections.

**Drop Shadow**

Applied via Layer Styles → Drop Shadow. This creates separation without looking designed or glowy.

| Setting | Value |
|---------|-------|
| Opacity | 40% |
| Distance | 4 px |
| Size | 10–12 px |
| Angle | 135° |
| Colour | Near-black (RGB 0–10) |

If you see the shadow, it's too strong.

**Positioning**

Place vertically downward from the top right corner. This avoids TikTok's UI overlays on the bottom and left edges. Use the same position across all clips for consistency.

**Why styling is kept simple:**

- Expressions handle logic
- Text styling handles legibility
- No animations are baked into the text itself
- Motion comes from the footage, not the UI

This keeps the counter factual and grounded.

### Expression

An expression is a small piece of code that controls a property automatically. Instead of manually keyframing what the text says, the expression reads the marker positions and updates the text for you.

**To add the expression:**

1. Expand the text layer in the timeline
2. Find **Source Text** under the Text property
3. Hold `Alt` (Windows) or `Option` (Mac) and click the stopwatch icon next to Source Text
4. An expression field opens. Paste the code below.

```javascript
var L = thisComp.layer(index+1);
var weight = 190;
var reps = 0;

if (L.marker.numKeys >= 2 && time >= L.marker.key(2).time){
  reps = 1;
}

reps == 0 ? weight + "kg" : reps + " x " + weight + "kg";
```
{: file="Rep Counter Expression" }

**Why this works:**

- No layer naming required. References by index.
- Works with duplicates. Each counter is independent.
- One counter per clip. Deterministic, no accidental counting.

For multiple reps, extend the logic:

```javascript
var L = thisComp.layer(index+1);
var weight = 190;
var reps = 0;

if (L.marker.numKeys >= 2 && time >= L.marker.key(2).time) reps = 1;
if (L.marker.numKeys >= 3 && time >= L.marker.key(3).time) reps = 2;
if (L.marker.numKeys >= 4 && time >= L.marker.key(4).time) reps = 3;

reps == 0 ? weight + "kg" : reps + " x " + weight + "kg";
```
{: file="Extended Rep Counter Expression" }

---

## Editing & Motion

Static footage feels flat. Even when the subject is moving, a locked-off frame can feel like surveillance footage rather than something intentional. Adding subtle motion like scale, drift, and rotation gives the footage life. It feels like there's a camera man making decisions, even when there isn't. The viewer doesn't consciously notice it, but they should feel it.

### Hard Cuts

When clips are from different locations or lighting conditions, use a hard cut. Clip A ends, Clip B starts. No transition. Declare the scene change. Don't hide it.

### Exposure Dip (Blink Effect)

A subtle "blink" at the cut point. The image dips dark briefly, then recovers. This makes hard cuts feel intentional rather than abrupt.

**What's an adjustment layer?**

An adjustment layer is a blank layer that applies effects to everything below it in the stack. Instead of adding the effect directly to your footage, you add it to an adjustment layer. That way you can position and trim it independently.

**Setup:**

1. Layer → New → Adjustment Layer
2. Trim it to 6 frames, centred over the cut
3. Apply Effect → Color Correction → Lumetri Color
4. Keyframe the Exposure property

**Timing:**

If Clip A ends and Clip B begins at frame 10, the adjustment layer straddles the cut:

| Frame | Position | Exposure |
|-------|----------|----------|
| 7 | Start of dip | 0 |
| 9–10 | Cut point (peak dip) | -0.3 |
| 13 | End of dip | 0 |

The darkest point sits on the cut. The viewer blinks, the scene changes.

### Scale Animation (Push-In)

A slow scale from 100% to 105-110% creates a subtle push-in effect. It draws the viewer's eye toward the subject and adds forward momentum to the clip. Without it, the frame sits still while the action happens inside it. With it, the frame feels like it's leaning in.

Each clip resets its own motion. Don't carry animation across clips.

| Keyframe | Scale |
|----------|-------|
| Start | 100% |
| End | 105–110% |

Apply Easy Ease to both keyframes.

### Position Drift

A slow horizontal or vertical drift keeps the frame alive. Static footage can feel like a security camera. Drift gives the impression of a camera man tracking the subject, even when the tripod hasn't moved.

Keyframe the Position property:

| Keyframe | Position |
|----------|----------|
| Start | Centre |
| End | 20–40 pixels left, right, up, or down |

Keep it subtle. The viewer shouldn't consciously notice the drift.

### Subtle Rotation

A tiny rotation over the clip feels organic, like a handheld camera settling.

| Keyframe | Rotation |
|----------|----------|
| Start | 0° |
| End | 0.5° to 1° |

More than 1° starts to feel intentional. Less feels natural.

### Combining Movements

For a richer cinematic feel, combine scale + drift + rotation on the same clip. All three running together creates complex, organic motion from simple keyframes.

Example combination:

- Scale: 100% → 107%
- Position: centre → 30px right
- Rotation: 0° → 0.5°

Easy Ease all keyframes. The movements blend together. No single one dominates.

### Wiggle for Weight

Heavy lifts have impact. The bar bends, the floor shakes, you're grinding through the rep. A subtle wiggle on the frame translates that physical intensity to the viewer. It's not about simulating handheld camera. It's about making the weight feel heavy on screen.

There are two types of wiggle, and they serve different purposes.

**Ambient Wiggle (Continuous)**

Adds subtle physical presence to heavy lifts without drawing attention. Runs for the whole clip, not triggered by markers.

Applied to the footage layer's Position property:

```javascript
wiggle(0.35, 8)
```
{: file="Ambient Wiggle Expression" }

| Parameter | Value | Effect |
|-----------|-------|--------|
| Frequency | 0.35 | Slow vibration = heavy feel |
| Amplitude | 8 | Subtle movement |

Use for squats, deadlifts, heavy singles, and static tripod shots. Scale footage to 101–103% to prevent edges showing. Use sparingly.

**Struggle / Impact Wiggle (Marker-Driven)**

Translates strain, grind, or bar impact into visible force. Short duration only, triggered by markers, always returns to centre.

```javascript
wiggle(2.2, 14)   // struggle
wiggle(4, 24)     // bar drop
```
{: file="Impact Wiggle Expression" }

| Use Case | Frequency | Amplitude | Duration |
|----------|-----------|-----------|----------|
| Struggle / sticking point | 2.2 | 14 | 0.2–0.35s |
| Bar drop / floor impact | 4 | 24 | 0.2–0.35s |

Scale footage to 103–105% for the more intense shake.

> **The distinction matters**  
> Ambient wiggle = weight exists.  
> Marker wiggle = weight reacts.  
> Keep that separation and you'll never misuse either.
{: .prompt-tip }

---

## Look & Feel

### Global Adjustment Layer

A single adjustment layer spanning the entire timeline. Its purpose is not grading, but normalisation and cohesion. Clips from different angles and lighting conditions should feel like the same session.

The adjustment layer should disappear into the footage. You notice it most when it's gone. Toggle the layer off, then on. If you think "everything feels more together" or "the image is slightly punchier", that's correct. If you think "there's a vignette" or "the corners are dark", it's too strong.

**Placement**

One adjustment layer, positioned above all footage but below grain, text, and UI elements. Spans the full edit duration. Never trim it per clip.

Why below text? The global layer affects everything beneath it. If it sat above your rep counter, the text would lose contrast, shift colour, and get vignetted. UI stays on top, untouched.

```
Grain Overlay
Text / Rep Counter
───────────────────
Adjustment Layer (global)
───────────────────
Footage Clips
```

**Effect Stack**

Order matters. Apply in this sequence.

**1. Lumetri Color (Basic Correction)**

Used only to stabilise the image, not to stylise it.

| Setting | Value | Notes |
|---------|-------|-------|
| Exposure | 0 (default) | Only touch if clips are wildly inconsistent. Max adjustment: ±0.1 |
| Contrast | +5 to +10 | Adds definition without harshness. Keeps the industrial grey feel. Avoid higher values. Gyms already have hard lighting. |
| Saturation | 100–105 | Slight lift to avoid flatness. Keeps plates and skin from looking dead. Never exceed 110. |

If saturation feels too strong, reduce per clip, not here.

**2. Vignette**

This is where your style shows, but subtly.

| Setting | Value | Notes |
|---------|-------|-------|
| Amount | -0.4 (range: -0.3 to -0.5) | Darkens edges just enough |
| Midpoint | 40 | |
| Roundness | 0 | |
| Feather | 80 (range: 70–85) | |

The vignette focuses attention on the lifter, helps hide lighting falloff, and blends clips together perceptually.

If you notice the vignette, reduce Amount, not Feather.

**What This Layer Should NOT Do**

- Fix blown highlights
- Correct white balance
- Stylise individual clips
- Add mood or drama

Those belong per clip, not globally.

### Film Grain Overlay

Film grain is a texture layer that sits over your footage. It mimics the organic noise you see in analogue film. Digital footage, especially from modern cameras, can look too clean. Grain breaks up that clinical sharpness and makes the image feel more natural.

For gym footage, grain adds grit. It softens the harsh digital edges without blurring anything. It also helps blend clips together. When every clip has the same grain running over it, lighting differences and colour shifts become less noticeable.

**Setup**

1. Use a video grain overlay. Black background with moving grain/dust. [Download the grain overlay I use](https://dinnertimebucket.s3.us-east-1.amazonaws.com/AdobeStock_1024542648.mov){:target="_blank"}
2. Place above everything in the layer stack
3. Scale to fill the comp
4. Blend mode: Soft Light or Overlay
5. Opacity: 5–8%

**Soft Light vs Overlay:**

Both blend the grain into the footage, but Overlay has more contrast and punch. Soft Light is gentler. If your footage already has hard lighting (most gyms do), Soft Light usually works better. Overlay can make it feel too crunchy.

**Why 5–8% opacity:**

Grain should add texture, not noise. At 5–8%, you feel it more than you see it. The footage gains a subtle film quality without looking filtered. Go higher and you start seeing individual dust particles and scratches. That's too much.

**Looping**

Grain overlays are usually short. A 30-second clip won't cover a longer edit. To extend it, right-click the grain footage in the Project panel → Interpret Footage → set Loop to 10 or more. This repeats the clip seamlessly so you can stretch it across your full timeline.

> **Grain should be felt, not seen**  
> If you notice scratches or dust particles, the opacity is too high.
{: .prompt-info }

---

## Finishing

### Struggle, Impact, and Ending

This covers the final moments of each clip. Struggle, bar drop, and the end-of-video finish. Each element has a specific purpose.

**Struggle Moment**

Sell effort and tension without gimmicks.

An adjustment layer, local to the struggle moment.

| Parameter | Value |
|-----------|-------|
| Length | 6–10 frames |
| Effect | Lumetri → Exposure |
| Keyframes | `0 → -0.3 → 0` |
| Easing | Easy Ease all |

The middle keyframe sits at peak struggle. This is a tension dip, not a fade.

A one-off wiggle triggered by a struggle marker. Short duration, returns to centre, stops clean. This makes the frame feel loaded, not handheld.

> **−0.3 is tension, not darkness**  
> The dip should be felt, not seen as a fade.
{: .prompt-info }

**Bar Drop / Impact**

Communicate weight and force.

A second marker triggers a stronger, shorter shake. Higher amplitude, higher frequency. It stops immediately after the impact.

Optional: a tiny exposure hit of −0.2 to −0.3, kept under 6 frames.

**End-of-Video Finish**

End with certainty, not fadey softness.

An adjustment layer starting 12 frames before the end, finishing exactly on the last frame.

| Frame | Exposure |
|-------|----------|
| Start | 0 |
| End | −3 to −4 |

Easy Ease. This takes the image to true black. Grain and detail die naturally with the exposure.

> **−3 = lights off**  
> −0.3 is a dip. −3 is darkness. Don't confuse them.
{: .prompt-warning }

**Black Hold**

After the exposure dip, add a black solid on top of everything. Length: 8–12 frames.

This lets the impact land, prevents rushed endings, and makes loops feel intentional.

### Audio Fade

Audio is left untouched throughout the lift. No fades during reps or impacts. The gym sounds, the plates, the effort. That stays raw.

A single fade is applied only at the end to avoid an abrupt cutoff.

**Setup**

1. Expand the audio layer in the timeline
2. Find the final audible moment
3. Add keyframes to the Audio Levels property over the last 12–20 frames (roughly 0.5–0.8 seconds at 25 fps)
4. Fade from 0 dB down to −18 to −24 dB
5. Use a smooth fade curve (Constant Power or eased keyframes)

The final frames should fall into silence naturally. If the fade is noticeable, it's too strong.

**Timing with the Ending**

The audio fade should match the visual ending. Picture darkens, sound weakens, then silence.

| Element | Timing |
|---------|--------|
| Exposure dip starts | 12 frames before end |
| Audio fade starts | Same time or 2–4 frames after |
| Black hold | 8–12 frames of silence |

If there's a bar drop, fade after the impact sound. Not before.

### Pre-Export Checklist

**Quick Pass (Every Export)**

The essentials. Run through these every time.

- [ ] Scrub through all cuts
- [ ] Toggle grain on/off (sanity check)
- [ ] Verify rep counters trigger correctly on markers
- [ ] Check for visible edges from wiggle or scale
- [ ] Toggle Global Adjustment Layer on/off. Clips should feel unified, not graded.
- [ ] End-of-video exposure dip reaches −3 to −4
- [ ] Black hold present (8–12 frames)
- [ ] Audio fades naturally. No abrupt cut. No early fade before impact.
- [ ] Watch the final 10 seconds. Does the ending feel decisive?

**Full Pass (Important Uploads)**

Everything. For when you have time or it matters.

*Visual Integrity*

- [ ] Preview at Full or Half resolution, never Quarter
- [ ] Confirm vignette is not obvious. Edges shouldn't draw attention.
- [ ] Check highlight detail. No crushed whites in plates or lights.
- [ ] Ensure struggle exposure dips return to normal

*Motion & Timing*

- [ ] Confirm wiggle stops cleanly and returns to centre
- [ ] Ensure no wiggle overlap into calm moments
- [ ] Check scale animations. Start/end values make sense. No jumps between same-location clips.
- [ ] Verify no unintended easing on cuts meant to be hard

*Text & UI*

- [ ] Text is fully readable on bright and dark frames
- [ ] Rep counter visible against different backgrounds (check against walls, plates, lights)
- [ ] Drop shadow is subtle, not haloing
- [ ] Text is not affected by global adjustment or vignette
- [ ] Weight text appears and disappears intentionally

*Ending & Audio*

- [ ] Struggle dip and ending dip are not stacked
- [ ] Silence at the very end. No residual noise.

*Technical*

- [ ] Frame rate matches comp (25 fps)
- [ ] No disabled layers accidentally left on
- [ ] No guide layers visible
- [ ] No test solids or hidden adjustment layers

**Final Gut Check**

Watch the final 10 seconds only. Don't look for mistakes. Just feel it.

Ask yourself:

- Does the ending feel decisive?
- Does the lift land?
- Does anything pull attention away?

If nothing distracts you, it's ready.

> **If nothing calls attention to itself, the video is finished.**
{: .prompt-info }

### Export

Two exports from the same After Effects comp. One for uploading yourself, one for sending to others.

To export, go to Composition → Add to Adobe Media Encoder Queue. This opens Media Encoder with your comp ready to configure.

**TikTok / YouTube Shorts (Maximum Quality)**

This export prioritises image integrity and compression resilience. The platforms will downscale and recompress. This version gives them the best possible source.

Format: H.264

Preset: Start from High Quality, then customise below.

| Setting | Value |
|---------|-------|
| Frame Size | 2160 × 3840 (4K vertical, 9:16) |
| Frame Rate | Match comp (25 fps) |
| Field Order | Progressive |
| Aspect | Square Pixels |
| Profile | High |
| Level | Auto |

| Setting | Value |
|---------|-------|
| Bitrate Encoding | VBR, 2-pass |
| Target Bitrate | 35–50 Mbps |
| Maximum Bitrate | 60–80 Mbps |

VBR 2-pass means the encoder analyses your footage on the first pass, then encodes based on that analysis on the second. Better quality than single pass, but takes twice as long.

Higher bitrate helps preserve grain, dark gym lighting, and fine detail before the platform compresses it again.

| Setting | Value |
|---------|-------|
| Render at Maximum Depth | On |
| Use Maximum Render Quality | On |

These improve bit depth for gradients and use a better scaling algorithm. Helps with grain stability and banding in dark footage.

No sharpening. No LUTs. No social presets. Export sharpening creates artefacts with grain. Keep the file clean.

Before posting to TikTok, tap "More options" and enable "Allow high-quality uploads" or "Upload HD". This stops the app applying extra compression before upload.

> **Export once, compress once.**  
> Let the platform do the downscaling.
{: .prompt-tip }

**Send-to-Friend Export (Smaller File)**

For sending via WhatsApp, Google Drive, or AirDrop. Faster transfers with minimal quality loss. This is not the master upload file.

Format: H.264

Preset: Start from High Quality, then customise below.

| Setting | Value |
|---------|-------|
| Frame Size | 1080 × 1920 (vertical HD) |
| Frame Rate | Match comp (25 fps) |
| Field Order | Progressive |
| Aspect | Square Pixels |
| Profile | High |
| Level | Auto |

| Setting | Value |
|---------|-------|
| Bitrate Encoding | VBR, 2-pass |
| Target Bitrate | 12–16 Mbps |
| Maximum Bitrate | 20–25 Mbps |

| Setting | Value |
|---------|-------|
| Render at Maximum Depth | On |
| Use Maximum Render Quality | On |

Even for smaller files, these help avoid banding.

**Which to Use**

| Situation | Export |
|-----------|--------|
| Uploading yourself | 4K vertical |
| Sending to someone else | 1080p vertical |

Never send the 1080p version as your main upload unless you have to.

> **4K for platforms. 1080p for people.**
{: .prompt-info }

---

## Reference

### Key Principles

| Principle | Why |
|-----------|-----|
| Explicit markers over guesswork | Deterministic rep counting |
| Reset motion per clip | Each clip is self-contained |
| Declare scene changes | Hard cuts feel intentional |
| Subtle effects over flashy ones | Cinematic, not amateur |
| Build once, reuse forever | Repeatable workflow |
| Shoot native vertical | Full resolution, no cropping loss |
| 25 fps for UK lighting | Syncs with 50Hz mains, avoids flicker |
| UI above grading | Text stays readable, unaffected by look |
| Ambient wiggle vs marker wiggle | Weight exists vs weight reacts |
| Global adjustment for cohesion, not style | Unify clips, not grade them |
| Grain felt, not seen | Texture without noise |
| Struggle dip vs ending dip | −0.3 is tension, −3 is darkness |
| Export once, compress once | Let the platform do the work |
| If you can see the effect, it's too strong | Adjustments should disappear into footage |

### Summary

| Component | Specification |
|-----------|---------------|
| Composition | 2160 × 3840, 25 fps, square pixels |
| Footage | Direct in comp, precomp if complex |
| Markers | On footage layer in main comp |
| Rep Counter | Expression-driven, index-based, Chakra Petch font, #6CFF8D |
| Scale Animation | 100% → 105–110% per clip |
| Position Drift | 20–40 pixels over clip duration |
| Ambient Wiggle | 0.35 frequency, 8 amplitude |
| Marker Wiggle | 2.2/14 for struggle, 4/24 for impact |
| Global Look | Lumetri + vignette adjustment layer, below UI |
| Grain | 5–8% opacity, Soft Light blend |
| Struggle Dip | −0.3 exposure, 6–10 frames |
| Ending Dip | −3 to −4 exposure, 12 frames + black hold |
| Audio Fade | End only, 12–20 frames, after any impact |
| Export (4K) | H.264, VBR 2-pass, 35–50 Mbps target |
| Export (1080p) | H.264, VBR 2-pass, 12–16 Mbps target |

A repeatable structure for cinematic vertical gym content.

---

*Documented January 2026.*
