# Claude Battle: Auric Voyage

[![Live site](https://img.shields.io/badge/live-eval--forge.github.io%2Fclaude--battle-c4582f?style=for-the-badge)](https://eval-forge.github.io/claude-battle/)
[![Eval Forge](https://img.shields.io/badge/Eval%20Forge-homepage-2e50ed?style=for-the-badge)](https://eval-forge.github.io)

![Winner](https://img.shields.io/badge/winner-Fable%205.2-2f5d62?style=flat-square)
![Models](https://img.shields.io/badge/models-4-c4582f?style=flat-square)
![Effort](https://img.shields.io/badge/effort-high-776e62?style=flat-square)
![Three.js](https://img.shields.io/badge/Three.js-single%20HTML%20file-000000?style=flat-square&logo=threedotjs&logoColor=white)
![HTML](https://img.shields.io/badge/HTML5-standalone-e34f26?style=flat-square&logo=html5&logoColor=white)

Fable 5.2, Opus 5.5, Sonnet 5.5 and Haiku 5.5, all on `high` effort, all given the same prompt and the same reference image: build **Auric Voyage**, an ornate golden fantasy sailing ship in Three.js, as one standalone HTML file.

| | | | |
|:---:|:---:|:---:|:---:|
| [![Fable 5.2](previews/fable-5-2.jpg)](https://eval-forge.github.io/claude-battle/fable-5-2.html) | [![Opus 5.5](previews/opus-5-5.jpg)](https://eval-forge.github.io/claude-battle/opus-5-5.html) | [![Sonnet 5.5](previews/sonnet-5-5.jpg)](https://eval-forge.github.io/claude-battle/sonnet-5-5.html) | [![Haiku 5.5](previews/haiku-5-5.jpg)](https://eval-forge.github.io/claude-battle/haiku-5-5.html) |
| **#1 Fable 5.2** | **#2 Opus 5.5** | **#3 Sonnet 5.5** | **#4 Haiku 5.5** |

## Results

| Rank | Model | Score (S) | Truthness to prompt (P) | Time | Time score (T) | Final |
|:---:|:---|:---:|:---:|:---:|:---:|:---:|
| 1 | [Fable 5.2](fable-5-2.html) ![92.4](https://img.shields.io/badge/final-92.4-2f5d62?style=flat-square) | 92 | 95 | 1h 27m | 0.0 | **92.4** |
| 2 | [Opus 5.5](opus-5-5.html) ![81.3](https://img.shields.io/badge/final-81.3-c4582f?style=flat-square) | 78 | 90 | 1h 01m | 35.1 | **81.3** |
| 3 | [Sonnet 5.5](sonnet-5-5.html) ![76.6](https://img.shields.io/badge/final-76.6-c4582f?style=flat-square) | 67 | 100 | 52m | 47.3 | **76.6** |
| 4 | [Haiku 5.5](haiku-5-5.html) ![32.5](https://img.shields.io/badge/final-32.5-776e62?style=flat-square) | 12 | 80 | 13m | 100.0 | **32.5** |

## The formula

```
Final = 0.70 * S + 0.295 * P + 0.005 * T

T = 100 * (t_max - t) / (t_max - t_min)        t_min = 13 min, t_max = 87 min
```

- **S**: score, 0 to 100. Overall quality of the scene.
- **P**: truthness to prompt, 0 to 100. How much of what the prompt asked for is there and working.
- **T**: time score, 0 to 100. Fastest entry gets 100, slowest gets 0.

Weights are 70% score, 29.5% truthness, 0.5% time. Being the fastest is worth half a point, so time only ever breaks a near tie.

## Files

| File | What it is |
|:---|:---|
| `index.html` | The results page: ranking, formula, live previews, charts and the full prompt |
| `fable-5-2.html`, `opus-5-5.html`, `sonnet-5-5.html`, `haiku-5-5.html` | The four entries, exactly as each model delivered them |
| `previews/` | Screenshots used on the results page and above |
| `fable-5-2-torus-knot.html` | Bonus: a shimmering torus knot, not part of the battle |

Open `index.html` locally or visit the live site. The scores, times and weights live in one `ENTRIES` array and one `W` object at the bottom of `index.html`, so adding a model is a one-line job.
