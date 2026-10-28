# Food Log

A neon food, water and weight tracker for your phone.

- BMI plan with daily calorie and protein targets (Indian adult BMI cut-offs)
- Food search with 90+ Tamil Nadu and Indian foods, portions and macros
- Snap your plate: AI finds each food and logs it (free Gemini key or paid Claude key)
- Liquid water bottle, water reminders, food and water streaks that level up
- A–F daily score, body progress avatar, plate diary, weekly recap story
- Works offline. Your data stays on your phone.

## Use it

**Web app (any phone):** open `https://<your-github-name>.github.io/food-log/` in Chrome, then tap ⋮ → **Install app** (or **Add to Home screen**).

**Android APK:** go to this repo's **Releases** page, download `FoodLog.apk`, open it on your phone and allow "Install unknown apps" for Chrome or Files when asked.

## First-time GitHub setup (once)

1. Create a new **public** repository named `food-log`.
2. Upload everything in this folder (keep the `.github` folder; it's hidden on some computers).
3. In the repo, go to **Settings → Pages → Build and deployment → Source** and pick **GitHub Actions**.
4. Open the **Actions** tab. Two jobs run on every push to `main`:
   - **Deploy web app** publishes the site to GitHub Pages.
   - **Build Android APK** builds `FoodLog.apk` and attaches it to a new release.

To update the app, change `www/index.html` and push. Both jobs run again.

## AI photo scan and coach

Open ⚙️ **Settings** in the app and pick a provider:

- **Gemini · free** — get a key at https://aistudio.google.com ("Get API key"). Free keys have daily limits, and Google may use free-tier requests to improve its products.
- **Claude · paid** — key from https://console.anthropic.com, billed per use. Usually better at reading Indian dishes.

Keys are stored only on that phone. Without a key, everything else still works.

## Backup

Data lives in the phone's browser or app storage. Use ⚙️ **Settings → Copy backup** now and then and keep the text somewhere safe (for example WhatsApp "Message yourself"). **Restore** pastes it back. Photos older than 30 days are cleared automatically to save space.

## Build the APK on your own PC (optional)

```bash
npm install
npx cap add android
npm run android:icons
npx cap sync android
npx cap open android   # Android Studio: Build → Build APK(s)
```

Requires Node 20+, Java 17 and Android Studio.

## Health note

This app gives general guidance, not medical advice. Calorie targets never go below 1500 kcal (men) or 1200 kcal (women). Talk to a doctor before big diet changes, and get sugar, thyroid and BP checked if your BMI is high.
