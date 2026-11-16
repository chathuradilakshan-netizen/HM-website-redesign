<h1 align="center">⚛ HM Physics</h1>

<p align="center">
  <strong>A New Dimension of Physics</strong><br>
  A cinematic, interactive website for A/L Physics education.<br>
  Built around curiosity, clear information, and hands-on discovery.
</p>

<p align="center">
  <img alt="HTML5" src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&amp;logo=html5&amp;logoColor=white">
  <img alt="CSS3" src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&amp;logo=css&amp;logoColor=white">
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&amp;logo=javascript&amp;logoColor=black">
  <img alt="Canvas 2D" src="https://img.shields.io/badge/Canvas_2D-30343B?style=flat-square">
</p>

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#quick-start">Quick start</a> ·
  <a href="#project-structure">Project structure</a> ·
  <a href="#physics-labs">Physics labs</a> ·
  <a href="#deployment">Deployment</a>
</p>

---

## Overview

HM Physics reimagines the online experience for **Harsha Mahamalage's A/L Physics classes in Sri Lanka**. It combines an animated science-inspired interface with practical class information, an authentic teacher profile, and experiments visitors can control directly in the browser.

The project is a static front end built with HTML, CSS, and vanilla JavaScript. Its spatial scenes use mathematical 3D projection rendered through the **Canvas 2D API**. No JavaScript framework, package installation, or build step is required to run the supplied website.

The student portal opens the existing HM Physics LMS. Accounts, payments, enrolment records, and an admin dashboard are outside the supplied front end.

## Features

- **Cinematic homepage:** an animated atom, luminous orbit paths, moving electrons, floating equations, and pointer-responsive perspective.
- **Scroll-driven storytelling:** transitions through mechanics, waves, and electric fields, with rotating and morphing scientific illustrations.
- **Three interactive physics labs:** adjust variables and see wave behaviour, projectile trajectories, and electric fields respond.
- **Teacher profile:** Harsha Mahamalage's portrait, qualifications, and teaching background.
- **Class discovery:** switch between the included 2027 and 2026 A/L schedules and open enquiries tailored to the selected year and location.
- **Useful connections:** access the official student portal, timetable, results, events, WhatsApp, email, and telephone contacts.
- **Responsive navigation:** desktop links, a mobile menu, section anchors, and a reading-progress indicator.
- **Motion controls:** pause page animation, pause or reset applicable experiments, and respect the visitor's reduced-motion preference.

## Technology

| Technology | Role |
| --- | --- |
| HTML5 | Semantic page sections, navigation, forms, and accessible controls |
| CSS3 | Responsive layouts, animation, typography, gradients, and visual effects |
| Vanilla JavaScript | Interaction logic, simulation calculations, and scroll behaviour |
| Canvas 2D | Perspective-projected scenes and live experiment drawings |
| Browser observers | Reveal effects, canvas resizing, and visibility-aware drawing |
| Embedded assets | Fonts, teacher portrait, and favicon packaged with the website |

## Quick start

These instructions assume the contents of the supplied website folder are placed at the repository root. If they are inside a nested `HM-Physics-Purple` folder, open that folder before running the commands below.

### View the website immediately

Open the root **`index.html`** in a modern browser. This is the self-contained edition: its styling, JavaScript, fonts, and image are embedded.

The page, animations, and experiments can run offline. Links to the student portal, official website, WhatsApp, and other external services require internet access.

### Work with the editable source

Open **`source/index.html`** to use the separated HTML, CSS, and JavaScript files. Keep all three source files together.

A local server is useful while developing. With Python 3 installed, run this from the project root:

```bash
python -m http.server 8000 --bind 127.0.0.1
```

Use `python3` instead of `python` if that is your system's Python 3 command. Then open:

- **Standalone edition:** <http://127.0.0.1:8000/>
- **Editable edition:** <http://127.0.0.1:8000/source/>

Stop the server with `Ctrl+C`.

> **Source and standalone editions are separate files.** Editing `source/` does not automatically rebuild the root `index.html`. Deploy the edited source files together, or regenerate the standalone edition before publishing it. This package does not include an automatic bundling script.

## Project structure

| Path | Purpose |
| --- | --- |
| `README.md` | Project documentation |
| `index.html` | Self-contained website for previewing or deployment |
| `source/index.html` | Editable page content, markup, and embedded portrait |
| `source/style.css` | Responsive styles, typography, embedded fonts, and animation |
| `source/script.js` | Navigation, scrolling, canvas rendering, and physics calculations |
| `README.txt` | Original package instructions and delivery notes |
| `COLOURS.md` | Visual-design reference supplied with the package |

## Physics labs

| Experiment | Adjustable controls | Calculated outputs |
| --- | --- | --- |
| **Wave lab** | Frequency, amplitude, travelling/standing mode | Wavelength, wave speed, period |
| **Projectile motion** | Launch speed and angle | Horizontal range, maximum height, flight time |
| **Electric field** | Two signed charges, dipole/like-charge presets | Field magnitude and horizontal/vertical components at a fixed probe |

