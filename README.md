# UI Profile Card — Case Study

**Live Demo:** [sfezekile.github.io/UI-Profile-Card](https://sfezekile.github.io/UI-Profile-Card/)

---

## Overview

UI Profile Card is a front-end component project showcasing two distinct visual design approaches to a user profile card. Built with pure HTML and CSS, the project demonstrates layout techniques, neumorphic design patterns, responsive design, and image-handling strategies — all without any JavaScript.

---

## The Problem

Profile cards are one of the most common UI patterns across social platforms, dashboards, and portfolio sites. Despite their simplicity, they present several design challenges:

- How do you display user information cleanly without it feeling flat or generic?
- How do you handle images in cards — as standard `<img>` tags or as CSS background images?
- How do you make a component feel tactile and modern using only CSS?
- How do you ensure the layout holds up across screen sizes?

This project explores two answers to those questions side by side.

---

## Design Approach

### Card 1 — Dark Neumorphic Card

The first card uses a **dark neumorphic design** on a `#1A1A1A` background. The profile image is rendered as a standard `<img>` element, keeping it semantic and accessible.

The Follow button uses an **inset box shadow** to simulate a pressed, physical surface:

```css
box-shadow: inset 4px 4px 10px #2C2C2C, inset -4px -4px 10px #000;
```

On hover, an outer shadow is added to create a "lifted" effect, giving the button tactile feedback without JavaScript.

### Card 2 — Frosted Glass Overlay Card

The second card takes a different approach: the profile image is set as a **CSS background image** on the card itself, with the content overlaid using a frosted glass panel:

```css
backdrop-filter: blur(5px);
background: rgba(0, 0, 0, 0.2);
```

This creates a modern glassmorphism aesthetic where the user's image bleeds into the card background, and the text sits on a translucent layer above it. The Follow button mirrors the neumorphic style but uses a **light/white palette** to contrast against the dark image beneath.

---

## Technical Decisions

### Layout — Flexbox

The container uses `flex-wrap: wrap` so cards stack vertically on smaller screens and sit side by side on wider ones. Cards use `flex: 1 1 320px` with a `max-width: 400px`, allowing them to grow and shrink fluidly without media query breakpoints for the core layout.

### Typography — Google Fonts

The project imports a wide range of Google Fonts (`Inter`, `Raleway`, `Nunito`, `Cormorant Garamond`, etc.), with `Inter` applied as the body font. This gives the project a clean, neutral typographic base while making it easy to swap typefaces for experimentation.

### Icons — Remixicon

Icons (follower count, likes, verified badge, follow button) are sourced from [Remixicon](https://remixicon.com/) via CDN. Icon color uses `var(--secondary-color)` (`#3855f7`) for brand consistency, with a hover transition to white.

### CSS Custom Properties

A small set of CSS variables keeps the design consistent and easy to theme:

```css
:root {
    --secondary-color: #3855f7;
    --text-color: #333;
    --text-light: #666;
    --white-dark: #dcdcdc;
    --box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
```

---

## Responsive Behaviour

| Breakpoint | Behaviour |
|---|---|
| Default | Cards sit side by side, flex layout |
| `≤ 768px` | Reduced padding, smaller font sizes |
| `≤ 480px` | Cards stack vertically, button spans full width |

---

## File Structure

```
UI-Profile-Card/
├── index.html
└── src/
    ├── Style/
    │   └── style.css
    └── image/
        ├── image 2 (1).png   ← Card 1 profile image
        └── image 2.png       ← Card 2 background image
```

---

## Key Takeaways

- **Two image strategies** (`<img>` vs `background-image`) produce very different visual results and suit different use cases — semantic images for accessibility, background images for decorative bleed effects.
- **Neumorphism** works well on dark backgrounds where shadow contrast is achievable without washing out content.
- **Glassmorphism** is most effective when there is a rich, colorful image underneath the frosted layer.
- Pure CSS can produce polished, interactive-feeling components without any JavaScript when box shadows and transitions are used intentionally.

---

## Built With

- HTML5
- CSS3 (Flexbox, Custom Properties, `backdrop-filter`)
- [Remixicon](https://remixicon.com/) — icon library
- [Google Fonts](https://fonts.google.com/) — typography

---

*Component design by [@sfezekile](https://github.com/sfezekile)*
