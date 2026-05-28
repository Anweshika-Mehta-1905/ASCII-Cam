What It Does
Opens your webcam and renders the live feed as ASCII characters in a pink neon color scheme. Your face and surroundings are continuously converted into text art at up to 30fps.

How to Use

Open index.html in any modern browser (Chrome, Edge, Firefox, Safari)
Click ▶ Start Camera and allow camera access when prompted
You'll see yourself rendered in ASCII art with a hot-pink glow
Use the controls to tweak the look:

ControlWhat it doesResolutionLow (80) / Medium (120) / High (180) columns — more columns = finer detail but heavier CPUBrightnessShifts the overall lightness up or down (−80 to +80)ContrastStretches or compresses the tonal range (0.5× to 2.5×)MirrorFlips the feed horizontally (on by default, like a selfie camera)■ StopStops the camera and returns to the start screen

How It Works (Technical)
ASCII character mapping — brightness is mapped to a 70-character ramp from sparse/dark ( . ' \``) to dense/bright (# M W @ $`). Darker pixels get airy characters; brighter pixels get heavy ink-like ones.
Color — instead of plain white, brightness maps through five pink stops: black → deep rose → hot pink → bubblegum → pastel blush. The effect is a neon-pink gradient that follows the lighting on your face.
Performance — the video frame is first downsampled to a tiny cols × rows canvas (e.g. 120×68 pixels) before reading pixel data. This keeps the per-frame cost low even at high resolution settings.
Luminance uses the ITU-R BT.601 perceptual weighting (0.299R + 0.587G + 0.114B) rather than a simple average, so brightness feels natural to the human eye.
