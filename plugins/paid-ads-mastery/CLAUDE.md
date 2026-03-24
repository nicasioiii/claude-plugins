# Paid Ads Mastery v2.0 -- Routing & Operations

## Plugin Overview

Complete paid advertising knowledge engine for Meta, Google, and TikTok Ads. Built from 9 extraction files covering 610+ expert-level training transcriptions across 9 courses. Provides end-to-end guidance from account setup through advanced scaling, covering tracking infrastructure, creative research, campaign strategy, ad production, testing methodology, optimization, and scaling playbooks.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
Is the user asking about SETUP/TRACKING?
  YES -> Is it Meta? -> setup-meta-tracking
       -> Is it Google? -> setup-google-ads
  NO -> Continue

Is the user asking about RESEARCH before creating ads?
  YES -> research-creative
  NO -> Continue

Is the user asking about CAMPAIGN STRUCTURE or BIDDING?
  YES -> Which platform?
       -> Meta/Facebook/Instagram -> strategy-meta-ads
       -> Google (Search/Shopping/PMax/YouTube) -> strategy-google-ads
       -> TikTok -> strategy-tiktok-ads
       -> Multiple platforms / "which platform" -> strategy-cross-channel
  NO -> Continue

Is the user asking about CREATING ads?
  YES -> What type?
       -> Ad copy, headlines, static images -> create-ad-copy
       -> Video scripts, UGC, VSL -> create-video-ads
       -> AI-generated ads (Google Flow, HeyGen, etc.) -> create-ai-ads
       -> Google RSA, PMax assets, YouTube scripts -> create-google-assets
       -> Carousel ads or thumbnails -> create-carousel-ads
  NO -> Continue

Is the user asking about TESTING creative?
  YES -> test-creative
  NO -> Continue

Is the user asking about OPTIMIZING or DIAGNOSING campaigns?
  YES -> Which platform?
       -> Meta -> optimize-meta
       -> Google -> optimize-google
  NO -> Continue

Is the user asking about SCALING?
  YES -> scale-campaigns
  NO -> Continue

Is the user asking about BRAND STRATEGY or MULTI-PLATFORM decisions?
  YES -> strategy-cross-channel
  NO -> Ask clarifying questions
