# Threadline

A desktop application for engineering leaders. It captures everything that
lands on you, helps you decide what it is, plans your day around the time you
actually have, and closes the day and the week with a review — on your own
machine, in one local database, with no account and no server.

Threadline is the CPU layer of
[*The Engineering Protocol Stack*](https://engineeringprotocolstack.com/book/):
it manages your own capacity — what comes in, what you decide to do, and when.
It is the companion of [Trustline](https://github.com/guillemf/trustline-releases),
the WAN layer, which manages the commitments you make with other people. It is
free, for macOS, Windows, and Linux.

**This repository distributes the installers only — it holds no source code.**
The application is proprietary; see [Licence](#licence) below.

## Download

Every version, with its release notes, is listed under
[Releases](https://github.com/guillemf/threadline-releases/releases). The newest
published one is always at
[releases/latest](https://github.com/guillemf/threadline-releases/releases/latest).

| Platform | File | Notes |
| --- | --- | --- |
| macOS · Apple silicon | `Threadline_<version>_aarch64.dmg` | M1 or later |
| macOS · Intel | `Threadline_<version>_x64.dmg` | |
| Windows | `Threadline_<version>_x64-setup.exe` | 64-bit |
| Linux · AppImage | `Threadline_<version>_amd64.AppImage` | Runs on most distributions |
| Linux · Debian | `Threadline_<version>_amd64.deb` | Debian, Ubuntu and derivatives |
| Linux · RPM | `Threadline-<version>-1.x86_64.rpm` | Fedora, openSUSE and derivatives |

Prefer the `.deb` or `.rpm` where your distribution supports them. The
AppImage is much larger for the same application because it carries its own
copy of the WebKitGTK rendering engine; the packages declare it as a
dependency and let your package manager supply it.

Threadline asks this repository once a day whether a newer release has been
published, and says so in the app if one has. The request sends nothing about
you, and Settings → About can turn it off. The app only tells you and links
here; it never downloads or installs anything by itself.

### The first launch needs one extra step

These builds are not yet signed with a paid developer certificate, so macOS and
Windows will both warn that the publisher cannot be verified. What that warning
means in practice is that the operating system can see the file carries no
certificate it recognises — not that it found anything wrong with it.

- **macOS** — right-click the app and choose *Open*, then confirm once. Or, from
  a terminal: `xattr -dr com.apple.quarantine /Applications/Threadline.app`.
- **Windows** — choose *More info*, then *Run anyway*.
- **Linux** — no warning, but an AppImage has to be made executable before it
  will run: `chmod +x Threadline_<version>_amd64.AppImage`.

Certificates are being obtained, and these warnings will disappear in a later
release.

## What it does

- **Capture from anywhere.** A global shortcut opens a one-line capture window
  over whatever you are doing, so nothing has to be remembered.
- **Process the inbox.** Decide what each item is: do it, delegate it, schedule
  it, keep it as reference, or drop it — with the keyboard.
- **The Matrix.** Every active item sits in one of four quadrants of urgent and
  important, so what is important but not urgent stops being invisible.
- **Plan your day.** Choose a Big 3 for today, see your calendar, and start the
  day with a kick-off that compares what you planned with the time you have.
- **Focus blocks.** Work on one thing at a time, and record how the block ended.
- **Waiting for and follow-ups.** Everything you handed to someone else, grouped
  by person, with the date you meant to check back.
- **Daily, weekly and monthly reviews.** Close the day, run the weekly review
  step by step, and let the monthly migration surface what keeps slipping.
- **Projects and statistics.** Lightweight projects with next actions, and a
  dashboard of what you finished and where the work is piling up.
- **English, Spanish and Catalan**, with full keyboard operation.

## Where your data lives

Threadline has no account, no sign-up, and no backend. Everything is one local
SQLite database under your own user directory:

| | |
| --- | --- |
| macOS | `~/Library/Application Support/cat.guillem.threadline/threadline.db` |
| Windows | `%APPDATA%\cat.guillem.threadline\threadline.db` |
| Linux | `~/.local/share/cat.guillem.threadline/threadline.db` |

Settings → Export data writes every table to one JSON file you choose, and the
app can keep dated backups in a folder of your choice.

The only servers Threadline contacts are the calendar feeds you add yourself
(read-only) and, once a day, GitHub — to ask whether a newer version has been
published. That request sends nothing about you or your work, and you can turn
it off. There is no telemetry of any kind, and logs never contain the titles or
notes of your items.

## Licence

Threadline is proprietary software, offered free of charge. It is **not** open
source. You may install and use it for personal or commercial work, on devices
you own or control; you may not redistribute it. The only party permitted to
distribute Threadline is its author.

The licence terms are in [`LICENSE`](LICENSE) and [`EULA.md`](EULA.md). Paid
features may be added in future releases. What is free today stays free.

Copyright © 2026 Guillem Fernandez. All rights reserved.

## Links

- [*The Engineering Protocol Stack*](https://engineeringprotocolstack.com/book/)
- [Trustline releases](https://github.com/guillemf/trustline-releases)
- [guillem.cat](https://guillem.cat)
