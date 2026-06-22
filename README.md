# myWeddingPlan

A private nikkah & wedding plan. The published page (`index.html`) is **encrypted with [StaticCrypt](https://github.com/robinmoisson/staticrypt)** — opening it shows a password prompt; the real content only decrypts in the browser after the correct password is entered.

- The **plaintext master is never committed** — only the encrypted `index.html` lives here, so the repo is safe even if public.
- Hosted on **Netlify** (static — it just serves `index.html`).
- Marked `noindex` so search engines don't list it.

## Rebuild after editing the plan

1. Edit the master `wedding-plan.html` (kept outside this repo).
2. In this folder:
   ```powershell
   $env:STATICRYPT_PASSWORD = "your-password"
   .\build.ps1
   git add index.html
   git commit -m "Update plan"
   git push
   ```
3. Netlify redeploys automatically on push.

## Changing the password

Re-run the build above with a new `STATICRYPT_PASSWORD`, then commit & push. Share the password with family **separately** from the link.
