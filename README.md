# BelResumé

***A beautiful, modern, and minimal single-page resume site***

Powered by [Zola](https://getzola.org/). Styled with Tailwind CSS & Font Awesome

> “Bel” in French means beautiful — this is your beautiful resumé!

## Preview

[BelResumé](https://cx48.github.io/BelResume/) can be deployed for free using GitHub Pages or Vercel

#### Light Mode

![Light Mode](https://raw.githubusercontent.com/cx48/BelResume/refs/heads/main/static/images/light.png)

#### Dark Mode

![Dark Mode](https://raw.githubusercontent.com/cx48/BelResume/refs/heads/main/static/images/dark.png)

#### PageSpeed Insights

![PageSpeed](https://raw.githubusercontent.com/cx48/BelResume/refs/heads/main/static/images/pagespeed.png)

## Project Structure

- **config.toml**: Site metadata  
- **static/**: `css/style.css`, `js/script.js`  
- **templates/index.html**: Main layout (calls all partials)  
- **content/**: All resume sections are generated from easily readable files
  - `header.toml`: Name, job title, about, contact links
  - `experience.toml`: Work history (companies, roles, achievements)
  - `education.toml`: Schools, degrees, specializations
  - `projects.toml`: Key project summaries with tags
  - `skills.toml`: Visual skill bars (adjust widths)
  - `certifications.toml`: Cert title + authority + year
  - `languages.toml`: Language proficiency (bars & labels)
  - TODO: `awards.toml`: Award names + year + issuer

## Quick Start

1. **Install Zola**: [https://getzola.org/documentation/getting-started/installation/](https://getzola.org/documentation/getting-started/installation/) 

2. **Clone repository**:
   ```bash
   git clone https://github.com/andrescoit/Resume
   cd Resume
   ```

3. **Serve locally**:
   ```bash
   zola serve
   ```

   After making necessary changes to TOML files present under `content/` visit [http://127.0.0.1:1111](http://127.0.0.1:1111)

4. **Build static site**:
   ```bash
   zola build
   ```
   All files output to `/public`

## Deployment Guide

> Deploy to GitHub Pages

1. Run Zola build:
   ```bash
   zola build
   ```

2. Commit and push the contents of the `public/` folder to your `gh-pages` branch

3. In GitHub repo settings, enable Pages from the `/public` folder or `gh-pages` branch

4. Your site will be live at `https://yourusername.github.io/Resume/`

> Deploy to Vercel

1. Login to [Vercel](https://vercel.com) and import your GitHub repo

2. Set **Build Command** to:
   ```bash
   zola build
   ```

3. Set **Output Directory** to:
   ```bash
   public
   ```

4. Set **Framework Preset** to `Other`

5. Click **Deploy**

Zola will build and serve from the `public/` folder automatically on every push

## Customization Guide

To update your resume, simply open the required HTML file under `partials/` and modify it as per your requirement

### 1. **config.toml**  
Update site-wide metadata:
```toml
title = "John Doe"
description = "Senior Software Engineer"
base_url = "https://yourdomain.com"
```

### 2. **content/header.toml**
Edit your name, role, email, phone, location, LinkedIn link. Example:
```toml
name="First Last"
title="Highly accomplished senior professional with great soft skills."
about="Motivated and motivational CEO and nobel laureate with over 300 years of experience building value and drinking coffee."
email="user12345@aol.com"
location="Earth"
linkedin="linkedin.com/in/404.html"
```

### 3. **content/experience.toml**
Replace job titles, companies, durations, and bullet points. repeat `[[items]]` for each entry.
```toml
[[items]]
position="Chief Executive Officer"
date="1725 - Present"
employer="Boston Brewing & Beverage Research"
description="World leader of beans and hops."
bullets=[
    "invented coffee",
    "invented chocolate cake",
    "invented coffee brown ale"
]
```

### 4. **content/education.toml**
List your degrees, schools, GPA or honors:
```toml
[[items]]
degree="Doctor of Coffee Science"
date="1715 - 1725"
school="Harvard University — GPA: 3.9"
description="Graduated with honors. Founding member of First to Go & Graduate. President of Advanced Coffee Research Laboratory."
[[items]]
degree="Master of Beans Administration"
date="1712 - 1715"
school="Yale University - GPA: 3.8"
description="Magna cum laude, Dean's list. Invented coffee and coffee brown ale. Research industry trends and performed cross-functional collaboration to provide strategic recommendations for several lucrative performance markets, resulting in a 5% reduction in financial visibility and 100% accuracy."
```

### 5. **content/projects.toml**
List project names, stacks used, short descriptions.
```toml
[[items]]
title="Equine-commerce Platform"
description="Leveraging emerging self-driving horse technology to bring products to market."
tags=["AOL","B2B","C2C","D&D"]
url="http://e-commerce.geocities.com"
```

**TODO:**

### 6. **content/skills.toml**
Update skill bars by adjusting the width in `style="width: 90%"`.
```html
<h3>JavaScript</h3>
<div class="progress" style="width: 95%"></div>
```

### 7. **content/certifications.toml**
List certificates with name, organization, and date:
```html
<h3>AWS Certified Architect</h3>
<p>Amazon – 2022</p>
```

### 8. **content/languages.toml**
Change language names, levels, and progress widths:
```html
<span>English</span> <span>Native</span>
<div style="width: 100%"></div>
```

### 9. **content/awards.toml**
Highlight awards with name and source:
```html
<h3>Best Hackathon Project</h3>
<p>DefCon 2025</p>
```
