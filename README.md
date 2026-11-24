# HopeBridge

**Together We Build Brighter Communities**

HopeBridge is a static website for a community development organisation working in Sierra Leone. It connects supporters with local projects in four areas: **education, health, clean water and women's empowerment**. On the site, visitors can browse projects, check how much each one has raised, donate and apply to volunteer.

The site is plain HTML and CSS. It has no build step, no framework and no JavaScript.

---

## About

**Mission:** To work with communities in Sierra Leone on education, health, clean water and livelihoods, and to show supporters exactly how their help is used.

**Vision:** A Sierra Leone where every community has the tools and opportunities to thrive.

### Programme areas

| Programme | What it covers |
| --- | --- |
| **Education** | School libraries, school fees support and teacher training |
| **Health** | Mobile clinics, health talks and referrals for remote villages |
| **Clean water** | Boreholes and handwashing stations |
| **Women empowerment** | Savings groups, business training and mentoring |

---

## Built with

- **HTML5:** semantic, multi-page markup
- **CSS3:** one shared stylesheet using CSS custom properties, Flexbox and Grid

---

## Features

- **Project discovery:** search and filter projects by cause, region, status and funding need
- **Funding progress:** every project card shows a progress bar, the amount raised and the goal
- **Donation flow:** preset amounts in Leones (Le), with card, mobile money and bank transfer options
- **Volunteer portal:** registration, an application form and a dashboard of upcoming activities
- **Responsive design:** works on mobile, tablet and desktop, with a CSS-only hamburger menu
- **Lightweight:** no JavaScript, so pages load fast

---

## Pages

| Page | File | Purpose |
| --- | --- | --- |
| Home | `index.html` | Hero, project search, impact stats, featured projects, focus areas and a call to action |
| Projects | `projects.html` | All projects, with filters for cause, region, status and funding need |
| Project details | `project-details.html` | A single project page (currently *Girls' School Library*) |
| Programmes | `programmes.html` | The four programme areas, each with a photo and a link to its projects |
| About | `about.html` | Mission, vision, ways to help and an accountability section |
| Contact | `contact.html` | Contact details and a message form |
| Donate | `donate.html` | Donation form: choose a project, an amount in Leones (Le) and a payment method |
| Get involved | `get-involved.html` | Sign-in and registration for volunteers |
| Volunteer application | `apply.html` | Volunteer application form (district, interests, availability, skills) |
| Volunteer dashboard | `dashboard.html` | Application status and upcoming volunteer activities |
| Thank you | `thank-you.html` | Confirmation page shown after a donation or a contact message |

### How the pages connect

```
index ──search──▶ projects ──▶ project-details ──▶ donate ──▶ thank-you
                                                   contact ──▶ thank-you
get-involved ──sign in──▶ dashboard
             └─register─▶ apply ──▶ dashboard
```

---

## Project structure

```
HopeBridge/
├── index.html
├── projects.html
├── project-details.html
├── programmes.html
├── about.html
├── contact.html
├── donate.html
├── get-involved.html
├── apply.html
├── dashboard.html
├── thank-you.html
├── style.css          # One shared stylesheet for every page
└── images/
    ├── hero.jpg
    ├── about.jpg
    ├── girls-school-library.jpg
    ├── programme-education.jpg
    ├── programme-health.jpg
    ├── programme-water.jpg
    ├── programme-women.jpg
    ├── project-borehole.jpg
    ├── project-clinic.jpg
    ├── project-fees.jpg
    ├── project-handwashing.jpg
    └── project-women.jpg
```

---

## Getting started

No installation is needed. You only need a modern web browser.

**Open it directly:** double-click `index.html` to open it in any browser.

**Or run a local server** (recommended, because links and forms then behave as they would on a real host):

```bash
cd HopeBridge
python3 -m http.server 8000
# then visit http://localhost:8000
```

You can also use VS Code's **Live Server** extension or `npx serve`.

### Deploying

Since the site is static, any static host will work:

- **GitHub Pages:** push the repository, go to *Settings → Pages* and choose the branch to publish.
- **Netlify:** drag and drop the `HopeBridge` folder onto the Netlify dashboard.
- **Vercel / Cloudflare Pages:** import the repository. No build command is needed.

`index.html` is the entry page.

---

## Design

The colours are set as CSS custom properties at the top of `style.css`:

| Token | Value | Used for |
| --- | --- | --- |
| `--green` | `#146B3A` | Primary brand colour, buttons |
| `--green-d` | `#0C4A28` | Headings, hover states |
| `--gold` | `#F2B33D` | Donate buttons, focus outlines, logo accent |
| `--blue` | `#0B4F8A` | Links |
| `--ink` | `#1B2A22` | Body text |
| `--muted` | `#51605A` | Secondary text |
| `--bg` | `#F7F9F6` | Page background |

- **Typography:** Georgia (serif) for headings and the system UI font stack for body text.
- **Logo:** an inline SVG of a bridge in a green circle.
- **Responsive layout:** breakpoints at 900px, 700px and 560px. On small screens the menu becomes a hamburger, built with a CSS-only checkbox toggle.

### Accessibility

- A "Skip to content" link on every page
- Semantic landmarks (`header`, `nav`, `main`, `footer`) and `aria-current` on the active nav link
- Visible gold focus outlines
- Funding progress uses `<progress>` elements with `aria-label`s
- Descriptive `alt` text on all photos
- Respects `prefers-reduced-motion`

### Browser support

Works in the latest versions of Chrome, Firefox, Edge and Safari (macOS and iOS).

---

## Current limitations and to-do

This is a **front-end prototype**. There is no back end yet, so none of the forms process data. They only link from one page to the next.

- [ ] **Forms use `method="get"`.** Everything entered, including **passwords** on `get-involved.html`, ends up in the page URL. Switch to `POST` when you connect a back end.
- [ ] **No real payments.** The donate form needs a payment provider (card, mobile money, bank transfer).
- [ ] **No real accounts.** Volunteer sign-in, registration and the dashboard are static mock-ups.
- [ ] **Project filters don't filter yet.** `projects.html` always shows the same six projects.
- [ ] **Only one project-details page.** Each project needs its own page, or a template filled from data.
- [ ] **Placeholder content to replace before launch:**
  - Impact stats (12,400 people reached, 38 projects and so on)
  - Contact details (`hello@hopebridge.example`, `+232 00 000 000`)
  - The registration number, annual reports and team/partners on the About page
  - The Privacy and Terms links (these currently point to `#main`)
- [ ] **Images are AI-generated illustrations.** Swap in real project photos when you have them.

---

## Contributing

1. Fork the repository.
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push the branch: `git push origin feature/your-feature`
5. Open a pull request.

---

## Licence

© 2026 HopeBridge. All rights reserved.
