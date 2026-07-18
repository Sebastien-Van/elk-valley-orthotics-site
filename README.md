# Elk Valley Orthotics — Website

A static site (plain HTML/CSS/JS, no build step) for Elk Valley Orthotics, with an
embedded Jane App booking calendar.

## Before you go live — 3 things to swap in

1. **Jane App URL** — in `book.html`, replace `https://elkvalleyorthotics.janeapp.com`
   (in both the iframe `src` and the "Open in a new tab" link) with your clinic's
   actual Jane App booking URL. Also update the same placeholder link in `index.html`
   if you add one there.
2. **Contact form** — `contact.html` posts to Formspree (a free service that emails
   form submissions to you with no backend required). Go to
   [formspree.io](https://formspree.io), create a free account, create a form, and
   replace `YOUR_FORM_ID` in the form's `action` attribute with the ID they give you.
3. **Real photos** — the mountain/trail/team photos currently pull from Unsplash
   (free stock photography) as placeholders. Replace the `src` attributes in
   `index.html` and `about.html` with your own clinic and location photos once you
   have them, and drop the image files into the `images/` folder.

## Project structure

```
elk-valley-orthotics/
├── index.html        Homepage
├── about.html         About / team
├── services.html       Services list
├── contact.html         Contact form + map
├── book.html             Jane App booking embed
├── css/style.css
├── js/main.js
└── images/
    ├── logo-mark.png    (icon-only logo, transparent background)
    └── logo-full.png    (logo with wordmark, transparent background)
```

## Running locally

No build tools needed — just open `index.html` in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying (GitHub + Netlify)

See the deployment walkthrough provided separately, or in short:

1. Push this folder to a new GitHub repository.
2. Create a free Netlify account, import the repo, leave build settings blank,
   publish directory `/`.
3. In Netlify: Site settings → Domain management → add `elkvalleyorthotics.ca`.
4. In Namecheap: Advanced DNS → add the A record + CNAME Netlify gives you
   (leave your existing MX/TXT email records untouched).
5. Netlify auto-issues a free HTTPS certificate once DNS resolves.
