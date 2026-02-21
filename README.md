# IonicGameCongrats 🏆

A lightweight, animated congratulations page designed to be used as the **win screen** for Ionic mobile games. It is hosted on GitHub Pages and can be launched from any Ionic (or web-based) game by redirecting to its URL with a few query parameters.

## Live Demo

🔗 [https://sabriahmedamine.github.io/IonicGameCongrats.github.io/](https://sabriahmedamine.github.io/IonicGameCongrats.github.io/)

---

## Features

- 🎨 **Animated gradient background** that shifts between deep blue, red, and gold
- ⭐ **Twinkling star field** generated dynamically on every load
- 🎊 **Confetti rain** that falls across the screen on arrival
- 🏆 **Trophy pop-in animation** with the player's name underlined in gold
- 🌐 **Bilingual support** – French (`fr`) and Arabic (`ar`, RTL layout)
- 📱 **Responsive** – works on any screen size (mobile, tablet, desktop)

---

## URL Parameters

The page reads the following **query string parameters** from the URL:

| Parameter | Description | Default |
|-----------|-------------|---------|
| `nom`     | Player name displayed on the screen | `Joueur` |
| `score`   | Final score to display | `0` |
| `langue`  | Language code (`fr` or `ar`) | `fr` |

### Example

```
https://sabriahmedamine.github.io/IonicGameCongrats.github.io/?nom=Ahmed&score=950&langue=ar
```

This opens the page in Arabic, greeting **Ahmed** with a score of **950**.

---

## Usage in an Ionic App

From your Ionic game, redirect to the congratulations page when the player wins:

```typescript
import { Browser } from '@capacitor/browser';

const playerName  = 'Ahmed';
const playerScore = 950;
const language    = 'ar'; // 'fr' or 'ar'

const url = `https://sabriahmedamine.github.io/IonicGameCongrats.github.io/`
          + `?nom=${encodeURIComponent(playerName)}`
          + `&score=${playerScore}`
          + `&langue=${language}`;

await Browser.open({ url });
```

---

## Project Structure

```
IonicGameCongrats.github.io/
├── index.html      # Main congratulations page (HTML + CSS + JS, single file)
├── mosquee.png     # Favicon displayed in the browser tab
└── README.md       # This file
```

---

## Supported Languages

| Code | Language |
|------|----------|
| `fr` | French (default, LTR) |
| `ar` | Arabic (RTL layout) |

Any unrecognised language code falls back to French.

---

## License

This project is open source. Feel free to fork and adapt it for your own Ionic games.
