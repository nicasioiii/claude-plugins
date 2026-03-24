---
name: AI-Powered Ad Creation
description: |
  MANDATORY TRIGGERS: User asks to create AI-generated ads, use Google Flow/Veo, create AI clones, use HeyGen for ads, create AI video ads, use AI tools for ad production, generate AI UGC, clone their voice for ads, or use the 60-Second Ad Machine GPT.
  FOR: End-to-end AI ad creation using Google Flow/Veo, Google Whisk, HeyGen, ElevenLabs, CapCut, and SubMagic. Covers AI clone creation, scene consistency, product/location insertion, voice cloning, script writing with AI (60-Second Ad Machine GPT), UGC-style AI ads, and the complete AI tool stack.
  Do NOT use for: Traditional (non-AI) video scripting (use create-video-ads), ad copy writing (use create-ad-copy), Google asset creation (use create-google-assets).
---

# AI-Powered Ad Creation

Create AI-generated video ads using the modern AI tool stack. This skill covers the complete workflow from script to finished ad using Google Flow/Veo, Google Whisk, HeyGen, ElevenLabs, and CapCut.

## THE 4-STEP AI AD CREATION PROCESS

1. **Script** -- Write ad script using ChatGPT (60-Second Ad Machine GPT) or templates
2. **Images** -- Create scene images using Google Whisk (for character consistency)
3. **Video** -- Generate video clips using Google Flow/Veo 3 (animate images with dialogue)
4. **Edit** -- Assemble clips in CapCut; add music, sound effects, captions

### Time Benchmarks
- Script writing: ~60 seconds with the 60-Second Ad Machine GPT
- Full ad from scratch: 20-30 minutes for a basic ad
- Full ad with editing: Under 60 minutes

---

## CORE TOOL STACK

### Required Tools
| Tool | Cost | Purpose |
|------|------|---------|
| Google Ultra Account | ~$125/month | Unlimited Veo 3 Fast generations |
| ChatGPT | Free or $20/month | Script writing (60-Second Ad Machine GPT) |
| Google Flow | Included with Ultra | AI video generation (labs.google/flow) |
| Google Whisk | Free | AI image generation (labs.google/fx/tools/whisk) |
| CapCut | Free (Pro optional) | Video editing, music, SFX, captions |

### Optional/Advanced Tools
| Tool | Cost | Purpose |
|------|------|---------|
| HeyGen | $29/month | Long-form avatar (up to 30 min) with voice clone |
| SubMagic | Paid | Auto-captions + B-roll insertion |
| ElevenLabs | Free tier available | Voice cloning (5-10 min audio sample) |
| Descript | Paid | Edit video like a document |
| Opus Clip | Paid | Long-form to short-form clips with virality scoring |

**Setup note:** Google Gemini is only used to sign up for Ultra. All actual work happens in Google Flow. Without Ultra, you get approximately 5 generations per day (insufficient for ad production).

---

## GOOGLE FLOW / VEO -- VIDEO GENERATION

### Key Settings
- **Model:** Veo 3 Fast (unlimited with Ultra account)
- **Outputs per prompt:** Always set to 4 (generates 4 variations)
- **Aspect ratio:** Portrait for social ads (Reels, TikTok), Landscape for YouTube
- **Max clip length:** 8 seconds per generation

### Three Main Modes

**1. Text to Video:** Create from scratch with no reference images.
- Used when: No reference photos, creating avatars from imagination
- Prompt: Describe person + action + dialogue

**2. Frames to Video:** Animate an existing photo.
- Used when: Cloning yourself or using a specific character
- Upload photo, provide dialogue/action instructions

**3. Ingredients to Video:** Combine multiple reference elements.
- Used for: Inserting specific products, clothing, locations
- Upload person + product + location as separate "ingredients"

### Speed Hack for Dialogue
If AI speaks too slowly, add random filler text at the end of the prompt. The AI must fit ALL text into 8 seconds, so extra text forces faster delivery. Trim the random words in the editor.

### Download Settings
- 720p: Downloads immediately, fine for social media ads
- 1080p: Takes ~60 seconds to process

---

## GOOGLE WHISK -- SCENE/IMAGE GENERATION

### Basic Workflow
1. Describe character + scene in Whisk
2. Generate the image
3. Download images you like
4. Upload into Google Flow for animation

### Scene Consistency via "Refine" Button
This is the critical technique for maintaining the same character across scenes:
1. Generate initial image in Whisk
2. Download it
3. Click "Refine" (NOT a new prompt)
4. Describe the change: "Zoom out full body shot" or "Change apron to pink"
5. Download refined image -- same character maintained
6. Repeat for each scene change

**What breaks consistency:** Starting a completely new prompt from scratch creates a totally different person. Always use Refine on the existing image thread.

---

## SCRIPT ORGANIZATION DURING PRODUCTION

- Break scripts into 8-second segments (Google Flow max clip length)
- Highlight completed lines in yellow
- Highlight current working line in green
- Use different photos/scenes for each segment to create visual variety
- After basic script, ask ChatGPT to break into scene-by-scene table with Whisk prompts

---

## AI AD STRUCTURE (STANDARD)

1. **Hook** (0-3 sec): AI clone introduces itself or opens with pattern interrupt
2. **Pain Point** (3-10 sec): Call out audience frustration
3. **Solution** (10-18 sec): Present the product/service
4. **Benefits** (18-22 sec): List key outcomes
5. **CTA** (22-25 sec): Clear call to action

**Multiple scene changes in 25 seconds = better performance.** Ads that move from scene to scene quickly outperform static single-scene ads.

---

## When to Read Reference Files

Load `ref-ai-video-workflow.md` when:
- User is going through the step-by-step production process
- Needs Google Flow/Veo mode details or Whisk workflow
- Troubleshooting AI generation issues

Load `ref-ai-clone-creation.md` when:
- User wants to create an AI clone of themselves or a client
- Needs HeyGen vs Google Flow clone comparison
- Setting up voice cloning with ElevenLabs

Load `ref-ai-script-templates.md` when:
- User needs the 60-Second Ad Machine GPT workflow
- Needs script templates (clone opening, short-form, seasonal, UGC-style)
- Writing scene-by-scene scripts for AI production

Load `ref-ai-tool-stack.md` when:
- User is setting up their AI ad production workflow from scratch
- Needs tool comparison or pricing info
- Needs CapCut editing workflow details

---

## CROSS-REFERENCES

| When This Happens | Go To |
|-------------------|-------|
| AI ad needs traditional scripting foundations | `create-video-ads` skill (ref-video-scripting) |
| User needs creative research before scripting | `research-creative` skill |
| User wants non-AI video production | `create-video-ads` skill |
| User wants text copy, not video | `create-ad-copy` skill |
| User wants to test AI ads they created | `test-creative` skill |
