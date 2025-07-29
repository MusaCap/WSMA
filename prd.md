# 📄 Product Requirements Document (PRD)

## Product Name:
**Web3 Social Media Agent (WSMA)**

## Overview:
The Web3 Social Media Agent is an AI-powered content automation tool designed for emerging founder communities. It generates daily video scripts using ChatGPT, automates video editing via CapCut and other tools, and posts short-form content (reels) across TikTok, Instagram, Facebook, YouTube Shorts, SpillApp, and FanBase. It also gathers and analyzes post performance data to optimize future content strategy.

---

## 1. Goals & Objectives

### Primary Goals:
- Automate daily content ideation and scriptwriting using ChatGPT.
- Streamline reel production with integrations like CapCut.
- Cross-post seamlessly to all major short-form platforms.
- Monitor and optimize content performance using analytics.

### Secondary Goals:
- Enable community voice curation through user prompts or trending hashtags.
- Provide a dashboard for editorial oversight and content calendar management.
- Enable scalable content distribution for Web3 thought leaders and projects.

---

## 2. User Personas

### a. **Emerging Web3 Founder**
- Wants to build thought leadership on-chain and off-chain.
- Has limited time and editing skills.
- Needs consistent, high-quality content for visibility.

### b. **Community Manager**
- Supports multiple founders and projects.
- Manages scheduling and approvals.
- Analyzes engagement and trends.

---

## 3. Features & Requirements

### A. Script Generation (ChatGPT-Powered)
- Input options: free-form ideas, hashtags, links, or auto-trending scrape.
- Output format: short video scripts (30–60s) in conversational tone.
- Tone customization: choose voice (educational, humorous, edgy, founder-focused).
- Web3 contextual grounding via curated or user-fed news APIs (e.g., CoinTelegraph, Decrypt).

### B. Video Creation
- **CapCut Integration**:
  - Auto-load script into CapCut template.
  - Auto-suggest B-roll, effects, and background music.
  - Brand overlays (logo, colors).
- Support alternative tools: Descript, Pika, RunwayML (optional roadmap).
- Final output: MP4 vertical reels (TikTok spec).

### C. Cross-Platform Posting
- **Platforms**: TikTok, Instagram Reels, Facebook Reels, YouTube Shorts, SpillApp, FanBase.
- Auto-publish or schedule.
- CTA personalization per platform.
- Custom thumbnail uploads or auto-generation.

### D. Analytics & Optimization
- Collect data on:
  - Views, likes, shares, saves, comments, watch time.
  - Posting time vs. engagement.
  - Hashtag performance.
- Visual dashboard: trends, best time to post, best performing topics.
- Weekly optimization report with generative suggestions for next posts.

### E. Admin Dashboard
- Content calendar with post history and future scheduled content.
- Script approval workflow (AI draft → edit → approve).
- Team permissions (founders, editors, analysts).
- Export analytics CSV/PDF for reporting.

---

## 4. Technical Requirements

### Integrations:
- ChatGPT (OpenAI API)
- CapCut (via mobile app automation or CapCut Web if API exposed)
- Social platforms (TikTok, Meta Business, YouTube API, FanBase API if available)
- Analytics: Social API hooks or third-party aggregators (Metricool, Sprout Social)

### Backend:
- Node.js or Python (Flask/FastAPI)
- Cloud hosting (AWS, GCP, or Vercel)
- NoSQL for content (MongoDB), SQL for user/admin tracking

### Frontend:
- React or Next.js dashboard
- Mobile-first UX for real-time approval/editing
- OAuth for social media authentication

---

## 5. Roadmap (MVP to V1.0+)

| Phase   | Feature Set                                                                 |
|---------|------------------------------------------------------------------------------|
| **MVP** | ChatGPT scripts → CapCut template → manual upload & analytics tracker       |
| **V1.0**| Full automation of script → reel → cross-post → performance dashboard       |
| **V1.1**| Voiceover generation (AI avatar optional), community prompt voting          |
| **V1.2**| Token-gated content prompts for verified founder communities                |
| **V2.0**| Generative 3D avatars, voice-to-video, advanced ML-based trend prediction   |

---

## 6. Success Metrics

- Daily post consistency rate.
- Engagement rate per platform.
- Time saved per post (vs. manual).
- Community growth (followers, mentions).
- User retention and NPS.

---

## 7. Open Questions

- Will content include sensitive financial advice or promotional tokens that may require compliance flags?
- Is spillover into Discord, Lens, or Farcaster communities a future need?
- Will founders want voice cloning or AI avatars in future content cycles?
