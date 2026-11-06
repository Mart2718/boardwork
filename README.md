# Boardwork — Math Collaboration Studio

A browser-based classroom tool for Marty Romero’s collaborative mathematics classes at Santa Ana College. Designed for a projected display, with teacher controls for grouping, connection, mathematical discussion, and checks for understanding.

## Quick start

Open `index.html` in a modern browser. No installation, build command, API key, database, or account is required by the app. For a local web preview, run `python3 -m http.server 8000` from this folder and visit `http://localhost:8000`.

## Features

- **Build your groups:** paste one display name per line, or import a text/CSV roster. For multi-column CSV files, use a `Name`, `Display Name`, or `Student Name` header. CSV files with a single column can omit the header.
- Mark attendance before generating groups. Choose a target group size (2–12) or an exact number of groups. Automatic grouping balances sizes and avoids single-student groups. For odd attendance, a target of two may require a trio.
- Groups have numbers, not assigned locations. Place them wherever works in your classroom.
- **Move** a student without exchanging anyone, or **Swap** two students. Manual moves allow uneven, singleton, and empty groups; empty group slots remain available.
- **Make a connection:** 46 general, precalculus, and Calculus I prompts with teacher connection notes.
- **Start Thinking:** an everyday collaborative routine and nine additional routines, including Say Your Thinking and Predict → Solve → Check.
- **Check Understanding:** Explain → Try Alone → Reconnect and Recall → Compare → Check.
- **Help Me Enter:** supported entry into the mathematics through a small example, shared decision, and reconnection to the original task.
- Presentation mode, routine selection while presenting, sentence starters, and a pausable timer. Press Escape to exit presentation mode.

The instructor supplies the mathematics task and any individual check questions. The app does not generate or grade mathematical answers. Prompts and routines are editable in `app.js`.

## Put this in GitHub

1. Create a repository (suggested name: `boardwork`).
2. Upload the **contents** of this folder to the repository root. Keep `index.html`, `style.css`, and `app.js` together.
3. Commit the files.
4. Publish with your preferred static website host. The app has no build step. The included `netlify.toml` publishes the repository root when using Netlify.

This package contains no Git history, private ChatGPT hosting identity, hosting credentials, or classroom roster.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | App structure and dialogs |
| `style.css` | Responsive teacher and presentation layouts |
| `app.js` | Prompts, routines, grouping, roster import, and timer |
| `netlify.toml` | Optional Netlify configuration and response headers |
| `.gitignore` | Excludes local exports, credentials, and development clutter |
| `SECURITY.md` | Data handling, review scope, and limitations |

## Privacy and device storage

Names stay in the browser’s memory unless the teacher enables **Remember this roster on this device**. This saves display names in localStorage, not attendance, generated assignments, or grouping history. The saved roster is specific to the browser profile and site origin. Clearing the roster removes the app’s saved roster on that origin.

Do not commit student rosters, student IDs, email addresses, or classroom exports to the repository. Anyone viewing a projected group display can see the displayed names. On shared computers, leave remembering off and clear the roster after use.

The app makes no network requests, uses no external scripts/fonts, and includes no analytics. Static hosting providers may keep ordinary request logs independently of this app. Moving to a different domain does not transfer a saved browser roster.

## Accessibility

Controls have labels, keyboard focus indicators, and responsive layouts. Seated participation, pointing, sketching, and passing during check-ins are explicitly welcomed. These design choices are not a claim of certified WCAG compliance. Test the final hosted version with your classroom devices, keyboard, and preferred screen reader.

## Instructional context

The routines are classroom adaptations informed by collaborative learning and Building Thinking Classrooms, not an official or endorsed BTC product. Selected routines were adapted from Marty Romero’s [Willingham Faculty Hub](https://memorythinkingattention.netlify.app/). The package does not reproduce the hub’s book quotations or claim that these particular protocols have been independently validated.

## Validation at packaging

JavaScript syntax was checked. Earlier classroom UI checks covered grouping, moves, swaps, topic selection, routine selection, entry support, and presentation mode. Automatic grouping was checked across 22,089 size/count cases. Direct movement checks covered singleton and empty groups. New thinking and retrieval selectors were checked in both teacher and presentation views. The optional Netlify header configuration has not been tested on a deployed Netlify copy.

## License

No open-source license is assigned by this package. Choose a license before inviting reuse beyond the permissions you intend to grant.
