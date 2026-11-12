# Schedules

A single-page production schedule builder (`index.html`). No server, no build step. Same setup as the invoice app.

- New schedule: a step-by-step setup (project type, client, dates, outputs, team, WIP cadence) that blocks out a first schedule.
- Timeline to work in (drag, resize, link bars so they push each other), calendar to print or send to the client.
- **Print / PDF** prints the calendar on A4 landscape; choose Save as PDF in the print window.
- Every schedule is a file in a Google Drive folder called `Schedules` (`<name>.schedule.json`). This repository holds only the app, no schedules.
- Kontroll opens the same page in a tab (Tabs › Open Schedule).

Live at https://swisscirkus.github.io/schedules/

## Setup notes

The app uses the same Google OAuth *Web application* client ID as the invoice app (set at `GOOGLE_CLIENT_ID` near the end of `index.html`). Its origin, `https://swisscirkus.github.io`, is already an **Authorized JavaScript origin** for that client, so nothing new is needed in Google Cloud. The only permission requested is `drive.file`, which lets the app see just the files it created.

For local testing run `python -m http.server 8765` in this folder and add `http://localhost:8765` as an origin.

The page is built from Kontroll's prototype (`docs/prototypes/schedule-builder.html`); from now on this file is the live one.
