# Sing to Song: iPhone and Android app

This folder is the Sing to Song web app packaged as real iPhone and Android apps (using Capacitor).
Everything is set up: app name, app ID `com.singtosong.app`, icons, splash screens, and the
microphone permission text Apple and Google require.

- `www/index.html` is the app. To update it, replace this file, then run `npx cap sync`.
- `ios/` is the Xcode project for the App Store.
- `android/` is the Android Studio project for Google Play.

## Try it on Android right now
Install `sing-to-song-android-test.apk` on an Android phone (you'll need to allow installing from
your browser or Files app). This is a test build. Google Play needs a signed release build (step below).

## Put it on the App Store (needs a Mac)
1. Join the Apple Developer Program (US $99/year) at https://developer.apple.com/programs/ with your Apple ID.
2. On a Mac, install Xcode from the Mac App Store, and Node.js from https://nodejs.org.
3. Unzip this folder, open Terminal in it, and run:
   `npm install` and then `npx cap open ios`
4. In Xcode: click **App** in the left list, open **Signing & Capabilities**, pick your team.
   If `com.singtosong.app` is taken, change it to something unique like `com.yourname.singtosong`.
5. In https://appstoreconnect.apple.com: **Apps → + → New App**, use the same bundle ID and the name "Sing to Song".
6. In Xcode: choose **Any iOS Device** at the top, then **Product → Archive**, then **Distribute App → App Store Connect → Upload**.
7. Back in App Store Connect, fill in the listing (text below), add screenshots (6.9" iPhone), a privacy
   policy link, and **Submit for Review**. Try it first with **TestFlight** on your own phone.

## Put it on Google Play
1. Create a Google Play developer account (US $25 once) at https://play.google.com/console.
2. Install Android Studio, then run `npm install` and `npx cap open android`.
3. **Build → Generate Signed App Bundle** (make and keep a safe copy of your upload key).
4. In Play Console, create the app, upload the `.aab`, fill in the listing and data-safety form, and send it to review.

## Store listing text (ready to paste)
- **Name:** Sing to Song
- **Subtitle:** Sing it. Turn it into a song.
- **Category:** Music
- **Description:** Sing into your phone and Sing to Song builds music around your voice. Record in layers,
  add live voice effects like auto-tune, echo and harmonies, trim and fade parts, and drop in sound
  effects. Then generate a full arrangement that follows your key, tempo and melody, redo any part you
  don't like, give it a name and album photo, and save it to your phone.
- **Keywords:** sing,singing,voice,autotune,music maker,song maker,recording,vocal effects,beat,karaoke
- **Microphone:** used only to record your singing. Recordings stay on your phone.

## Before Apple will approve it
Apple reviews every app. These parts of the current version would likely get it rejected, and need
changing first:
1. **Payments:** Premium and buying songs or sound effects are test-only. On iPhone, digital purchases
   must use Apple's In-App Purchase. For a first release, hide these or connect In-App Purchase.
2. **Discover and profiles:** the other creators are examples, and following, likes and sales only exist on
   your phone. Apple rejects placeholder content. A first release should either hide Discover or connect a
   real server with accounts.
3. **Once people can share songs:** Apple requires a way to report and block people, terms of use, and a way
   to delete your account.
4. **Privacy policy:** a web page saying what the app collects (today: nothing leaves the phone).
