# Neoma HR Consulting Website

A static HTML/CSS website for Neoma HR Consulting. No frameworks, no build step, no dependencies.

## What's in here

```
neoma-site/
├── index.html              Home page
├── about.html              About page
├── services.html           Services page
├── referral-circle.html    Referral Circle page
├── engagements.html        Engagements page (speaking, training, facilitation)
├── contact.html            Contact page
├── 404.html                Custom error page
├── CNAME                   Custom domain config for GitHub Pages
├── sitemap.xml             For search engines
├── robots.txt              For search engine crawlers
├── assets/
│   ├── styles.css          Shared stylesheet for all pages
│   └── images/
│       ├── adrienne-portrait.jpg    The about-page portrait
│       ├── favicon.svg              Vector favicon
│       ├── favicon-32.png           Standard favicon (32x32)
│       ├── favicon-180.png          Apple touch icon (180x180)
│       └── og-image.png             Social sharing card (1200x630)
└── README.md               This file
```

## Best practices already implemented

This site ships with:

- **Per-page title tags and meta descriptions** for search engines and browser tabs.
- **Open Graph and Twitter Card tags** so links to your site preview cleanly when shared on LinkedIn, in iMessage, or in email.
- **Favicon** in three formats so the three-moon mark appears in browser tabs, bookmarks, and home screens.
- **Schema.org structured data** on the home page identifying Neoma as a ProfessionalService with founder and location.
- **Canonical URLs** on every page to prevent duplicate-content issues.
- **A sitemap** for Google to find every page.
- **A robots.txt** allowing search engines to crawl the public site.
- **Skip-to-content link** for keyboard and screen reader users.
- **Visible focus states** on all interactive elements.
- **Main landmark** wrapping the main content of each page for screen readers.
- **Accessible labels** on form fields with autocomplete hints.
- **Honeypot anti-spam field** in the contact form to block automated bots.
- **Privacy notice** on the contact form explaining how submissions are used.
- **Custom 404 page** that matches the brand and links back to the home page.
- **Auto-updating copyright year** so the footer never goes stale.
- **Mobile responsive** with breakpoints tested down to 360px wide.
- **No external dependencies.** No fonts, no JavaScript libraries, no third-party trackers.

## Before you deploy: two things to do

### 1. Set up the contact form on Formspree

The contact form needs to be connected to a real submission handler. Free tier is fine for low volume.

1. Go to formspree.io and sign up using `neomahrconsulting@gmail.com`
2. Create a new form. Name it "Neoma Contact Form."
3. Set the destination email to `neomahrconsulting@gmail.com`
4. Formspree gives you a form endpoint that looks like `https://formspree.io/f/abcdwxyz`
5. Open `contact.html` and find the line `action="https://formspree.io/f/YOUR_FORM_ID"`
6. Replace `YOUR_FORM_ID` with the part after `/f/` in your endpoint
7. Save

The free Formspree plan allows 50 submissions per month. The honeypot field in the form will catch most spam bots automatically.

### 2. Confirm the email address

The site lists `hello@neomahr.com` as the contact email. Forwarding from your Namecheap dashboard is already set up. No further action needed.

## Deploying to GitHub Pages

GitHub Pages will host this site for free. About fifteen minutes of work.

### Step 1: Create the repository

1. Sign in to github.com (sign up if you haven't, use `neomahrconsulting@gmail.com`)
2. Click the green "New" button to create a new repository
3. Repository name: `neomahr.com` (or anything, this name is conventional)
4. Set it to **Public** (Pages requires this on free accounts)
5. Do not initialize with a README
6. Click "Create repository"

### Step 2: Upload the files

Use GitHub's web interface. It's the simplest path.

1. On the new repository page, click "uploading an existing file"
2. Drag everything from inside the `neoma-site` folder into the upload area (the files themselves, not the folder)
3. Wait for the upload to complete
4. Scroll down, write a commit message ("Initial site"), and click "Commit changes"

The CNAME file in this folder tells GitHub Pages your site lives at `neomahr.com`.

### Step 3: Turn on GitHub Pages

1. In the repository, click "Settings"
2. Scroll down the left sidebar to "Pages"
3. Under "Source," select "Deploy from a branch"
4. Under "Branch," select "main" and "/ (root)"
5. Click "Save"
6. Wait two to three minutes

GitHub will give you a URL. Open it. The site loads.

### Step 4: Point your domain at GitHub Pages

In your Namecheap dashboard:

1. Go to your domain `neomahr.com`
2. Click "Advanced DNS"
3. **Remove** the existing URL Redirect Record that points to `www.neomahr.com`
4. **Add** four new "A Record" entries, all with Host set to `@`:
   - Value: `185.199.108.153`
   - Value: `185.199.109.153`
   - Value: `185.199.110.153`
   - Value: `185.199.111.153`
5. **Add** one "CNAME Record":
   - Host: `www`, Value: `<your-github-username>.github.io`

DNS changes can take up to 24 hours but usually work within an hour. Once they propagate, `neomahr.com` shows the site.

### Step 5: Enable HTTPS

After DNS resolves:

1. Go back to GitHub Settings → Pages
2. Check "Enforce HTTPS" once available (takes 10-30 minutes after DNS propagation)
3. The site is now served over HTTPS, which is required for modern browsers and Google ranking

## Making changes later

The most common change is copy. To update text:

1. Open the relevant `.html` file in any text editor (VS Code, Sublime, Notepad)
2. Find the text between the HTML tags
3. Edit and save
4. Upload the changed file to GitHub, or commit through Git
5. The live site updates within a minute

For visual changes (colors, fonts, spacing), edit `assets/styles.css`. The brand colors are defined as CSS variables at the top of the file, so changing the gold color, for example, only requires editing one line.

## What's not built (saved for later)

- **Analytics.** No tracking installed. Plausible (privacy-respecting, ten dollars a month) or Google Analytics (free, more invasive) can be added when needed.
- **Custom serif font.** The site uses Georgia, a system font. A Google Font like Cormorant Garamond would elevate it. One-line addition when ready.
- **Phone number on the contact page.** Not displayed. Add if you want to be reachable by phone.

## Brand reference

If a designer or developer ever needs to extend this site:

**Colors**
- Navy background: `#16223F`
- Navy light (alternating sections): `#1B2A4E`
- Gold (accent): `#C9A24A`
- Moonlight blue (tagline, soft text): `#B6C2DC`
- Stone gray (middle moon): `#8A93A6`
- Stone dark (first moon outline): `#6E7A95`
- White: `#FFFFFF`

**Typography**
- Serif (headlines, wordmark): Georgia
- Sans (body, navigation): System sans-serif stack
