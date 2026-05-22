# 2016 Superb Sedan 1.8 Maintenance

Static GitHub Pages site for tracking the 2016 Skoda Superb 1.8 sedan maintenance records.

## Project Links

- Local folder: `C:\Users\chenweihung\Projects\car-maintenance\2016-superb-sedan-1.8`
- GitHub repo: https://github.com/jo830412/car-maintenance-v2
- GitHub Pages: https://jo830412.github.io/car-maintenance-v2/
- Apps Script API: `https://script.google.com/macros/s/AKfycbyQ5BtYGjgoocNb9Jp-vn0siXcSPgdt-UuVkQCkTD_NWl8MNqvbM4rzheoS7S4LVljH/exec`

## Files

- `index.html`: the whole website and app logic.
- `.nojekyll`: keeps GitHub Pages in plain static-file mode.

## Update Flow

After editing `index.html`:

```powershell
node -e "const fs=require('fs'); const html=fs.readFileSync('index.html','utf8'); const scripts=[...html.matchAll(/<script[^>]*>([\s\S]*?)<\/script>/g)].map(m=>m[1]).filter(s=>s.trim()); for (const s of scripts) new Function(s); console.log('ok scripts', scripts.length);"
git status
git add index.html
git commit -m "Describe the change"
git push
```

GitHub Pages usually updates within 1-2 minutes after `git push`.

## Notes

- This project must stay separate from the 2026 Superb site because it uses a separate Apps Script API and Google Sheet.
- `build.py` is ignored and not needed for GitHub Pages.
