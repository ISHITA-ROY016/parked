# Prompts

The key prompts used to build Parked, lightly edited for readability. This is curated, not the full chat.

## 1. Original brief

> Build me an app that runs on my mobile and is downloadable, max 10 MB. I don't know what database to use; I have a DB on my system. It's a project-structured app. As full-time 9-to-5 developers we have many unfinished weekend projects that we later forget. It should be very simple: first add an app name. It's incomplete, so we open it and add all the features we want to build. Adding features should support text and voice. UI, UX and how it works are up to you. This is v1. In v2 maybe we send a reminder after one month saying "you should work on this project."
>
> In v1, if project ABC has 3 points and I finish developing the first one, I should be able to move it to Done. So there are states: To do, In progress, Done. The rest is up to you.

**What I specified:** the problem, size limit, mobile target, text plus voice input, the three statuses, and the v1/v2 split.
**What I left to the AI:** UI/UX, storage choice, packaging.

## 2. Deployment
- Asked for a walkthrough of GitHub Pages hosting.
- Hit a DNS error on my phone, which turned out to be a typo in the URL I typed by hand.

## 3. Planning v2
> What about the notification system? Any more plans for v2?

Outcome: a plan to wrap the app with Capacitor for scheduled local notifications, plus a list of v2 ideas (archive, notes, search, reorder, voice notes).

## 4. Decision
I'm using v1 for 2 to 3 weeks before building v2, so v2 is driven by real use.
