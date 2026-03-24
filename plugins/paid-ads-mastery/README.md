# Paid Ads Mastery v2.0.0

A complete paid advertising knowledge engine for Meta, Google, and TikTok Ads, built from 13 courses covering 610+ expert-level training transcriptions. Organized into 16 skills with 53 reference files and 8 slash commands. Provides end-to-end guidance from account setup through advanced scaling, covering tracking infrastructure, creative research, campaign strategy, ad production (traditional and AI), testing methodology, optimization diagnostics, and scaling playbooks.

This plugin transforms Claude into an expert paid ads advisor across three major platforms. It follows a layered workflow: set up tracking, research audiences and competitors, build campaign strategy, create ad creative (copy, video, AI-generated, Google assets, carousels), test systematically, optimize with diagnostic frameworks, and scale with proven methodologies.

## Source Material

- Ezra Firestone / Brett Curry -- Smart Google Ads
- Shri Kanase -- Google Ads Mastery
- PPC Mastery Hub -- Google Ads Success Path
- Konstantinos Doulgeridis -- Facebook Ads Master Course
- Deividas Tokaris / Carlo -- Creative Media Buyer + Make Ads
- Salif Sibane -- 9-Figure Ecom Creatives & Funnels
- Kristine Mirelle -- AI Ad Creation Mastery
- Seth Godin / Mitchell Wheeler -- Ad Creative Academy
- Story Hero Academy -- Story-Driven Ad Frameworks
- Master of Carousels -- Carousel Ad Design
- Thumbnail Masterclass -- Thumbnail & Visual Hook Design
- TikTok Ads Strategy (integrated across multiple sources)
- Cross-Channel Strategy & Brand Building (integrated across multiple sources)
- Total: 13 courses, 53 reference files, ~1.75M lines of source material

## Skills (16)

| Skill | Description | Ref Files |
|-------|-------------|-----------|
| `setup-meta-tracking` | Meta Pixel, CAPI & Account Setup -- pixel installation, server-side tracking, account health, payment hygiene | 2 |
| `setup-google-ads` | Google Ads, Merchant Center & Conversion Tracking -- conversion code, Merchant Center approval, product feed, product research | 3 |
| `research-creative` | Creative Research & Audience Intelligence -- 4-step research process, code banks, personas, awareness levels, ICE scoring | 4 |
| `strategy-meta-ads` | Meta/Facebook Ads Campaign Strategy -- CBO/ABO/ASC, Crazy Method, Blender Method, hot pockets, budget rules, retargeting | 5 |
| `strategy-google-ads` | Google Ads Campaign Strategy -- Search/Shopping/PMax/YouTube structure, bidding progression, Quality Score, full-funnel | 5 |
| `strategy-tiktok-ads` | TikTok Ads Strategy & Creative -- TikTok-specific strategy, creative principles, benchmarks, 3-week iteration loop | 2 |
| `strategy-cross-channel` | Cross-Channel & Funnel Strategy -- multi-platform allocation, push vs pull, brand strategy, funnel mapping | 2 |
| `create-ad-copy` | Ad Copy, Headlines & Static Creative -- Meta copy templates, headlines, static design, persuasion psychology | 3 |
| `create-video-ads` | Video Ad Scripting & Production -- video frameworks (VSL, UGC, mashups), hooks, retention, scripting | 5 |
| `create-ai-ads` | AI-Powered Ad Creation -- Google Flow/Veo, HeyGen, ElevenLabs, CapCut, AI clones, 60-Second Ad Machine | 4 |
| `create-google-assets` | Google Ads Creative & Asset Production -- RSA headlines, Shopping titles, PMax assets, YouTube 7 elements | 4 |
| `create-carousel-ads` | Carousel & Thumbnail Design -- 3 carousel types + hybrid, slide structure, thumbnail AHQ framework | 2 |
| `test-creative` | Creative Testing Methodology -- 6 testing approaches, kill criteria, volume guidelines, iteration framework | 2 |
| `optimize-meta` | Meta Campaign Optimization & Diagnostics -- CBO loop, diagnostics, creative fatigue, attribution, daily management | 3 |
| `optimize-google` | Google Campaign Optimization & Diagnostics -- Shopping/Search/PMax optimization, Quality Score, POAS, bottleneck analysis | 4 |
| `scale-campaigns` | Scaling Playbook (Cross-Platform) -- Bell Theory, Daily Loop Theory, offer prerequisites, multi-country expansion | 3 |

## Commands (8)

| Command | Description |
|---------|-------------|
| `/build-campaign` | Design a complete campaign from scratch with architecture, targeting plan, budget allocation, and creative brief |
| `/write-ad` | Generate ad copy, video scripts, AI ad scripts, or Google assets based on platform and format |
| `/research-brief` | Run the 4-step creative research methodology producing code bank, personas, and hypotheses |
| `/audit-campaign` | Diagnose an existing campaign using diagnostic frameworks with bottleneck identification |
| `/test-plan` | Design a creative or campaign testing plan with hypotheses, kill criteria, and timeline |
| `/scale-plan` | Create a scaling roadmap with budget progression, creative needs, and risk mitigation |
| `/brief-media-buyer` | Generate comprehensive SOP document for media buyer or team handoff |
| `/creative-iterate` | Produce iteration variations of winning ads using 5-stage iteration framework |

## Workflow

Skills are organized into 7 layers that follow the natural campaign lifecycle:

1. **Setup** (Skills 1-2): setup-meta-tracking, setup-google-ads
2. **Research** (Skill 3): research-creative
3. **Strategy** (Skills 4-7): strategy-meta-ads, strategy-google-ads, strategy-tiktok-ads, strategy-cross-channel
4. **Create** (Skills 8-12): create-ad-copy, create-video-ads, create-ai-ads, create-google-assets, create-carousel-ads
5. **Test** (Skill 13): test-creative
6. **Optimize** (Skills 14-15): optimize-meta, optimize-google
7. **Scale** (Skill 16): scale-campaigns

## What's New in v2.0.0

- **7 new skills** added: `strategy-tiktok-ads`, `strategy-cross-channel`, `create-ai-ads`, `create-google-assets`, `create-carousel-ads`, `test-creative`, `scale-campaigns`
- **Reference files expanded** from initial build to 53 across all 16 skills
- **TikTok coverage** added as a full platform alongside Meta and Google
- **AI ads workflow** added covering Google Flow/Veo, HeyGen, ElevenLabs, CapCut
- **Carousel frameworks** added with 3 types + hybrid and thumbnail AHQ framework
- **Dedicated testing skill** separated from optimization for clearer methodology
- **Dedicated scaling skill** with Bell Theory, Daily Loop Theory, and multi-country playbooks
- **Cross-channel strategy** added for multi-platform allocation and brand vs DR decisions
- **Complete rebuild** from v1.0.0 (9 skills covering only Meta and Google)

## Audit Status

- Structural audit (checks 1-23): PASS
- Content completeness audit (checks 24-30): PASS
- Total audit cycles: 4 (3 structural + 1 content completeness)
