# Valentine's Day Website ❤️

A beautiful, romantic interactive Valentine's Day website with advanced animations, particle systems, and engaging experiences — all built with pure HTML, CSS & JavaScript.

**Created by Swan Htet** | [swannhtet.com](https://swannhtet.com) | [GitHub](https://github.com/Swann-Htet)

## 🌟 Features Overview

This comprehensive Valentine's Day experience includes:

- **7 Interactive Pages** — Dashboard, photo gallery, video player, particle animations, love letter, puzzle game, and portrait morphing
- **Advanced Canvas Animations** — Floating hearts, interactive particle systems, and image-to-particle morphing
- **Professional Design** — Romantic color palette (blush pink, deep red, cream, gold) with custom fonts
- **Fully Responsive** — Optimized for mobile and desktop with smooth transitions
- **Zero Dependencies** — Pure HTML/CSS/JS with no external libraries
- **Easy Customization** — Replace photos, videos, and text to personalize your experience

📖 **[View Detailed Page Documentation](docs/PAGES.md)** | 🎨 **[Animation & Customization Guide](docs/FEATURES.md)**

---

## How to Run Locally

### Option 1 — Simply open the file
1. Navigate to the project folder.
2. Double-click **`index.html`** to open it in your browser.

> **Note:** Some browsers restrict local file navigation. If page links don't work, use Option 2.

### Option 2 — Local server (recommended)
Use any lightweight server. For example with Python:

```bash
# Python 3
cd D:\ED
python -m http.server 8000
```

Then open **http://localhost:8000** in your browser.

Or with Node.js:

```bash
npx serve .
```

Or install the **Live Server** extension in VS Code, right-click `index.html` → "Open with Live Server".

> **⚠️ Note:** For `particle-image.html`, you must use a local server (not direct file opening) to avoid CORS errors when loading images.

---

## Project Structure

```
D:\ED\
├── dashboard.html        ← Main landing page with floating hearts animation
├── photos.html          ← Interactive photo gallery with hover effects
├── video.html           ← Video player with custom controls
├── particles.html       ← Interactive particle system with quotes
├── letter.html          ← Animated envelope with love letter
├── puzzle.html          ← Sliding puzzle game (3×3, 4×4, 5×5)
├── particle-image.html  ← Advanced portrait particle morphing
├── styles.css           ← Master stylesheet (~2000 lines)
├── script.js            ← Shared JavaScript (~1000+ lines) 
├── LICENSE.md           ← Creative Commons Attribution 4.0
├── README.md            ← This file
├── docs/
│   ├── PAGES.md         ← Detailed page documentation
│   └── FEATURES.md      ← Animation & customization guide
└── assets/
    ├── images/
    │   ├── 1.jpg - 9.jpg ← Gallery photos (customizable)
    │   └── p.jpg         ← Portrait for particle morphing
    └── video/           ← Video assets folder
```

---

## Quick Start Customization

### 1. Replace Photos (photos.html)
Replace images in `assets/images/` folder:
- **1.jpg - 9.jpg** → Your gallery photos (any aspect ratio, recommended 800px+ width)
- **p.jpg** → Portrait for particle morphing (square preferred, 512px+)

### 2. Add Video (video.html)
Place your video file in `assets/video/` and update the source path:

```html
<video controls preload="metadata">
  <source src="assets/video/your-video.mp4" type="video/mp4">
</video>
```

### 3. Customize Love Letter (letter.html)
Edit the letter content directly in the HTML file — change the text, signature, and envelope color.

### 4. Update Quotes (particles.html)
Modify the romantic quote overlay to personalize the particle experience.

**📖 For detailed customization instructions, see [docs/FEATURES.md](docs/FEATURES.md)**

---

## Technical Features

### Animations & Interactions
- **Canvas-based floating hearts** with physics simulation
- **Interactive particle systems** with mouse repulsion/attraction
- **Image-to-particle morphing** with color sampling and state transitions
- **Smooth page transitions** and hover effects throughout

### Design & Responsiveness
- **Professional color palette:** Blush pink, deep red, cream, and gold
- **Typography:** Playfair Display, Great Vibes, Lora (Google Fonts)
- **Fully responsive:** Optimized layouts for mobile and desktop
- **Accessibility:** Semantic HTML and keyboard navigation support

### Technical Stack
- **Pure HTML/CSS/JavaScript** — No frameworks or dependencies
- **Modern CSS:** Custom properties, flexbox, grid layouts
- **Canvas API:** Advanced 2D graphics and particle systems
- **ES6+:** Modern JavaScript with classes and modules

---

## License & Attribution

**Valentine's Day Website** © 2026 by [Swan Htet](https://swannhtet.com) is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE.md).

**Developer:** Swan Htet • **Website:** [swannhtet.com](https://swannhtet.com) • **GitHub:** [@Swann-Htet](https://github.com/Swann-Htet)

Feel free to use, modify, and share this project! Just include appropriate attribution. 💝
