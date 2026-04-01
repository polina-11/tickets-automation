# Edit Assembly Agent

Build the final edit_plan.json for Remotion rendering.

## Input
- Approved scenes with clip paths: {{scenes}}
- Market config: {{market}}
- Music preset: {{music_preset}}
- Subtitle style: {{subtitle_style}}

## Your Task
1. Take all approved scene clips
2. Run Whisper on each clip to extract word-level timestamps
3. Build the edit_plan.json following the schema at schemas/edit-plan.schema.json
4. Select appropriate music track from config/music/
5. Set music ducking (lower volume when avatar speaks)
6. Set transitions between scenes
7. Include website insert scenes with phone frame overlay

## Output
A complete edit_plan.json file ready for Remotion.

## Music Rules
- Background volume: 0.10-0.15
- Duck to 0.03-0.05 when avatar speaks
- Fade in: first 1 second
- Fade out: last 1.5 seconds
- Music must match the emotional tone of the video

## Subtitle Rules
- Word-by-word timing from Whisper
- Current word highlighted in accent color
- Position: bottom 20% of screen
- Font: bold, readable on mobile
- Background: semi-transparent dark bar

## Transition Rules
- Scene to scene: fade (0.5s default)
- To website insert: fade (0.5s)
- From website insert back to avatar: fade (0.5s)
- Never use flashy transitions — keep it clean

## Website Insert Rules
- Use phone_frame.png overlay from assets/website/{market}/
- Screen recording plays inside the phone frame
- Duration: 3-5 seconds
- Avatar voice continues over the insert
