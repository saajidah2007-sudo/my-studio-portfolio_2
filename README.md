# Saajidah Abrahams — Developer Portfolio

A responsive, single-page Vue 3 portfolio styled as a modern photo-booth album. The project uses Vue 3 and Vite, with plain CSS and no router or extra UI dependencies.

## Run locally

1. Install Node.js (a current LTS release).
2. From this project folder, run:

   ```sh
   npm.cmd install
   npm.cmd run dev
   ```

3. Open the local URL printed by Vite (usually `http://localhost:5173`).

To verify a production build:

```sh
npm.cmd run build
npm.cmd run preview
```

On Windows PowerShell, use the `.cmd` form shown above if script execution policy blocks `npm`.

## Where to make updates

- Edit the six project descriptions, categories, confirmed technologies, and any real GitHub/demo links in `src/data/projects.js`. Links are intentionally empty until supplied.
- Replace `public/images/profile/portrait-strip.svg` with a real portrait-strip image when you have one. Keep the same path or update `HeroSection.vue`.
- Project covers are CSS-built visual studies, not screenshots of the actual projects. Replace them with real screenshots as they become available; the visual studies clearly identify themselves as placeholders.
- Add your email to the `email` ref in `src/components/ContactSection.vue`. The contact button copies the configured address. No personal email or professional profile links were provided, so none have been fabricated.
- Adjust the shared color, spacing, type, and radius tokens in `src/assets/styles/variables.css`; shared layout and responsive styles are in `src/assets/styles/main.css`.

## Structure

```text
my-studio-portfolio/
├── public/
│   └── images/
│       └── profile/
│           └── portrait-strip.svg         Replaceable photo-strip illustration
├── src/
│   ├── assets/
│   │   └── styles/
│   │       ├── main.css                   Global styles, responsive layout and motion
│   │       └── variables.css              Shared design tokens
│   ├── components/
│   │   ├── AboutSection.vue
│   │   ├── ContactSection.vue
│   │   ├── HeroSection.vue
│   │   ├── ProjectArtwork.vue
│   │   ├── ProjectCard.vue
│   │   ├── ProjectDetails.vue
│   │   ├── ProjectGallery.vue
│   │   ├── SiteFooter.vue
│   │   ├── SiteNavigation.vue
│   │   └── TechnicalSkills.vue
│   ├── data/
│   │   └── projects.js                    Project content and verified links
│   ├── App.vue                            Continuous page and active-section tracking
│   └── main.js                            Vue entry point and stylesheet imports
├── index.html                              Page metadata and app mount point
├── package.json                            Dependencies and scripts
├── package-lock.json                       Locked dependency versions
├── vite.config.js                           Vite + Vue configuration
├── .gitignore                               Ignores dependencies and build output
└── README.md                                Setup, updates and testing checklist
```

## Quality checklist

- [ ] Check the layout at 1440px, 768px, and 375px.
- [ ] Use every navigation link and the hero calls to action.
- [ ] Open a project with the keyboard and mouse; close its details with Escape, the close button, or the backdrop.
- [ ] Confirm there is no horizontal overflow and reduced-motion settings are respected.
- [ ] Add real project screenshots, verified links, and an email address before publishing.
