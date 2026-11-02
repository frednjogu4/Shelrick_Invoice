# Publish this app to the existing Vercel project

This is a static PWA. It does not need a server-side database or build step. Invoice records and client details remain in each user's browser storage.

## 1. Put the files in a private GitHub repository

1. Extract this ZIP on a computer.
2. Create a **private** GitHub repository.
3. Upload the *contents* of this folder into the repository root. Keep `index.html`, `manifest.webmanifest`, `sw.js`, and `vercel.json` at the root, along with the `icons/` and `assets/` folders.
4. Commit the files to the repository's production branch, usually `main`.

## 2. Connect it to Vercel

1. Sign in to Vercel and open the existing project **shelrick-invoice-app** (team `shelricktech`).
2. Open **Settings → Git → Connect Git Repository** and choose the private repo. Grant Vercel access to that repo if prompted.
3. Use the repository root as the Root Directory. Select **Other** as the framework preset; leave install/build commands and output directory empty (there is no build step).
4. Ensure the production deployment URL is publicly accessible (not gated by Vercel Authentication/SSO), since a phone must reach the app over HTTPS to install the PWA.
5. Trigger a production deployment from the `main` branch.

The project may have Git deployments disabled. If connecting the repository does not start a deployment, open the project's Git settings and enable Git deployments, then trigger a redeploy. Alternatively, use Vercel CLI from the extracted folder with `vercel deploy --prod` after logging in and linking the existing project.

## 3. Confirm the deployment

Open the Vercel production URL on a phone. On Android use Chrome's **Install app** option; on iPhone use Safari's **Share → Add to Home Screen**. After first load, the app shell works offline.
