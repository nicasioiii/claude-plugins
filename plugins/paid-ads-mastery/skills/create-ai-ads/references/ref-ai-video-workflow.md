---
title: AI Video Creation Workflow (Google Flow + Whisk)
category: reference
skill: create-ai-ads
---

# AI Video Creation Workflow

## STEP-BY-STEP PRODUCTION PROCESS

### Step 1: Write Script
- Use 60-Second Ad Machine GPT or templates (see ref-ai-script-templates)
- Break script into 8-second segments (Google Flow max clip length)
- Mark each segment with scene description and dialogue

### Step 2: Generate Scene Images in Whisk
1. Go to Google Whisk (labs.google/fx/tools/whisk)
2. For each scene segment, describe the character + setting + action
3. Generate image, download if good
4. For NEXT scene: click "Refine" (NOT new prompt) to maintain character consistency
5. Describe the scene change: new background, new action, new camera angle
6. Download refined image
7. Repeat for all scenes

### Step 3: Generate Video Clips in Google Flow
1. Go to Google Flow (labs.google/flow/about)
2. Select "Frames to Video" mode
3. Upload scene image from Whisk
4. Write dialogue prompt for that scene segment
5. Set: Veo 3 Fast, 4 outputs, Portrait (for social) or Landscape (for YouTube)
6. Generate and review all 4 options
7. Click "Add to Scene" on best option
8. Repeat for each scene segment

### Step 4: Assemble in CapCut
1. Download all chosen clips from Google Flow (720p is fine for social)
2. Import into CapCut
3. Arrange clips in script order
4. Trim dead space at beginning and end of each clip
5. Add background music from CapCut library
6. Add sound effects at key moments
7. Add captions/subtitles
8. Export

---

## GOOGLE FLOW / VEO DETAILED REFERENCE

### Text to Video Mode
- Creates content from scratch with random characters
- Prompt format: "A [description of person] in [setting] saying [SCRIPT LINE]"
- Example: "A young lady with pink hair in an office space saying 'Are you tired of recording videos all day?'"
- Used when: No reference photos needed, creating imaginary characters

### Frames to Video Mode
- Animates an existing uploaded photo
- Upload photo > write dialogue/action prompt
- Used when: Cloning yourself/client or using a specific Whisk-generated character
- Best for: Consistent character across multiple scenes

### Ingredients to Video Mode
- Combine multiple reference images per generation
- Upload: person image + product image + clothing image + location image
- Each image = one "ingredient"
- Prompt combines all elements: "Put the girl in the blue dress holding the drink"
- Used for: E-commerce product placement, real estate, fashion, food/beverage

### Prompting Tips for Ingredients
- Be explicit about which ingredient goes where
- If it misses an element, reword and regenerate
- Sometimes it infers from images automatically, sometimes needs direction
- Regenerate freely -- unlimited with Ultra account

### Reuse Prompt Feature
- Click three dots on any generation > "Reuse"
- Re-populates the exact prompt
- Useful for: fixing misspellings, adjusting wording, regenerating failed attempts

### Google Flow Built-in Editor
- Click "Add to Scene" on chosen clips
- "Switch to Scene Builder" opens the editor
- Click "Arrange" to reorder or trim clips
- Limitations: Cannot add music or SFX -- use CapCut for that
- Trim dead space at beginning and end of each clip

---

## GOOGLE WHISK DETAILED REFERENCE

### Creating Avatars from Scratch
- Describe any character: age, ethnicity, hair color, setting, clothing, expression
- Example: "An elderly woman smiling in a retirement home in a wheelchair looking directly at the camera"
- Example: "A cartoon garbage can that has friendly eyes and a mustache"
- Key: Subject should be "very visible and looking into camera"

### Creating Scenes with Real People
- Upload a photo of yourself/client into Whisk
- Instructions: "Please make the subject sitting in a boat in Venice, smiling, looking straight into camera"
- Download resulting scene image for use in Google Flow

### Photo Requirements
- Gather 5-10 photos that could work
- Great lighting required
- Subject very visible, looking into camera
- Professional photos sometimes get flagged as "prominent figures" -- use casual photos as backup
- Can source photos from Facebook profiles for client work

### Scene Consistency -- The Refine Workflow
1. Generate initial character in Whisk
2. Download the image
3. Click "Refine" on SAME image (NOT new prompt)
4. Describe change: "Now in a kitchen" or "Zoom out full body shot"
5. Download refined version -- same character, new scene
6. Repeat for all needed scenes

### What Refine Preserves:
- Character appearance (face, body type)
- Art style / visual consistency
- General composition feel

### What Breaks Consistency:
- Starting a completely new prompt from scratch
- Switching to a different image as the base
- Solution: Always chain Refine from the original image

---

## PRODUCT/LOCATION INSERTION (INGREDIENTS MODE)

### Use Cases
| Industry | Ingredients |
|----------|------------|
| E-commerce | Avatar + specific product image |
| Real estate | Avatar + property interior/exterior |
| Food/beverage | Avatar + branded item |
| Fashion | Avatar + specific clothing item |
| Travel | Avatar + landmark location |

### Process
1. Select "Ingredients to Video" in Google Flow
2. Upload reference images (person + product + location)
3. Write prompt combining all elements
4. Generate 4 outputs, select best
5. If element is missed, reword prompt and regenerate

---

## COMMON AI VIDEO ISSUES AND FIXES

| Issue | Fix |
|-------|-----|
| Speaking too slowly | Add filler text at end of prompt to force faster delivery |
| Wrong accent/language | Regenerate -- AI sometimes adds random accents |
| Lip sync off | Regenerate -- sometimes doesn't align |
| "Prominent figures" block | Use less professional/more casual photos |
| Content policy triggers | Reword prompt -- sometimes triggers for innocent content |
| Dead space | Trim all pauses in CapCut |
| Inconsistent characters | Use Whisk Refine, not fresh prompts |

---

## EDITING QUALITY STANDARDS

- Trim ALL dead space where nobody is talking
- Move quickly from scene to scene
- Keep total ad under 60 seconds for maximum platform compatibility
- Add music and sound effects (CapCut library)
- Add captions for accessibility and engagement
- Target lengths: ~25 sec (punchy), ~30 sec (social reels), ~55 sec (comprehensive)

### Audio Replacement Trick
If AI mispronounces a single word:
1. Record yourself saying just the correct word(s) on phone
2. Import audio into CapCut timeline
3. Cut original audio at error point
4. Lower original volume in that section
5. Layer your recorded correction over it
