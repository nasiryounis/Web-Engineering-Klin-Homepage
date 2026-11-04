# Kiln Studio: React homepage

A responsive, single-page business homepage built with React 18 and Vite.
There are no UI libraries, no CSS frameworks, and no image files. All artwork is inline SVG and all
styling is plain CSS.

## Run it

You need Node.js 18 or newer.

```bash
npm install
npm run dev
```

Open the address Vite prints (usually http://localhost:5173).

Other commands:

```bash
npm run build     # production build into dist/
npm run preview   # serve the production build locally
```

## Project structure

```
index.html
vite.config.js
public/
  favicon.svg
src/
  main.jsx                  entry point
  App.jsx                   page layout
  styles/global.css         design tokens, reset, buttons, logo
  data/
    content.js              all page copy: links, services, projects, testimonials, contact
    palette.js              colors used inside SVG illustrations
  components/
    Navbar.jsx / .css       sticky nav, active-section highlight, mobile menu
    Hero.jsx / .css         headline, call-to-action buttons, animated illustration
    HeroArt.jsx             hero illustration (SVG)
    About.jsx / .css        intro, illustration, Read More toggle
    AboutArt.jsx            about illustration (SVG)
    Services.jsx / .css     four service cards
    Portfolio.jsx / .css    three project cards
    ProjectArt.jsx          project thumbnails (SVG)
    WhyChooseUs.jsx / .css  four benefits
    Testimonials.jsx / .css three testimonials with ratings
    CallToAction.jsx / .css closing banner (also the #contact anchor)
    Footer.jsx / .css       logo, links, social icons, contact details, copyright
    Button.jsx              shared link/button component
    Logo.jsx, Icons.jsx, Avatar.jsx
```

## Customizing

- **Copy and links:** edit `src/data/content.js`. Replace the sample company name, email, phone
  number, address, testimonials, and social URLs with your own.
- **Colors:** change the custom properties at the top of `src/styles/global.css`, and the matching
  values in `src/data/palette.js` (used by the SVG artwork).
- **Fonts:** Bricolage Grotesque and Instrument Sans load from Google Fonts in `index.html`.
  Without an internet connection the page falls back to system fonts.

## How the interactive parts work

- Nav links and buttons are anchor links that scroll smoothly to each section.
- The nav highlights the section you are viewing (IntersectionObserver).
- On screens 900px wide or narrower the links collapse into a menu that closes on link click,
  on Escape, and when the window widens.
- "Read More" in the About section expands and collapses extra text.
- "Book a Free Call" opens an email to the address in `content.js`.
- Animations respect the operating system's reduced-motion setting.

All names, testimonials, and figures in this project are sample content.
