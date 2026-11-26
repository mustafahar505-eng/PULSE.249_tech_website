# PULSE 249⁴⁹ Technology Website

Official static website + **Admin control panel**.

- Design: unchanged from your original file
- Control: Decap CMS at `/admin/`
- Deploy: GitHub → Cloudflare Pages
- Media upload: images, PDF, videos → saved in `assets/uploads/`

## Quick start

1. Upload all files in this folder to your GitHub repository
2. Connect the repo to Cloudflare Pages (no build command)
3. Open `https://your-domain/admin/` and login with GitHub
4. Upload media and edit content

See **HOW-TO-CONTROL.md** for full instructions (English, no special characters).

## Structure

- `index.html` – public website
- `admin/` – control panel
- `content/` – editable JSON (slides, events, settings)
- `assets/uploads/` – all files uploaded from Admin

## Contact

info@pulse249.org
