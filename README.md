<p align="center">
  <img src="./assets/readme/hero.svg" width="100%" alt="Tennis Video Private Coach: upload a practice video, get annotated slow motion of your best and worst shots and a plan for your next session">
</p>

<p align="center">
  <b>English</b> · <a href="README.zh-CN.md">中文</a> · <a href="https://zakezhang.github.io/tennis-video-review-public/">Project page</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude-Skill-24608f?style=flat-square" alt="Claude Skill">
  <img src="https://img.shields.io/badge/language-EN%20%2B%20%E4%B8%AD%E6%96%87-24608f?style=flat-square" alt="English and Chinese">
  <img src="https://img.shields.io/badge/license-MIT-d9f21c?style=flat-square&labelColor=153a58" alt="MIT license">
</p>

**Tennis Video Private Coach** is a Claude Skill for amateur players. Give Claude a phone video of your practice and get back what a coach would tell you after watching it: which part of your stroke breaks down, the shots that prove it, and what to practice next.

## What you get

- **12 annotated clips**: your 3 best and 3 worst forehands and backhands, at quarter speed on your own footage, with your swing path drawn on you, freezes at the take-back and at contact, and your best swing overlaid on your worst.
- **A straight answer to your question**, such as *"why do my forehands fly long?"*, at the top of the report.
- **Technique measured on every swing**: take-back height, knee bend, stance width, contact height.
- **Knees and footwork, every time**: hopping, one-leg landings, pivoting on a straight leg.
- **Net and out counts** when the ball is visible, and a plain note when it isn't.
- **A plan for your next session** that fits how you train: wall, ball machine, coach or partner.

<p align="center">
  <img src="./assets/readme/workflow.svg" width="100%" alt="How it works: upload video, find every swing, pick best and worst, render annotated clips, write the next-session plan">
</p>

## Quick start

**1. Install one language version**

| Where you use Claude | How |
| --- | --- |
| Claude apps (web, desktop) | Zip `skills/tennis-video-private-coach/` and upload it as a custom skill in settings. Code execution must be on. |
| Claude Code | `cp -r skills/tennis-video-private-coach ~/.claude/skills/` |

The Chinese version is `skills/tennis-video-private-coach-zh/`. The skill runs Python 3 and ffmpeg and installs `ultralytics`, `opencv-python`, `numpy`, `scipy` and `Pillow`. No GPU needed.

**2. Upload a video and say three things**

> Here's 20 minutes of me hitting against the wall. **I'm the one in the white shirt, right-handed, two-handed backhand.** My forehands go into the net when the ball comes fast. Review it and tell me what to practice this week.

Which player you are, how you hold the racket, and the one problem you want fixed. Add last time's report to get a before/after comparison.

## Faults it checks first

| You notice | It usually finds |
| --- | --- |
| Balls fly long or into the sky | A swing path that finishes straight up; lifting from the knees on high bounces |
| Forehands into the net | A take-back above the head, so the racket can't drop in time |
| Contact too far back, then crowded | Late preparation: reaching for wide balls, flicking fast ones |
| Two-handed backhand into the net | The racket held upright at the chest instead of resting at the hip |
| Hopping, landing on one leg | A narrow stance and swinging before the feet stop |
| Late one-handed backhand | Setting up as a two-hander, then switching |

Each comes with how it shows on video and a drill to fix it.

## Film it so the review is sharp

- **Side-on is the most useful angle**: outside the net on your hitting side, 3–4 m away, at waist height.
- **Behind you**, 1.2–1.5 m high and centered, is best for counting net and out.
- 4K 60 fps or 1080p 120 fps, focus and exposure locked, a few continuous minutes.
- Outdoors, frame more of the far court and less sky and trees.

## Limits

- Pose comes from one phone camera, so angles are estimates. Compare with your own past sessions, not with other players.
- With moving trees or many people in the background the ball usually can't be tracked, so no net/out percentage is given.
- Not medical advice. If something keeps hurting, see a sports-medicine doctor.

<details>
<summary><b>What's in this repository</b></summary>

```
skills/
  tennis-video-private-coach/      English skill
  tennis-video-private-coach-zh/   Chinese skill
docs/index.html                    Project page (GitHub Pages)
assets/readme/                     README images (SVG)
```

</details>

## License

MIT. See [LICENSE](LICENSE).
