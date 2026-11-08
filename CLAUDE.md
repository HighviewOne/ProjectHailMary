# Project Hail Mary — A Tribute

A personal fan tribute site for Andy Weir's novel and the 2026 film. Everything lives in
`index.html`: inline CSS, inline SVG (Rocky illustration) and inline JS (star field, scroll
reveal, nav highlight, Rocky's Web Audio "voice"). There is no build step and there are no
dependencies. Keep it that way.

## Deploy

Every push to `main` deploys to GitHub Pages (https://highviewone.github.io/ProjectHailMary/) via
`.github/workflows/deploy.yml`. Docs and template-only changes are skipped by `paths-ignore`.
Pushing or merging to `main` publishes the site, so confirm with the user first.

## Content accuracy

This is a tribute, so getting the canon right matters more than anything else. Each claim needs a
source. Never invent quotes.

- Rocky has **no eyes**. Eridians sense by sound. Don't draw or describe eyes or "sensory organs".
- Rocky breathes **ammonia** (NH₃, about 29 atm), not "ammonium".
- The Hail Mary accelerates at **1.5 g**. The trip takes ~3.9 years aboard and ~13 years on Earth.
- Eva Stratt **heads** Project Hail Mary on Earth; she is not the mission commander.
- Tau Ceti has **candidate** exoplanets, not confirmed ones.
- The film opened in theaters on **March 20, 2026**. It was directed by Phil Lord & Christopher
  Miller, stars Ryan Gosling and Sandra Hüller (Stratt), and has a screenplay by Drew Goddard.
- Quotes in the Quotes section are verified against the book (see the Goodreads quotes page).
- Keep the plot spoiler-light. Don't reveal the ending.

## Code conventions

- Colors are CSS custom properties on `:root`. Reuse them rather than hard-coding new hex values.
- Use classes, not inline styles.
- Content marked `.reveal` fades in only when `<html class="js">` is set (added in `<head>`), so
  the page still works without JavaScript.
- Respect `prefers-reduced-motion`. The CSS media query disables animations, and the JS checks
  `reduceMotion.matches` for the star field and note particles.
- Mark decorative emoji and graphics `aria-hidden="true"`.
- Rocky's limbs are one shape (`#rk-limb-shape` in `<defs>`) drawn five times with `<use>`
  rotations. Edit the shape once.

## Testing

Serve with `python3 -m http.server 8000`, then check widths of 375px and 1280px. There should be
no sideways scroll and every nav link should be visible. Test the "Hear Rocky Speak" button, and
check that the stars twinkle.
