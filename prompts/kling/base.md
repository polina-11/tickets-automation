# Kling Video Prompt Builder

Generate a Kling prompt from an approved keyframe + scene data.

## Input
- Scene: {{scene}}
- Character Passport: {{character_passport}}
- Approved keyframe image: {{keyframe_path}}

## Kling Prompt Template

```
[Character Identity]
Same exact person as in the reference image.
Identical facial identity — same bone structure, same eyes, same nose, same lips, same face shape.
{{character_passport.locked.identity_anchor}}
Age: {{character_passport.locked.age_band}}. Ethnicity: {{character_passport.locked.ethnicity}}.

[Action]
{{scene.action}}

[Speech]
The character speaks directly: "{{scene.spoken_text}}"
Natural lip movement matching the spoken words.
Emotional delivery: {{scene.emotion}}.

[Environment]
{{scene.location}}

[Camera]
{{scene.camera_framing}} shot.
{{character_passport.default_camera_behavior}}

[Realism]
- Natural blinking, subtle breathing motion
- Realistic skin texture and lighting
- No artificial smoothing
- Emotionally intimate delivery to camera

[DO NOT]
- Do NOT alter the person's face, age, ethnicity, or identity in any way
- Do NOT add any other person unless explicitly requested
- Do NOT change face proportions
- Do NOT make the character look like a different person
- Do NOT use exaggerated expressions — keep it natural
```

## Duration
{{scene.duration_seconds}} seconds

## Aspect Ratio
9:16 vertical (1080x1920)
