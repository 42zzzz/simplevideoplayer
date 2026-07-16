## Debloated simplevideoplayer

A stripped-down single-file version of [Ifedapo A. Olarewaju's Simple Video Player](https://github.com/ifedapoolarewaju/simplevideoplayer).

This fork wouldn't exist without Ifedapo's original work, thank you Ifedapo.

### Differences from the original

**Original** ([ifedapoolarewaju/simplevideoplayer](https://github.com/ifedapoolarewaju/simplevideoplayer))

- **Stack:** Next.js 14 + React + TypeScript, multiple components in `src/`, custom React context, JSX/TSX compilation
- **Dependencies:** Node.js, npm, `next.config.mjs`, `package.json` with ~20 packages
- **Build:** Requires `npm install && npm run build`; deployable to Vercel
- **Audio:** Web Audio API (`AudioContext` + `GainNode`) for volume amplification up to 400%
- **Theme:** Pink accent, animated GitHub corner ribbon, logo images
- **Controls:** Separate actions bar (PiP, subtitle file picker, exit) below the main controls overlay
- **Tracking:** GTM / analytics script
- **Accessibility:** No explicit focus indicators or ARIA labeling
- **Mobile:** No touch-specific handling; controls rely on `mousemove`

**Mine** (`simplevideoplayer.html`)

- **Stack:** Single `.html` file — zero dependencies, no build step, open in any browser
- **Audio:** Native `<video>.volume` only (0–1 range); no Web Audio API
- **Theme:** Black & white; plain text GitHub link; no logos or images
- **Controls:** Unified toolbar: Play/Pause, Mute + volume slider, duration, Subtitles, Fullscreen
- **Keyboard:** `j`/`l` seek ±10s, `k` play/pause, `,`/`.` frame step, `>`/`<` speed, `0`–`9` seek %, `Home`/`End`, `C` toggle subtitles, `Esc` context-sensitive (fullscreen → home → close modal)
- **Subtitles:** Settings modal with ms text input (±1s buttons), px text size, background opacity slider, VTT `line:` position slider; toggle on/off (`C`); remove button; filename shown in modal
- **Drag-and-drop:** Video onto home view, subtitle files onto player view
- **Mobile:** `touchend` triggers controls, larger 36×36px touch targets at ≤720px
- **WCAG 2.0 Compliant:** Focus-visible outlines on all controls, `aria-label` on every interactive element, color contrast ≥4.5:1, fully keyboard-operable
- **Tracking:** None
- **Persistence:** Subtitle preferences (size, bg opacity, vertical position) saved to `localStorage`

### Contribution
PRs and ideas welcome. This is a hobby project and I'd love to see what others want to add.
