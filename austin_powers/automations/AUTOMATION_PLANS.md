# 🤖 AUTOMATIONS — Project Austin Powers

## n8n Workflows & AI Scripts

---

## 📋 PLANNED AUTOMATIONS

### 1. Content Log (Priority: HIGH)

**Purpose:** Store every song/clip idea + status in one tracker

| Field | Type | Description |
|-------|------|-------------|
| ID | Auto | Unique identifier |
| Title | Text | Song/clip name |
| Type | Select | Serious / Malody / Idea |
| Status | Select | Idea / In Progress / Ready / Posted |
| Hook Timestamp | Text | Where the hook starts |
| Platform | Multi-select | TikTok / Reels / Shorts / DSPs |
| Posted Date | Date | When it went live |
| Performance | Number | Views/streams |
| Notes | Long text | Additional context |

**Implementation:** Google Sheet or Airtable
**n8n Trigger:** Manual input form or webhook

---

### 2. Posting Checklist (Priority: HIGH)

**Purpose:** Auto-generate weekly checklist and reminders

**Workflow:**

1. Every Sunday evening, generate next week's posting schedule
2. Pull from Content Log (items marked "Ready")
3. Create checklist in preferred format
4. Send reminder via email/Slack/Discord

**n8n Nodes:**

- Schedule Trigger (Sunday 6 PM)
- Google Sheets (read Content Log)
- Filter (status = Ready)
- Format checklist
- Send notification

---

### 3. Asset Intake (Priority: MEDIUM)

**Purpose:** Auto-organize new files into proper folders

**Workflow:**

1. Monitor incoming folder (e.g., /incoming/)
2. Detect file type (audio, video, image)
3. Move to appropriate folder:
   - `.mp3`, `.wav`, `.m4a` → `/assets/audio/`
   - `.mp4`, `.mov` → `/assets/video/`
   - `.jpg`, `.png` → `/assets/images/`
4. Log the action

**Implementation Options:**

- n8n with local file trigger (if available)
- Python script with watchdog
- PowerShell scheduled task

---

### 4. Release Pack Builder (Priority: MEDIUM)

**Purpose:** Auto-create release folder with subfolders

**Workflow:**

1. Trigger: New release name input
2. Create folder structure:

```
/releases/serious/[release-name]/
├── masters/
├── artwork/
├── clips/
├── captions/
└── RELEASE_INFO.md
```

3. Generate RELEASE_INFO.md template
2. Notify team

---

## 🔧 SCRIPTS TO BUILD

### Python Scripts

- [ ] `rename_files.py` — Batch rename with consistent format
- [ ] `extract_hook.py` — Cut audio file to specific timestamp range
- [ ] `generate_release_pack.py` — Create release folder structure

### PowerShell Scripts

- [ ] `backup_to_cloud.ps1` — Sync to OneDrive/Google Drive
- [ ] `organize_imports.ps1` — Sort incoming files by type

---

## 📊 AUTOMATION STATUS

| Automation | Priority | Status | Location |
|------------|----------|--------|----------|
| Content Log | High | 🔲 Not started | TBD |
| Posting Checklist | High | 🔲 Not started | TBD |
| Asset Intake | Medium | 🔲 Not started | TBD |
| Release Pack Builder | Medium | 🔲 Not started | TBD |

---

## 🔗 INTEGRATION POINTS

### Data Sources

- Google Sheets (Content Log, Analytics)
- Spotify API (metrics, if accessible)
- Social media platforms (posting, analytics)

### Notifications

- Email
- Discord (if using)
- Slack (if using)

### File Storage

- Local: `/austin_powers/` folder structure
- Cloud: OneDrive (current workspace)

---

## 💡 FUTURE AUTOMATION IDEAS

- [ ] Auto-post to multiple platforms simultaneously
- [ ] Analytics aggregator (pull all platform stats into one dashboard)
- [ ] Release countdown automation (auto-post daily countdowns)
- [ ] Comment response templates
- [ ] Playlist pitching tracker

---

*Last Updated: January 13, 2026*