```

---

## Skill Routing Table (All 16 Skills)

### Layer 1: SETUP
| Skill | Display Name | Use When |
|---|---|---|
| `setup-meta-tracking` | Meta Pixel, CAPI & Account Setup | Meta pixel installation, CAPI, server-side tracking, account health, payment hygiene |
| `setup-google-ads` | Google Ads, Merchant Center & Conversion Tracking | Google conversion code, Merchant Center approval, product feed, product research |

### Layer 2: RESEARCH
| Skill | Display Name | Use When |
|---|---|---|
| `research-creative` | Creative Research & Audience Intelligence | 4-step research process, code banks, personas, awareness levels, ICE scoring, competition research |

### Layer 3: STRATEGY
| Skill | Display Name | Use When |
|---|---|---|
| `strategy-meta-ads` | Meta/Facebook Ads Campaign Strategy | CBO/ABO/ASC, Crazy Method, hot pockets, budget rules, targeting progression, retargeting |
| `strategy-google-ads` | Google Ads Campaign Strategy | Search/Shopping/PMax/YouTube structure, bidding progression, Quality Score, full-funnel |
| `strategy-tiktok-ads` | TikTok Ads Strategy & Creative | TikTok-specific strategy, creative principles, benchmarks, iteration loop |
| `strategy-cross-channel` | Cross-Channel & Funnel Strategy | Multi-platform allocation, push vs pull, brand strategy, funnel mapping |

### Layer 4: CREATE
| Skill | Display Name | Use When |
|---|---|---|
| `create-ad-copy` | Ad Copy, Headlines & Static Creative | Meta copy, headlines, static design, copy templates, psychology |
| `create-video-ads` | Video Ad Scripting & Production | Video frameworks, hooks, retention, scripting, UGC, storytelling |
| `create-ai-ads` | AI-Powered Ad Creation | Google Flow/Veo, HeyGen, ElevenLabs, CapCut, AI clones |
| `create-google-assets` | Google Ads Creative & Asset Production | RSA headlines, Shopping titles, PMax assets, YouTube 7 elements |
| `create-carousel-ads` | Carousel & Thumbnail Design | Carousel types, slide structure, thumbnail AHQ framework |

### Layer 5: TEST
| Skill | Display Name | Use When |
|---|---|---|
| `test-creative` | Creative Testing Methodology | 6 testing approaches, kill criteria, statistical significance, volume guidelines |

### Layer 6: OPTIMIZE
| Skill | Display Name | Use When |
|---|---|---|
| `optimize-meta` | Meta Campaign Optimization & Diagnostics | CBO loop, diagnostics, creative fatigue, attribution, daily management |
| `optimize-google` | Google Campaign Optimization & Diagnostics | Shopping/Search/PMax optimization, Quality Score, POAS, bottleneck analysis |

### Layer 7: SCALE
| Skill | Display Name | Use When |
|---|---|---|
| `scale-campaigns` | Scaling Playbook (Cross-Platform) | Bell Theory, Daily Loop, budget scaling, multi-country, offer prerequisites |

---

## Cross-Reference Map with Trigger Conditions

| Source Skill | References | Trigger Condition |
|---|---|---|
| `strategy-meta-ads` | `setup-meta-tracking` | Pixel maturity unknown or account is new |
| `strategy-meta-ads` | `scale-campaigns` | User asks about scaling budgets or breaking daily loops |
| `strategy-google-ads` | `setup-google-ads` | Merchant Center or conversion tracking issues |
| `strategy-google-ads` | `scale-campaigns` | User asks about scaling Shopping or PMax |
| `create-ad-copy` | `research-creative` | Always -- research should precede copy writing |
| `create-video-ads` | `research-creative` | Always -- code banks and personas feed scripting |
| `create-ai-ads` | `create-video-ads` | AI ad needs traditional scripting foundations |
| `create-google-assets` | `strategy-google-ads` | Asset creation needs campaign context |
| `test-creative` | `create-ad-copy` / `create-video-ads` | Test plan requires actual creative production |
| `test-creative` | `optimize-meta` / `optimize-google` | Test results need interpretation |
| `optimize-meta` | `strategy-meta-ads` | Optimization reveals structural problems |
| `optimize-meta` | `test-creative` | Creative fatigue detected |
| `optimize-google` | `strategy-google-ads` | Quality Score or structure issues found |
| `scale-campaigns` | `optimize-meta` / `optimize-google` | Scaling diagnostics needed |
| `scale-campaigns` | `test-creative` | Scaling requires new creative angles |
| `strategy-tiktok-ads` | `create-video-ads` | TikTok creative needs video scripting fundamentals |
| `strategy-cross-channel` | All strategy skills | Multi-platform allocation advice needed |
| `create-carousel-ads` | `create-ad-copy` | Carousel needs copy/messaging foundations |

---

## Slash Command Table

| Command | Description | Skills Activated |
|---|---|---|
| `/build-campaign` | Design complete campaign from scratch | strategy-meta-ads OR strategy-google-ads, research-creative, strategy-cross-channel |
| `/write-ad` | Generate ad copy, video scripts, or assets | create-ad-copy, create-video-ads, create-ai-ads, OR create-google-assets |
| `/research-brief` | Run 4-step research methodology | research-creative |
| `/audit-campaign` | Diagnose existing campaign with frameworks | optimize-meta OR optimize-google, scale-campaigns |
| `/test-plan` | Design creative or campaign testing plan | test-creative, research-creative |
| `/scale-plan` | Create scaling roadmap from current performance | scale-campaigns, strategy-meta-ads OR strategy-google-ads |
| `/brief-media-buyer` | Generate comprehensive SOP for team handoff | strategy-meta-ads OR strategy-google-ads, optimize-meta OR optimize-google, test-creative, scale-campaigns (selected based on platform) |
| `/creative-iterate` | Produce iteration variations of winning ads | test-creative, create-ad-copy OR create-video-ads |

---

## Implementation Notes

- **Decision Tree First:** Use routing tables above to determine which skill(s) to invoke.
- **Cross-Reference When Needed:** Acknowledge when multiple skills contribute.
- **SKILL.md First, Then References:** Start with SKILL.md for high-level guidance, then reference files for deep specifics.
- **Ask Clarifying Questions:** If user stage is unclear (setup vs. optimize vs. scale), ask before routing.
- **Product Marketing Context:** If `product-marketing-context.md` exists, load and reference brand voice, audience definitions, positioning, and KPIs.
