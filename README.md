# Fullscreen API (iOS) — How to hide tabs in Safari
Hide Mobile Safari tabs on iPhone to emulate fullscreen for web apps and games. A lightweight workaround using Visual Viewport instead of the standard Fullscreen API.

The page locking approach used here is adapted from the technique described in the article [I fixed a decade-long iOS Safari problem](https://stripearmy.medium.com/i-fixed-a-decade-long-ios-safari-problem-0d85f76caec0).

[Live demo](https://playgama.github.io/hide-mobile-safari-tabs/) · [Example index.html](https://github.com/Playgama/hide-mobile-safari-tabs/blob/main/index.html)

## TL;DR
This approach helps you **hide Safari tabs and the address bar** in iOS landscape mode, giving a **fullscreen-like** effect for web apps and games. It monitors visualViewport and locks the layout when the browser UI collapses. The repository does **not** ship a standalone script; see [index.html](https://github.com/Playgama/hide-mobile-safari-tabs/blob/main/index.html) for the minimal, copy‑paste example.
- 📱 Works on Safari & Chrome for iOS (Safari 18 and 26.1+)
- 🧠 Uses window.visualViewport

## Why not just use the Fullscreen API (iOS)?
On iPhone Safari, the **Fullscreen API** is not available or unreliable for arbitrary elements. This project is a **simple workaround** that creates the same immersive effect **without user permission prompts**.
PWAs with `display: standalone` already hide the UI, but for regular web apps and games, this method gives you back that precious screen space.

## How it works (Hide Mobile Safari Tabs)
1. Track viewport changes using visualViewport.
2. Detect when Safari’s bars (tabs, address) are visible.
3. Show a hint overlay telling the user to scroll.
4. Add a spacer to enable scrolling.
5. Once tabs collapse — lock the page to maintain fullscreen.

Implementation: see [index.html](https://github.com/Playgama/hide-mobile-safari-tabs/blob/main/index.html) for the complete code.

## Usage examples
### 📺 Landscape orientation for HTML5 browser games
This approach was originally developed and tested for **HTML5 browser games** that run in **landscape mode** on iPhone. In that mode, Safari’s top and bottom UI elements (address bar, tab bar) take up a significant portion of the screen and can ruin the immersive experience.
By applying this script, we achieve a stable, fullscreen-like view — ideal for mobile game engines such as Phaser, Construct, Pixi.js, or custom canvas-based projects. Once the user scrolls slightly and the Safari UI collapses, the viewport becomes fully usable, allowing games to run truly edge-to-edge.

### 💡 Other possible uses
- Interactive demos or web apps that need immersive layouts.
- Kiosk or exhibition web builds.
- Testing fullscreen UX on iOS when Fullscreen API isn’t available.

## Browser Notes
- **iPhone Safari / Chrome**: main target.
- **iPad / Desktop**: prefer native Fullscreen API.

## FAQ
**Does it break UX guidelines?**
No, it only guides users to scroll — a native gesture.

**Can I use it in portrait?**
No — this approach targets landscape on iPhone. In portrait, the helper does not activate or show any UI.

## SEO notes (discoverability)
**Primary phrase**: Fullscreen API (iOS) - How to hide tabs in Safari
**Keywords**
- fullscreen api ios
- safari ios hide tabs
- hide mobile safari tabs
- safari iphone fullscreen fix
- visual viewport safari
- fullscreen web game ios
- pwa fullscreen ios
- mobile safari landscape
- safari 100vh fix
