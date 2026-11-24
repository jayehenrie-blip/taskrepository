# Task Nebula

Your Google Tasks shown as a 2D map of bubbles. Each list is a cluster, each task is a bubble, and subtasks are small dots attached to their task. Installable on Android from Chrome.

- **Size** shows how soon a task is due; today and overdue are the largest.
- **Color** shows priority: gray = none, blue = `!3`, amber = `!2`, red = `!1` (put the tag at the start of the task title).
- **Outlines:** pulsing = overdue; dashed = in progress (`#doing` in the task notes).

Everything reads from and saves to Google Tasks directly. There is no server; the app keeps only a cached copy, settings and unsaved changes on each device.

## Hosting

This is a static site. Turn on **Settings → Pages → Deploy from a branch → main / (root)**. The app opens at `https://<user>.github.io/<repo>/`.

## First run

1. In Google Cloud, enable the **Google Tasks API**, set up **Google Auth Platform** (External, Testing, with your account as a test user), and create a **Web application** OAuth client.
2. Open the app. The setup screen shows the exact **JavaScript origin** and **redirect URI** to register on that client.
3. Paste the Client ID into the app and sign in.

The Client ID is stored only on each device, not in this repository.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app |
| `manifest.webmanifest` | Install details (name, icons, colors) |
| `sw.js` | Keeps the app available offline; Google sign-in and API calls always go to the network |
| `icons/` | App icons |
