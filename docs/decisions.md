# Design decisions

## PWA instead of a native app
- Needs no app store, no Android Studio and no signing for v1
- Installs from a link and runs full-screen
- Total size is a few KB, far under the 10 MB limit
- Trade-off: no reliable scheduled notifications (see below)

## IndexedDB instead of a server database
- The app is single-user and personal, so a backend would add cost and complexity for no benefit
- Data stays on the device and works offline
- Trade-off: data is lost if browser storage is cleared, so I added JSON export and import

## Vanilla JavaScript, one HTML file
- A project this small does not need a framework or build step
- Easy to read, edit and host anywhere

## Web Speech API for voice
- No extra library or API key
- Dictated text goes into the input box first, so I can correct it before adding
- Trade-off: needs Chrome on Android and a network connection

## Status model: To do, In progress, Done
- Tapping the pill cycles the status, which takes one tap on a phone
- In the All view, in-progress items come first, then to do, then done

## Why reminders are deferred to v2
A PWA cannot reliably fire a notification at a scheduled time while the app is closed on Android. Wrapping the same code with Capacitor lets it schedule local notifications on the device with no server. Each project already stores a last-touched time, so the plan is to schedule a reminder 30 days after the last activity and reset it on any change.

## Hosting
GitHub Pages: free, HTTPS by default (needed for service workers and voice), deploys on push.
