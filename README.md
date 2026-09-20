# Color Mood Lab

## Name and purpose

**Color Mood Lab** is a tiny, playful color-reaction classifier. It connects a visitor's chosen color with one possible human reaction:

- `delight`
- `angry`
- `stress`
- `depress`

The page is an educational experiment about labels, examples, features, and distance. It does not diagnose emotions or claim that a color has one universal meaning.

## Open and use the page

1. Open [one-pixel.html](one-pixel.html) directly in Chrome, Edge, Safari, or Firefox.
2. Choose a color with the color picker, a quick color swatch, or the personal warmth slider.
3. Click **Classify this color** to see the prediction, distance scores, feature weights, and explanation.
4. Click **Replay training** to watch the model compare the color with each example.
5. Give the model your own judgment by choosing `delight`, `angry`, `stress`, or `depress`. Your color and label become a new training example.
6. Click a training example to test it again, or click **Reset my examples** to restore the starter data.

There is no build step, API key, paid service, or installation. The page works offline. A local server is optional:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/one-pixel.html`.

## How the prediction works

The page turns each color into a small list of numbers, called features: red level, blue level, brightness, and warmth. It also stores those features for each labeled example.

For a new color, the classifier:

1. Measures the new color's distance from every labeled example.
2. Sorts the examples from closest to farthest.
3. Uses the label of the closest example as its prediction.
4. Shows the closest example and its distance so the visitor can understand the reason.

This is a simple nearest-example approach. The **Replay training** panel makes those comparisons visible one at a time.

## One limitation

The classifier learns from only a few hand-picked examples, so it cannot reliably generalize to all colors or all people. Color reactions are subjective and can change with personal mood, memories, culture, and context. Adding more examples can change the result, but it still does not make the prediction a fact about someone's feelings.

## Short development log

- Started with a one-pixel grayscale lesson about labeling dark and light examples.
- Redesigned the page around color and the four requested emotion-reaction labels.
- Added color features, nearest-example distances, learned feature weights, and prediction explanations.
- Added visitor judgment buttons so personal labels become new training examples.
- Added quick color choices, confidence language, accessible label grouping, and a replayable training visualization.
- Tested the page directly in a browser and pushed the project to GitHub.
