# Architecture

## System Overview

AI video content production pipeline for TICKETS.
Generates short-form vertical videos (TikTok/Reels) with AI avatars.

## Layers

### 1. GitHub Repo (this repo)
- Prompt templates
- Market/format/character configs
- JSON schemas
- Remotion render templates
- Website insert assets
- Documentation

### 2. Google Drive (media storage)
- Generated keyframes
- Kling video clips
- Voiceover audio
- Final rendered videos
- Job folders with all assets

### 3. Server (187.77.109.4)
- Paperclip agent runtime
- Claude CLI for content generation
- Remotion for video rendering
- Whisper for subtitle timing

## Pipeline Flow

```
Human input → Agent reads templates from repo
  → Claude CLI generates content (ideas/script/storyboard)
  → Kie AI generates keyframes
  → Kling generates video clips (with avatar voice)
  → Whisper extracts word timestamps from clips
  → Agent builds edit_plan.json
  → Remotion renders final MP4
  → Human reviews → approve/reject
  → Final video saved to Google Drive
```

## Key Principle
Agent decides HOW to edit. Remotion executes.
Agent reads templates from repo, generates unique content per video.

## Storage Map

| What | Where |
|------|-------|
| Prompt templates | GitHub `/prompts/` |
| Market configs | GitHub `/config/markets/` |
| Character Passports | GitHub `/config/characters/` |
| Website inserts | GitHub `/assets/website/{country}/` |
| Remotion project | GitHub `/templates/remotion/` |
| Keyframes, clips, finals | Google Drive `/TICKETS Videos/` |
| Job state & metadata | Google Drive `/TICKETS Videos/{job}/metadata.json` |
