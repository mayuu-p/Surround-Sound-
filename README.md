# SurroundSync

SurroundSync is an installable browser app for creating a local audio room, sharing Wi-Fi setup through a real QR code, scanning that QR code with a phone camera, adding up to 15 manually named devices, assigning channels, and playing a locally selected audio/video file.

## Important browser limitation

This is a web app. A browser cannot turn on Android hotspot, join Wi-Fi automatically, access `WifiNetworkSpecifier`, perform native NSD discovery, or route one audio stream across multiple phones. Start or join the hotspot in Android Settings, then use the QR and on-screen steps in this app. Selected media plays on the current phone.

## Run locally

Requirements: Node.js 20+ (or Bun 1.1+).

```sh
git clone <your-github-repository-url>
cd surroundsync
npm install
npm run dev
```

Open the local URL printed by Vite. For camera scanning, use `localhost` or an HTTPS deployment and grant camera permission.

## Build and preview

```sh
npm run build
npm run preview
```

The project uses TanStack Start, React, TypeScript, Vite, and Tailwind CSS. The complete application is in `src/routes/index.tsx`; shared styling is in `src/styles.css`; PWA metadata is in `public/manifest.webmanifest`.

## Upload to GitHub

1. Create an empty repository on GitHub.
2. Extract this download and open a terminal in the extracted folder.
3. Run:

```sh
git init
git add .
git commit -m "Add SurroundSync app"
git branch -M main
git remote add origin https://github.com/<your-user>/<your-repository>.git
git push -u origin main
```

## Deploy

GitHub stores the code, but GitHub Pages does not run the TanStack Start server build used by this project. Deploy the GitHub repository with a host that supports the Vite/TanStack Start build, such as Vercel, Netlify, or Cloudflare, using:

- Install command: `npm install`
- Build command: `npm run build`
- Node version: `20`

After deployment, open the HTTPS URL on Android and choose the browser's **Add to Home screen** or **Install app** option. HTTPS is required for camera access outside `localhost`.