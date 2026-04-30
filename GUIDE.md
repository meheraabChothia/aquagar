# Blog Guide

## How We Set This Up

1. Created a new repo from the Chirpy starter template at `https://github.com/cotes2020/chirpy-starter`, named `meheraabChothia.github.io` (later renamed to `aquagar`)
2. Cloned the repo locally
3. Installed Ruby: `sudo apt install ruby-full build-essential zlib1g-dev`
4. Configured gem path in `~/.bashrc`:
   ```
   export GEM_HOME="$HOME/gems"
   export PATH="$HOME/gems/bin:$PATH"
   ```
5. Installed Jekyll and Bundler: `gem install jekyll bundler`
6. Installed project dependencies: `bundle install`
7. On GitHub: Settings → Pages → Source → set to **GitHub Actions**
8. Renamed repo to `aquagar` and updated `_config.yml` with `baseurl: "/aquagar"`

---

## Running Locally

```bash
bundle exec jekyll serve
```

Visit `http://127.0.0.1:4000/aquagar` to preview (the `/aquagar` suffix is due to the `baseurl` setting).

---

## Adding a New Post

1. Create a file in `_posts/` named: `YYYY-MM-DD-your-post-title.md`
2. Add this front matter at the top:
   ```yaml
   ---
   title: Your Post Title
   date: YYYY-MM-DD
   categories: [Category1, Category2]
   tags: [tag1, tag2]
   ---
   ```
3. Write your content below the closing `---` in Markdown
4. Use `##` for top-level sections (these show in the TOC), `###` for subsections
5. Push to GitHub — the site rebuilds automatically

---

## Changing Configuration

All config lives in `_config.yml`. Key fields:

| Field | What it does |
|-------|-------------|
| `title` | Blog name |
| `tagline` | Subtitle shown under the name |
| `url` | Must be `https://meheraabChothia.github.io` |
| `baseurl` | Must be `/aquagar` |
| `avatar` | Path to sidebar profile image (e.g. `/assets/img/aquarion-1.png`) |
| `timezone` | Set to `Asia/Kolkata` |
| `github.username` | Your GitHub username |
| `social.name` | Your name shown in footer |
| `social.email` | Your email |

After any change to `_config.yml`, restart the local server to see the effect.

---

## Changing the Favicon

1. Go to `https://realfavicongenerator.net`, upload your image and download the package
2. Extract and copy the files into `assets/img/favicons/`, replacing what's there
3. Push to GitHub

---

## Deploying Changes

```bash
git add .
git commit -m "your message"
git push
```

GitHub Actions handles the build and deploy. Check the **Actions** tab on your repo to monitor progress.

---

## Adding a Custom Domain

1. In your domain registrar, add a CNAME DNS record pointing your domain to `meheraabChothia.github.io`
2. On GitHub: Settings → Pages → Custom domain → enter your domain and save
3. In `_config.yml`, update `url` to your domain and clear `baseurl`
4. Tick **Enforce HTTPS** once GitHub provisions the SSL certificate
