FORGE PLAN - HOW TO MAKE THE APK

1. HOST IT (GitHub Pages, free)
   - Make a GitHub account. Create a NEW PUBLIC repository named exactly:
       YOURUSERNAME.github.io
     (It must be this name so the app sits at the root of the website.)
   - Upload EVERYTHING in this folder, including the hidden file ".nojekyll".
   - Repo Settings > Pages > Source: "Deploy from a branch", branch "main", folder "/ (root)". Save.
   - After 1-2 minutes, open https://YOURUSERNAME.github.io on your phone and check the app works.

2. BUILD THE APK (PWABuilder)
   - Go to https://www.pwabuilder.com, paste https://YOURUSERNAME.github.io, press Start.
   - It should find the manifest and service worker. Click "Package for stores" > Android > Generate package.
   - Options: Package ID like com.yourname.forgeplan, App name "Forge Plan",
     Signing key: "Create new". Download the zip.
   - The zip contains:  .apk (install on phones), .aab (only for Play Store),
     signing.keystore + signing-key-info.txt (KEEP SAFE, needed for future updates),
     assetlinks.json.

3. REMOVE THE BROWSER ADDRESS BAR
   - In your GitHub repo, create the file  .well-known/assetlinks.json
     and paste in the contents of assetlinks.json from the PWABuilder zip.
   - Wait a few minutes, then reinstall the app.

4. INSTALL ON BOTH PHONES
   - Send the .apk to each phone (WhatsApp to yourself, Google Drive, USB).
   - Tap it, allow "Install unknown apps" when Android asks, then Install.

UPDATING THE APP LATER
   - Edit index.html in GitHub, and change VERSION in sw.js (forgeplan-v1 -> forgeplan-v2).
   - The installed app picks up the change by itself. No new APK needed.
