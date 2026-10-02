# SkinAI_PWA

A separate, installable PWA launch page for the existing SkinAI Streamlit deployment:

https://skindiseaseaideploy.streamlit.app/

## Safety and separation
- This folder is independent from your original `SkinDiseaseAI` project and your `SkinAI_Deploy` folder.
- It does not contain, copy, or modify your model or inference code.
- The **Open SkinAI** button opens the existing Streamlit app.
- The service worker caches only this PWA's own static files. It deliberately does not cache or intercept the Streamlit website.
- This is a launch PWA, not an offline skin-screening application. The deployed Streamlit app needs an internet connection.

## Deploy it with GitHub Pages
1. Create a **new GitHub repository** named `skinai-pwa` (do not reuse `skinai-deploy`).
2. Upload all files and the `icons` folder from this directory to the root of the new repository.
3. In that repository, open **Settings → Pages**.
4. Under build and deployment, choose **Deploy from a branch**, select `main` and `/(root)`, then save.
5. Wait for GitHub Pages to publish the site. The URL will typically be `https://YOUR-GITHUB-USERNAME.github.io/skinai-pwa/`.
6. Open that HTTPS URL on Android in Chrome, use the browser menu, and choose **Install app** or **Add to Home screen**.

## Updating
- Changes to the existing Streamlit app: update the existing `skinai-deploy` repo as usual. After Streamlit Cloud finishes deploying, the PWA's Open SkinAI link will open the updated website; users may need to refresh/reopen it.
- Changes to the PWA page itself: update this separate `skinai-pwa` repository. GitHub Pages will publish the new version; reopen or refresh the PWA to receive it.
- A failed Streamlit deployment will not be fixed by updating the PWA.

## Notes
- HTTPS is required for service worker/PWA features; GitHub Pages provides HTTPS.
- This first version uses a launch page because third-party websites such as Streamlit may block embedding in an iframe.
- SkinAI is a research prototype for preliminary screening and is not a medical diagnosis.
