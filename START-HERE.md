# CareCircle iPhone app (CC002)

This folder is the iPhone wrapper for **carecircle.netlify.app**. The app opens the live site inside a real iPhone app.
Put the website up first (CareCircle-CC002 zip, DEPLOY.md). If your Netlify site name is not `carecircle`,
change the two places it says `carecircle.netlify.app` in `capacitor.config.json` (or ask Claude).

- Bundle ID: **com.carecircle.app**

Same steps as the Rival apps:
1. developer.apple.com > Identifiers > + > App IDs > App. Description `CareCircle`, Bundle ID Explicit `com.carecircle.app`. Register.
2. appstoreconnect.apple.com > Apps > + > New App. iOS, name `CareCircle` (if taken, `CareCircle Family`), English, bundle `com.carecircle.app`, SKU `carecircle`, Full Access. Create.
3. GitHub > New repository `carecircle-ios`, Private > uploading an existing file > drag in everything inside this folder > Commit changes.
4. Codemagic > Add application > GitHub > `carecircle-ios` > Ionic > Finish.
5. developer.apple.com > Profiles > + > App Store Connect > `com.carecircle.app` > newest distribution certificate > name `CareCircle App Store` > Generate.
6. Codemagic > Settings > Code signing identities > iOS provisioning profiles > Fetch profiles > tick `CareCircle App Store`, name `carecircle_profile` > Download selected.
7. Codemagic > CareCircle > Start new build > main.

The app asks for the camera only when you take photos of paperwork, and the microphone only when you tap Speak.
