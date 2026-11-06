# Security and privacy notes

## Reviewed scope

The packaged browser-only app: `index.html`, `app.js`, and `style.css`, based on source revision `ca3be6c55faae7624d7bf0347bb7f00a7ad53bd6`. Packaging adds documentation, ignore rules, and optional Netlify configuration. No backend, database, external integration, or account system is included.

- Roster text is rendered using DOM text APIs rather than HTML insertion.
- Import size is limited to 100 KB; accepted data is limited to 200 display names of at most 100 characters each.
- Optional localStorage contains display names only. localStorage is not encryption or access control.
- No secrets, real rosters, third-party scripts, or application network destinations are included.
- Manual movement and swaps preserve student identities, including duplicate display names.

No significant security issue was found in the reviewed application scope. This is not certification or a guarantee. Hosting configuration, provider logs, repository permissions, and future changes are outside that conclusion.

## Hosting

The optional `netlify.toml` sets a content security policy for this self-contained app, blocks MIME sniffing, suppresses referrer information, and disables camera/microphone/geolocation permissions. It intentionally does not set frame restrictions, so an instructor can evaluate LMS embedding. These headers need verification on the final host. Other hosts may ignore this file.

There is no application login in this export. A public repository or public deployment exposes the source code and app to visitors; it does not upload your local browser roster. Do not put roster files in the repository.

If you add analytics, embedded tools, external fonts, math libraries, network APIs, or backend storage, re-review the data flow and update the content security policy before deployment.
