# PULSE 249 – How to Control the Website (Admin + Upload)

This package keeps your website design **exactly the same**.
It adds a real **Admin panel** so you can:

- Upload images, PDFs, videos
- Add news / slides
- Add events
- Edit contact & about text
- Everything saves to GitHub → Cloudflare updates the live site automatically

---

## 1. What is inside this ZIP

```
pulse249_v2/
├── index.html              ← Your original website (design unchanged)
├── admin/
│   ├── index.html          ← Admin panel entry
│   └── config.yml          ← CMS settings
├── content/
│   ├── settings.json       ← Email, About text
│   ├── slides/             ← Hero news / slides (JSON files)
│   └── events/             ← Events (JSON files)
├── assets/
│   ├── uploads/            ← All files you upload from Admin go here
│   ├── images/
│   ├── videos/
│   ├── docs/
│   └── events/
├── README.md
└── HOW-TO-CONTROL.md       ← This file
```

**Important:** All file names are in English only (no Arabic letters) so GitHub does not break them.

---

## 2. Upload to GitHub (clean way)

1. Delete the broken files you already uploaded (the ones with strange names).
2. Create a **new empty repository** or clean the current one.
3. Upload **everything inside** the `pulse249_v2` folder (not the folder itself if you want the files at the root).

Best method (recommended):

- On your computer, open the folder `pulse249_v2`
- Select **all files and folders** inside it
- Drag them into GitHub “Upload files”
- Or use Git:

```bash
git init
git add .
git commit -m "PULSE 249 site with admin"
git branch -M main
git remote add origin https://github.com/mustafahar505-eng/PULSE.249_tech_web.git
git push -u origin main
```

---

## 3. Connect Cloudflare Pages

1. Cloudflare Dashboard → **Workers & Pages** → Create → Pages → **Connect to Git**
2. Choose your repository
3. Settings:
   - Framework preset: **None**
   - Build command: leave **empty**
   - Build output directory: `/` or leave default
4. Deploy
5. Add your custom domain in **Custom domains**

---

## 4. How to use the Admin (the important part)

### First time setup (one time only)

1. Open your live site: `https://YOUR-DOMAIN/admin/`
2. You will see Decap CMS login → **Login with GitHub**
3. Authorize the app for your repository

If it asks for repository name, make sure in `admin/config.yml` the line:

```yaml
repo: mustafahar505-eng/PULSE.249_tech_web
```

matches **exactly** your GitHub username/repo.

### Daily use

1. Go to `https://YOUR-DOMAIN/admin/`
2. Login with GitHub
3. You will see collections:
   - **Hero slides / News** → add or edit slides
   - **Events** → add seminars, meetings, etc.
   - **Site Settings** → change email, about text
4. Click **Media** or use the image field → **Upload** any photo, PDF, video
5. Click **Publish** / **Save**
6. The CMS creates a commit on GitHub
7. Cloudflare automatically rebuilds → your site updates in 1–2 minutes

---

## 5. Important notes about the current design

- The **public website design is 100% the same** as the file you gave me.
- The Admin currently writes clean JSON files into `content/`.
- The main `index.html` still contains the original data inside the JavaScript.
- To make the Admin fully control the visible content, we need one small next step: connect `index.html` to read from the JSON files.

**Right now you can:**
- Upload any media safely
- Manage content in structured JSON
- Have a professional admin like university sites

**Next step (tell me when you want it):**
I will make `index.html` load the slides, events, and settings from the JSON files automatically, so whatever you save in the Admin appears on the live site without touching the HTML again.

---

## 6. Quick checklist

| Task                        | How                                      |
|----------------------------|------------------------------------------|
| Upload photo / PDF         | Admin → Media or image field → Upload    |
| Add news slide             | Admin → Hero Slides → New                |
| Add event                  | Admin → Events → New                     |
| Change email / about       | Admin → Site Settings                    |
| Site updates automatically | Yes (after you click Publish)            |
| Design changes?            | No – design stays exactly as you built it|

---

## 7. If the Arabic filename broke again

Never upload files with Arabic names via the GitHub web interface.
Always use English names only (this package already does that).

---

You can deploy this today.
After it is live, open `/admin/` and test uploading one image.

When you are ready for the site to **read** the JSON automatically (so Admin changes appear on the homepage), just say the word and I will connect it.
