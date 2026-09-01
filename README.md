# Personal web resume — Sahasawat Wittayaprasit

Static single page. No framework, no build step, no dependencies, no tracker.
Open `index.html` in a browser, or serve the folder.

Live at <https://sahasawatt.github.io/>.

## Files

| File | What it is |
|---|---|
| `index.html` | The page. All content lives here, including the 200-mark SVG field. |
| `tokens.css` | The design system: colour, type, spacing, motion. |
| `styles.css` | Layout and component rules. Consumes `tokens.css` by name — no raw colour or font value appears outside the token block. |

## The design

Near-black ground, one warm amber accent, light-weight Geist display, two fixed radial blooms.

The centrepiece is **200 marks, one per 100 pay slips** — the field is the figure from the résumé
drawn to scale, and the caption states the unit so the encoding can be checked rather than taken
on trust.

Motion degrades safely. Elements are **visible by default**; the hidden state applies only once
the script has run, anything already on screen reveals synchronously, and a 2.5s timer reveals
everything regardless. If the script throws it removes its own `js` class and the page renders in
full. A blocked or failed script can never leave the page blank.

## Verified, not assumed

Every claim below was measured on the rendered page rather than eyeballed:

- **Contrast** — 20 text/background pairs computed against their effective background; worst is
  5.43:1 against a 4.5:1 floor.
- **No horizontal overflow** at 320 / 390 / 414 / 768 / 1280 / 1920 px, checked with a planted
  overflowing element first so the empty result is known to come from a working probe.
- **Line length** stays inside the 45–75 character band on every prose block at desktop widths.
- **Hero fits a 1280×800 fold** — the dot field and its caption are above the fold, not cut by it.
- **Degradation** — with the script disabled, 0 of 27 revealed elements and 0 of 200 marks stay
  hidden.

## Content provenance

Every figure comes from the résumé of record. Nothing was invented to fill a slot:

- `20,000` pay slips per cycle, `20+` enterprise tenants — Humanica
- `3+` years · `2` countries' payroll statute (Thailand and Vietnam) · `2` product generations
  (legacy Humatrix on ASP.NET C#, Workplaze on Go / React)

## Deliberately omitted

- **Phone number.** It is on the PDF; a public page gets scraped.
- **`og:url` / `og:image` / `canonical`** until the deployed URL is stable — a wrong canonical is
  worse than a missing one.
- **Analytics.** None.
