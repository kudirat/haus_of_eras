# Haus of Eras

Haus of Eras is a static portfolio site for showcasing creative work and collecting contact inquiries.

## Tech Stack

- HTML for the pages and contact form
- CSS for layout, styling, and responsive rules
- Google Fonts for the Big Shoulders typeface
- Formspree for processing contact form submissions
- GitHub Pages as the configured hosting destination

There is no application framework, JavaScript bundle, backend server, or package manager in the current project. The page artwork and portfolio images are stored in `site-files/landing/`.

## Pages

- `index.html` is the portfolio homepage and contact form.
- `thanks.html` is the form's post-submission confirmation page.
- `coming-soon.html` is used for the Work, Studio, and Services navigation links.

## Contact Form and Formspree

The contact form in `index.html` uses a regular HTML form submission; the browser sends the form directly to Formspree. No custom JavaScript or server-side form handler is needed.

1. Create a form in the Formspree dashboard and complete any email verification it requests.
2. Copy the form endpoint provided by Formspree. Replace `xyzabcde` in the form's `action` URL with the actual form ID, so the URL has the form `https://formspree.io/f/YOUR_FORM_ID`.
3. Confirm the `_next` hidden field points to the published `thanks.html` URL. Its current value is `https://kudirat.github.io/haus_of_eras/thanks.html`.
4. Publish the site and submit a test inquiry. Confirm it appears in Formspree and reaches the configured recipient.

The form sends `firstName`, `lastName`, and `email` as required fields, plus optional `phone`, `service`, and `message` fields. The submit button sends the form using HTTP `POST`. Formspree handles the submission and, on success, the `_next` value directs the visitor to the confirmation page.

**Important:** The current endpoint ID, `xyzabcde`, looks like a placeholder. The contact form will not reach the intended Formspree form until it is replaced with the real ID from the dashboard. If the published site URL changes, update `_next` as well.

## Run Locally

Open `index.html` directly in a browser to view the site. To check the complete deployed form flow, use the published site and a valid Formspree endpoint; local file previews are not a substitute for testing the hosted submission and redirect.