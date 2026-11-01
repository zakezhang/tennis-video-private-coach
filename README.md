# Tennis Video Private Coach

**English** · [中文](README.zh-CN.md)

A Claude Skill that turns your tennis practice video into a coaching review: what breaks down in your stroke, which shots prove it, and exactly what to practice next.

Give it a phone video of a practice session and it will:

- **Find every swing** and separate forehands, two-handed backhands and one-handed backhands.
- **Pick your 3 best and 3 worst shots** of each type and render annotated slow-motion clips: your real footage at quarter speed, with your swing path drawn on it, freezes at the top of the take-back and at contact, and your best swing overlaid on your worst as a dashed line.
- **Count net and out** when the ball is visible (practice wall, clean indoor footage), and tell you plainly when it isn't.
- **Measure technique** on every swing: take-back height, knee bend, stance width, contact height.
- **Check knees and footwork**: hopping, one-leg landings, pivoting on a locked straight leg.
- **Compare with your last review**, so you can see what actually changed.
- **Write your next session**: drills with reps, a countable target, and when to move on, matched to whether you train with a wall, a ball machine, a coach or a partner.

It also ships with a table of common amateur faults (sky balls, late contact, upright two-hander take-back, hopping, late one-hander) with how each shows on video and how to fix it.

## What's inside

```
skills/
  tennis-video-private-coach/      English skill
    SKILL.md
  tennis-video-private-coach-zh/   Chinese skill (中文版)
    SKILL.md
docs/
  index.html                       Project page (GitHub Pages)
```

Install one language version; they contain the same method.

## Install

**Claude apps (claude.ai / desktop):** zip the skill folder you want (for example `tennis-video-private-coach/`) and upload it as a custom skill in Claude's settings. Code execution needs to be enabled.

**Claude Code:** copy the folder into `~/.claude/skills/` (personal) or `.claude/skills/` in a project.

The skill needs an environment that can run Python 3 and ffmpeg and install `ultralytics`, `opencv-python`, `numpy`, `scipy` and `Pillow`. No GPU required.

## Use it

Upload your practice video and tell Claude:

- which person in the frame is you (clothing, position);
- your dominant hand, and one- or two-handed backhand;
- where you practiced (wall / ball machine / coach / rally, indoor or outdoor);
- the one thing you most want fixed, for example *"lots of my forehands fly long"*.

Example prompt:

> Here's 20 minutes of me hitting against the wall. I'm the one in the white shirt, right-handed, two-handed backhand. My forehands keep going into the net when the ball comes fast. Review it and tell me what to practice this week.

If you have a previous review, include it and you'll get a before/after comparison.

## Filming tips

- **Side-on is the most useful angle**: outside the net on your hitting side, 3–4 m away, waist height.
- **Behind you** (1.2–1.5 m high, centered) is best for counting net/out.
- Shoot 4K 60 fps or 1080p 120 fps, lock focus and exposure, and record a few continuous minutes rather than many short clips.
- Outdoors, frame more of the far court and less sky and trees.

## Limits

- Pose comes from a single phone camera, so knee angles and contact depth are approximate. Compare your numbers with your own past sessions, not with other people.
- With moving trees or many people in the background, the ball usually can't be tracked, so no net/out percentage is reported.
- This is not medical advice. If a knee or anything else keeps hurting, see a sports-medicine doctor.

## License

MIT. See [LICENSE](LICENSE).
