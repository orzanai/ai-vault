# FREE: 4 paid apps and their free copies on GitHub

From the reel: *"Claude just made $80 of my subscriptions free."*

Prices were checked on each app's own pricing page on Nov 24, 2026 (individual plans, USD). Together they cost **$79.98 a month**. The four swaps below cost $0.

| You pay for | Price | Free copy | What it does | Download |
|---|---|---|---|---|
| Midjourney (Basic) | $10/mo | **Invoke** · 29K ⭐ · Apache-2.0 | Type a prompt and get an image. Runs AI image models on your own computer | [Mac / Windows / Linux app](https://github.com/invoke-ai/launcher/releases/latest) |
| Photoshop (Single App) | $22.99/mo | **Krita + AI Diffusion** · 10.9K ⭐ · GPL-3.0 | A free Photoshop-style editor, plus a plugin for AI fill, inpaint and outpaint | [Krita](https://krita.org/en/download/) + [the AI plugin](https://github.com/Acly/krita-ai-diffusion/releases/latest) |
| Topaz Photo (annual) | ~$25/mo | **Upscayl** · 53K ⭐ · AGPL-3.0 | Makes blurry or small photos sharp and up to 4× bigger | [Mac / Windows / Linux app](https://github.com/upscayl/upscayl/releases/latest) |
| ElevenLabs (Creator) | $22/mo | **VoiceStudio** · 117K ⭐ · AGPL-3.0 | Voice cloning, voice design, dubbing, transcription, audiobooks | [Mac / Windows app](https://github.com/debpalash/VoiceStudio/releases/latest) |

**Which file do I download?**
- **Mac with Apple chip (M1 or newer):** the `arm64` `.dmg`. Invoke's Mac app is Apple-chip only.
- **Windows:** the `.exe` (Invoke's file is called `Invoke-Community-Edition-Setup`).
- **Linux:** the `.AppImage`.
- **Krita AI plugin:** download Krita first. Then download the plugin `.zip`, open Krita, go to *Tools → Scripts → Import Python Plugin from File*, pick the zip, and restart Krita. The plugin walks you through setting up its local AI server.

---

## Let Claude Code install them for you

Open Claude Code in any folder and paste this. Change the OS if you need to.

```
Install these 4 free apps on my Mac:
- Invoke (https://github.com/invoke-ai/launcher)
- Krita (https://krita.org) plus the AI Diffusion plugin (https://github.com/Acly/krita-ai-diffusion)
- Upscayl (https://github.com/upscayl/upscayl)
- VoiceStudio (https://github.com/debpalash/VoiceStudio)

1. First check my chip (Apple silicon or Intel), free disk space, RAM and GPU, and tell me which of these will run well here.
2. Use the official installer from each project's latest release. Don't build from source if an installer exists.
3. Show me every command before you run it and wait for my OK.
4. For the Krita plugin, tell me exactly which menu to click, since that step happens inside Krita.
5. When you're done, tell me how to open each app and one thing to try first.
```

---

## Honest limits
- **Your computer does the work.** Image models, AI fill and voice cloning want a decent GPU (NVIDIA with 6GB+ VRAM) or an Apple-silicon Mac with 16GB+ RAM. On an old laptop they'll be slow, or won't run at all.
- **Expect big downloads.** AI models are several GB each. Invoke and the Krita plugin download them the first time you use them.
- **They aren't 1:1 copies.**
  - Midjourney's own model has a look you can't download.
  - Invoke uses open models (FLUX, SDXL and others).
  - The paid apps have more polish and cloud features.
- **VoiceStudio's default voice model is non-commercial** (CC-BY-NC). Check each model's license in its Model Manager before client work.
- **Only clone your own voice,** or a voice you have permission to use.
- **Upscayl's last app release was Dec 2024.** It still works, and the repo is active.

Follow [@orzan.ai](https://instagram.com/orzan.ai). The next free one drops tomorrow.
