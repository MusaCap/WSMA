# 📊 Web3 Social Media Agent - Data Model

## 1. User

- **user_id** (UUID) – Primary Key
- **name** (String)
- **email** (String, unique)
- **role** (Enum: Founder, Admin, Editor, Analyst)
- **profile_picture_url** (String)
- **connected_accounts** (Array of SocialAccount IDs)
- **created_at** (Timestamp)
- **updated_at** (Timestamp)

---

## 2. SocialAccount

- **account_id** (UUID) – Primary Key
- **user_id** (Foreign Key → User.user_id)
- **platform** (Enum: TikTok, Instagram, Facebook, YouTube, SpillApp, FanBase)
- **username** (String)
- **auth_token** (Encrypted String)
- **last_synced_at** (Timestamp)

---

## 3. Prompt

- **prompt_id** (UUID) – Primary Key
- **user_id** (Foreign Key → User.user_id)
- **content** (Text)
- **source_type** (Enum: manual, trending_topic, link, hashtag)
- **tags** (Array of Strings)
- **created_at** (Timestamp)

---

## 4. Script

- **script_id** (UUID) – Primary Key
- **prompt_id** (Foreign Key → Prompt.prompt_id)
- **title** (String)
- **body** (Text)
- **tone** (Enum: educational, humorous, edgy, founder-focused)
- **status** (Enum: draft, approved, edited)
- **generated_by** (Enum: AI, user)
- **created_at** (Timestamp)
- **updated_at** (Timestamp)

---

## 5. VideoAsset

- **video_id** (UUID) – Primary Key
- **script_id** (Foreign Key → Script.script_id)
- **edit_tool** (Enum: CapCut, Descript, Manual, RunwayML)
- **video_url** (String)
- **thumbnail_url** (String)
- **duration_sec** (Integer)
- **format** (Enum: vertical, square, landscape)
- **status** (Enum: in_progress, ready, published)
- **created_at** (Timestamp)
- **updated_at** (Timestamp)

---

## 6. Post

- **post_id** (UUID) – Primary Key
- **video_id** (Foreign Key → VideoAsset.video_id)
- **platform** (Enum: TikTok, Instagram, etc.)
- **caption** (Text)
- **cta** (String)
- **status** (Enum: scheduled, published, failed)
- **scheduled_time** (Timestamp)
- **published_time** (Timestamp)
- **platform_post_id** (String)
- **created_at** (Timestamp)

---

## 7. Analytics

- **analytics_id** (UUID) – Primary Key
- **post_id** (Foreign Key → Post.post_id)
- **views** (Integer)
- **likes** (Integer)
- **comments** (Integer)
- **shares** (Integer)
- **saves** (Integer)
- **watch_time_sec** (Integer)
- **engagement_rate** (Decimal)
- **collected_at** (Timestamp)

---

## 8. OptimizationReport

- **report_id** (UUID) – Primary Key
- **user_id** (Foreign Key → User.user_id)
- **period** (Date Range)
- **top_performers** (Array of Post IDs)
- **best_time_to_post** (Time of Day)
- **hashtag_insights** (Array of Strings)
- **recommendations** (Text or JSON)
- **generated_at** (Timestamp)

---

## Relationships Summary

- One **User** → Many **SocialAccounts**
- One **User** → Many **Prompts**
- One **Prompt** → One or Many **Scripts**
- One **Script** → One or Many **VideoAssets**
- One **VideoAsset** → One or Many **Posts**
- One **Post** → One **Analytics** record (updated over time)
- One **User** → Many **OptimizationReports**

---

## Optional Future Entities

### TokenGating
- **token_id**, **required_wallet_address**, **access_level**

### VoiceClone
- **voice_id**, **script_id**, **voice_data_url**

