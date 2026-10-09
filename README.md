# Friends Expo app

A React Native app built with Expo. The Plans tab has an interactive picnic
invitation, and the My Circle tab shows the friend list and lets you share an
invite from your phone.

The screens use shared `ThemedView` and `ThemedText` components. The custom app
icon and splash-screen artwork are in `assets/`.

## Run the app on your computer

1. Open this folder in VS Code.
2. Open **Terminal → New Terminal**.
3. Run `npm start`.
4. To preview it on a phone, install **Expo Go** and scan the QR code shown in
   the terminal. Your computer and phone should be on the same Wi-Fi network.

## Build and share an Android APK

You need an Expo account for EAS Build. Create your own account at
[expo.dev/signup](https://expo.dev/signup), or sign in to your own existing
account. Do not use someone else's Expo account.

In the VS Code terminal, make sure you are in this project folder, then run:

```sh
eas login
eas whoami
eas build:configure
```

If EAS asks which account or project to use, choose your own account and create
a new EAS project for this app. Do not link another student's project. EAS may
add a `projectId` to `app.json`; keep that value in this project.

Start the Android APK build:

```sh
eas build --platform android --profile preview
```

If asked about Android signing credentials, let EAS create a new keystore for
this app. Keep the keystore associated with your own Expo project. The cloud
build can take several minutes; it is not complete until EAS reports **Build
finished** or **Build successful**.

When the build succeeds, open its build-details link from the terminal or from
your project on [expo.dev](https://expo.dev/). Use the APK download/install
link on that build page as the shareable installer link for your assignment.
The `preview` profile is configured for internal distribution and an `.apk`,
not a Play Store `.aab`.

## Create the Assignment 02 submission PDF

After the APK build has finished and the project has been uploaded to your own
GitHub repository, create the five-page submission PDF. The three screenshot
files are generated locally and are excluded from the repository, so keep
them in this project folder:

```sh
npm run submission:pdf -- https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

Replace the example with your actual GitHub repository URL. The resulting
`Assignment-02-Submission.pdf` includes the repository link, direct APK
download and QR code, a screenshot of VS Code, and screenshots of both app
tabs.
