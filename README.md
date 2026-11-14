# INDIA XI — Cricket Match Centre

A responsive, GitHub Pages-ready website for India's **men's and women's cricket**. It has Live, Upcoming and Results views, plus gender and format filters.

## 1. Run it locally

Download/unzip this project and open `index.html` in a browser. For best results, use a local static server (for example VS Code Live Server).

## 2. Connect real match data

This project is wired to [OpenCricket API](https://opencricketapi.com/).

1. Create an account and generate an API key at https://opencricketapi.com/.
2. Open the website and click **SETUP**.
3. Paste your key and choose **Save & Load Matches**.

**Plan note:** OpenCricket's published documentation says the free Starter key includes archive matches from the last 12 months, but live scores and upcoming fixtures require the Developer plan. The site requests live matches, fixtures, and male/female India match history. See the provider's [API documentation](https://opencricketapi.com/docs) and [pricing](https://opencricketapi.com/).

## 3. Publish on GitHub Pages

1. Create a new GitHub repository, e.g. `india-cricket-match-centre`.
2. Upload all files and folders from this project to the repository root.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then Save.
6. Wait for the Pages URL to appear.

Every push to `main` will update the published site.

## Important security note

GitHub Pages is static hosting. The API key is stored in the visitor's browser `localStorage`; it is **not** stored in this repository, but it is still accessible to that browser user and can be seen in browser developer tools/network requests. Do not embed a private key in `app.js` or commit it to GitHub. For a public production website where visitors should not provide their own key, add a server-side proxy (Cloudflare Worker, for example) and keep the API key in that service's secret environment variables.

## Data and coverage

- Men's and women's teams are filtered separately.
- Live scores and fixtures depend on provider availability and plan access.
- Historical coverage depends on the provider's archive and the source's coverage.
- The page intentionally does not invent scores when the API is disconnected.
- OpenCricket documentation describes historical data from Cricsheet (ODC-By 1.0) and live/fixture data from ESPN's public scoreboard. Follow the provider's attribution/licensing requirements.

## Project files

- `index.html` — page structure and settings dialog
- `styles.css` — responsive dark-green visual design
- `app.js` — API requests, filters, rendering and refresh logic
- `.nojekyll` — tells GitHub Pages not to process the site with Jekyll
