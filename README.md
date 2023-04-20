# A checklist for all projects that are going live at RETINENS
Based on https://github.com/spatie/checklist-going-live 

## 1. Test on Desktop and mobile
- [ ] Desktop
- [ ] Mobile

## 2. Front end checklist

### Assets
- [ ] Search sources for `http://`. Replace by `https://`
- [ ] Check everything is compiling `npm run prod-all`
- [ ] Webfonts: is the live domain configured in services like Fontawesome ?

### Scripts
- [ ] Check JS errors. Remove all `console.log` lines in scripts
- [ ] Check for console errors

### Page weight
- [ ] Evaluate total weight of at least homepage (GTMetrix)
- [ ] Open Inspector network/timeline tab to identify heavy assets (CSS, JS or images)
- [ ] Check if heavy assets are cached
- [ ] Are the images optimized and well-sized ?

### Audits
- [ ] Use the Chrome DevTools (in incognito mode) and perform a mobile audit (with throttling) to fix common problems.
- [ ] Repeat with a desktop audit.
- [ ] Page speed insight audit
- [ ] Run PageSpeed Insights

## 3. Check content (with an open console)
- [ ] Are all strings / images present (and translated)?
- [ ] Does menu/submenu have a correct active state on every page?
- [ ] Are custom 404, 500 and 503 pages provided? Do they provide useful content like 'back to home', search or a navigation tree?
- [ ] Check all pages for n+1 problems

### Meta/SEO
- [ ] Check default values in `config/seotools.php`
- [ ] Check page titles / descriptions on every page 
- [ ] Test Facebook / Twitter sharing. 
- [ ] Does the Favicon load? Pin the tab in Safari to check pinned icon
- [ ] Is a theme color defined in the HTML header ?

_Repeat this section for all languages_

### Components

- [ ] Forms: fill out with wrong/right values
- [ ] Video: check with sound on
- [ ] Try subscribing to a newsletter with incorrect & correct email (use correct mail twice to get 'already subscribed' message)
- [ ] Check layout of emails
- [ ] Check email styling
- [ ] Check structured data for news, events, products,... https://search.google.com/structured-data/testing-tool/

## 4. Back end checklist
- [ ] Create a new admin and try to log in
- [ ] Try the password reset flow for existing user
- [ ] Verify all e-mail recipients are correct (for contact emails)
- [ ] Scan database for urls to development domain

## 5. Server, DNS & Services
- [ ] Add redirects from old to new pages if necessary (`routes/redirect.php`)
- [ ] Install Let's Encrypt certificate
- [ ] Check SSL certificate health https://www.ssllabs.com/ssltest/
- [ ] Try visiting `www` domain, should redirect to `non-www`
- [ ] Try out visiting `http`, should redirect to `https`
- [ ] Verify that indexing is not prohibited with `x-robots-tag: none` by checking `curl -I https://url | grep 'x-robots-tag'`. Allow robots in `.env`
- [ ] Check dns propagation with https://www.whatsmydns.net/
- [ ] Verify Tag Manager / Analytics have been correctly set up

### Google Search Console
- [ ] Submit all www/non-www http/https variations
- [ ] Set up non-www https as the preferred domain 
- [ ] Crawl > Fetch as Google > Submit to index to kickstart index

### Server
- [ ] Are DigitalOcean backups enabled?
- [ ] Is the output of artisan task `backup:run` ok?
- [ ] Is artisan scheduled on Ploi?
- [ ] Is Horizon configured in Supervisor on Ploi?
- [ ] Is the database backed up on Ploi ?
