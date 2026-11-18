# Parked

A tiny offline-first app for developers to track the weekend projects they start and never finish.

**Live app:** https://ishita-roy016.github.io/parked/
(Open in Chrome on Android, then menu → *Install app*.)

## Why this exists

Working a 9-to-5 means a pile of half-built side projects that get forgotten. Parked keeps each project and its unbuilt features in one place, so picking one back up takes seconds instead of an archaeology session.

## Features (v1)

- Add a project by name
- Add features to a project by **typing or voice**
- Each feature has a status: **To do, In progress, Done**
- Tap a status pill to move a feature forward
- Filter by status; progress bar and "last touched" date on every project
- Works fully offline after the first load
- Export and import a JSON backup

<!-- Add screenshots here -->
<!-- ![Home](docs/screenshots/home.png) ![Project](docs/screenshots/project.png) -->

## Tech

| Concern | Choice |
|---|---|
| App type | Progressive Web App (installable, no app store) |
| UI | Vanilla HTML, CSS and JavaScript in a single `index.html` |
| Storage | IndexedDB (data stays on the device, no backend) |
| Voice input | Web Speech API |
| Offline | Service worker with a cache-first strategy |
| Hosting | GitHub Pages |

Total size is under 20 KB. See [docs/decisions.md](docs/decisions.md) for why these choices were made.

## Roadmap

- [x] v1: projects, features, statuses, text and voice input, backup
- [ ] v2: native Android build with Capacitor
- [ ] v2: local notification if a project is untouched for 30 days
- [ ] v2: archive an abandoned project without deleting it
- [ ] v2: project notes and repo link
- [ ] v2: search across features
- [ ] v2: nicer edit screens in place of browser pop-ups

## Using Parked: privacy and limitations

Parked is free and needs no account. Open the link, install it, and you get your own private copy.

- **Your data stays on your device.** Projects are stored in your browser's IndexedDB. Nothing is collected, uploaded or shared, and there is no server.
- **Every install is separate.** Other people's projects never appear in yours, and yours never appear in theirs.
- **It works offline** once it has loaded the first time.

### Limitations

- **No sync.** Projects don't move between your phone and other devices. Use Export backup and Import backup to transfer them.
- **Data lives in browser storage.** Clearing Chrome's site data deletes your projects, so export a backup now and then.
- **Voice input needs Chrome on Android and an internet connection.** It may not work on iPhone. To install on iPhone, open the link in Safari and use Share, then Add to Home Screen.
- **Basic edit dialogs.** Naming and editing use browser pop-ups for now.
- **No reminders yet.** Browsers can't reliably schedule background notifications, hence the Capacitor plan for v2.

## Built with AI assistance

I designed the idea and its requirements (the problem, the three statuses, text and voice input, the size limit, mobile-first, v1/v2 split). The first version of the code was written with Claude (Anthropic). I deployed it, tested it on my phone, and I'm iterating on it from real use. The prompts that shaped it are in [docs/prompts.md](docs/prompts.md).

From here on, commits that include AI-written changes carry a `Co-authored-by: Claude` trailer. The earlier commits (README, docs and license) were also written with Claude's help but were pushed without it.

## Run locally

Any static server works, for example `python3 -m http.server`, then open `http://localhost:8000`. Service workers and voice input need HTTPS or localhost.