### Wave model

Travelling waves use `y = A sin(kx − ωt)`. Standing waves use `y = A sin(kx) cos(ωt)`, where `A` is the maximum antinode displacement.

The wave speed is fixed at **2 m/s**; `λ = v/f` and `T = 1/f`. For the standing-wave mode, that speed refers to the constituent travelling waves.

### Projectile model

The simulation assumes uniform gravity of **9.81 m/s²**, no air resistance, and equal launch and landing heights. Range follows `R = v₀² sin(2θ)/g`.

### Electric-field model

The field is calculated by superposing the contributions of two point charges in vacuum. Charges are entered in **nanocoulombs**, positioned at `(-0.9, 0)` m and `(0.9, 0)` m. The probe measures the field at `(0, 1)` m.

Field-arrow lengths are compressed for readability. Numerical readouts use SI units.

The labs are idealised learning demonstrations. The decorative atom and scrolling scenes are conceptual illustrations rather than quantum orbital models.

## Editing guide

| Change | Where to work |
| --- | --- |
| Headings, biography, navigation, and contact links | `source/index.html` |
| Page layout, typography, and animation styling | `source/style.css` |
| Class-year switching and enquiry messages | `selectYear()` in `source/script.js` |
| Experiment values and displayed measurements | Physics helpers and `updateLab()` in `source/script.js` |
| Hero atom and scrolling scientific scenes | `drawAtom()` and `drawUniverse()` in `source/script.js` |
| Wave, projectile, and field drawings | `drawWave()`, `drawProjectile()`, and `drawField()` in `source/script.js` |

Class information is stored in the page and JavaScript. Update both the initial HTML values and the year-selection logic when changing the timetable. A content-management integration can be added if the class team needs to manage these details through an admin interface.

## Accessibility and performance

The implementation includes a skip link, labelled range controls, keyboard-operated experiment tabs, visible focus styles, native FAQ disclosures, mobile-menu state announcements, and reduced-motion support.

Canvas rendering uses `requestAnimationFrame`. The code checks document visibility, avoids drawing off-screen canvases when visibility information is available, and caps the rendering pixel ratio to limit drawing work on high-density displays.

## Validation

For an optional JavaScript syntax check, with Node.js installed:

```bash
node --check source/script.js
```

The supplied package does not include an automated test suite. Before publishing a change, check:

- Desktop and mobile layouts, including the portrait, navigation, and overflow.
- All three experiments, sliders, presets, and pause/reset controls.
- Keyboard navigation and reduced-motion behaviour.
- Class-year switching, class enquiries, and external destinations.
- The standalone edition if it was regenerated.

## Deployment

### Existing hosting or another static host

Choose the edition you intend to maintain:

| Edition | Files to publish | Build step |
| --- | --- | --- |
| Standalone | Root `index.html` | None |
| Editable source | The contents of `source/`, with its `index.html` at the public root | None |

Use a private staging deployment for review before replacing the production homepage. Keep the existing LMS and any required `/schedule`, `/results`, `/events`, and `/contact-us` routes available. Confirm current class information and remove preview-only wording before an approved public release.

### GitHub Pages

For an approved public deployment, if GitHub Pages is available for the repository:

1. Place the standalone `index.html` at the root of the publishing branch.
2. Open **Settings → Pages** in the repository.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the publishing branch and **`/(root)`**, then save.
5. Use the deployment URL shown by GitHub and verify the page.

Branch-based publishing supports the repository root or a `/docs` directory. To publish the editable edition this way, place its three files together in the chosen publishing directory. A GitHub Actions workflow can also publish `source/` as an artifact.

Pages availability depends on the account plan and repository visibility. A private repository does not by itself make the published website private. See the [official GitHub Pages configuration guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Contributing

Keep changes focused and describe the intended result in the pull request. Include desktop and mobile screenshots for visual changes, and explain how any changed simulation was checked. Preserve keyboard access, motion controls, and the distinction between decorative illustrations and quantitative experiments.

## Credits and references

- **Project maintainer:** [Chathura Dilakshan](https://github.com/chathuradilakshan-netizen).
- **Repository:** [HM-website-redesign](https://github.com/chathuradilakshan-netizen/HM-website-redesign).
- **Educational identity and source material:** [HM Physics / Harsha Mahamalage](https://mahamalage.com/).
- **Teacher biography:** [Official teacher information](https://mahamalage.com/contact-us).
- **Class information:** [Official timetable](https://mahamalage.com/schedule).
- **Existing learning platform:** [HM Physics LMS](https://lms.mahamalage.com/).
- **Embedded typefaces:** Manrope and Space Grotesk.

## License

A project-wide software license has not been supplied with this package. The maintainer should specify the intended terms in a `LICENSE` file before presenting the project as open source. Teacher imagery, branding, written content, and embedded fonts remain subject to their respective permissions and licenses.

---

<p align="center"><strong>Observe. Question. Experiment.</strong></p>
