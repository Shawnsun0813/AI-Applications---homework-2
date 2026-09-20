# Color Mood Classifier

This project is one self-contained HTML page for a tiny, playful color classifier. It compares a visitor's chosen color with four examples and predicts one of four possible reactions: `delight`, `angry`, `stress`, or `depress`.

## Open and test it

1. Open `one-pixel.html` directly in Chrome, Edge, Safari, or Firefox.
2. Choose a color with the color picker, a quick swatch, or the warmth slider.
3. Click **Classify this color** and read the prediction, color-distance scores, learned weights, and reason.
4. Give the model your own judgment by choosing `delight`, `angry`, `stress`, or `depress`. Your color and label are added as a new training example.
5. Click a training example to test it, or click **Shuffle example meanings** to see how changing the examples changes the result.

There is no build step, API key, paid service, or installation required. The page works offline. A local server is optional:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/one-pixel.html`.

The emotion labels are intentionally subjective examples, not facts about how people must feel. Personal mood, memories, culture, and context can all change a color reaction.
