# Dr. Mohd Rafiq – Academic Resume

A responsive, single-page academic resume website for **Dr. Mohd Rafiq**. The site presents academic qualifications, professional experience, awards, research publications, workshops and conferences, computer skills, and other academic activities.

## Features

- **Profile header** with name, email address, location, and profile photograph.
- **Section navigation** with links to key parts of the resume.
- **Career objective** and areas of specialization.
- **Education** presented in a structured table.
- **Professional experience** and **national awards** displayed as lists.
- **Research articles** with DOI links.
- **Seminars, workshops, and conferences** attended or presented.
- **Computer skills** with animated skill-level bars.
- **Academic certificates** and extracurricular achievements.
- **Responsive layout** for desktop and smaller screens.
- **Smooth scrolling**, hover effects, and subtle entrance animations.

## Technologies Used

- HTML5
- CSS3 (custom properties, Flexbox, Grid, media queries, and animations)
- JavaScript (Intersection Observer API and smooth-scroll navigation)
- [Google Fonts](https://fonts.google.com/) – Neuton, PT Serif, and Trirong
- [Font Awesome 6.4.0](https://fontawesome.com/) – icons
- [cdnjs](https://cdnjs.com/) – Font Awesome stylesheet CDN

## Project Structure

Keep the following files together in the project directory:

```text
academic-resume/
├── index.html       # Main resume webpage
├── favicon.ico      # Website favicon
└── README.md        # Project documentation
```

The profile photograph is currently loaded from an external image URL in `index.html`. An internet connection is therefore required to display that image and load the external fonts and icon stylesheet.

## Run Locally

No build tools or package installation are required.

1. Download or clone this repository.
2. Make sure `index.html` and `favicon.ico` are in the same directory.
3. Open `index.html` in a web browser.

For a local development server, you can also use the **Live Server** extension in Visual Studio Code.

## Deployment

### GitHub Pages

1. Push the project files to a GitHub repository.
2. Ensure the main HTML file is named `index.html` and is in the repository root (or the selected publishing folder).
3. Open the repository on GitHub.
4. Go to **Settings → Pages**.
5. Under **Build and deployment**, select **Deploy from a branch**.
6. Select the required branch (usually `main`) and folder (`/root`), then save.
7. Wait for GitHub Pages to publish the site. The published URL will be shown in the Pages settings.

## Customization

Edit `index.html` to update the resume content:

- **Personal details:** update the name, email, location, and profile image URL in the header.
- **Education and experience:** edit the corresponding table rows and list items.
- **Awards and publications:** update the relevant sections and DOI links.
- **Skills:** change the skill names and each `data-level` value (0–100) in the skill bars.
- **Colors and fonts:** adjust the CSS variables in the `:root` selector and the font imports.
- **Favicon:** replace `favicon.ico` with your own icon, keeping the same filename, or update the favicon path in the HTML.

When adding or removing a navigation section, make sure the navigation link's `href` matches the section's `id`.

## Notes

- The website is a static front-end project. It does not require a database, backend, or server-side application.
- The contact email uses a `mailto:` link.
- External resources (profile image, Google Fonts, and Font Awesome) may not load when offline.
- Review personal information and publication details before publishing the website publicly.

## License

No license is specified for this project. Add a `LICENSE` file if you intend to distribute the source code under a particular open-source license.
