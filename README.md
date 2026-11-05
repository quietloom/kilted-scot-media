# kilted-scot-media

Transient media drop for [kilted.scot](https://kilted.scot) social publishing.
**Disposable by design.** Nothing here is an archive, and nothing here is canonical.

## Why this exists

Instagram's Content Publishing API does not accept a file upload. It takes a URL and
fetches it: *"We cURL media used in publishing attempts, so the media must be hosted on
a publicly accessible server at the time of the attempt."* Unpublished containers expire
after 24 hours.

So a finished video needs a public HTTPS URL that survives **one fetch**. This repo,
served by GitHub Pages, is that URL. Once Instagram has the video, Instagram hosts it —
the copy here has done its job.

## What this repo is not

- **Not the website.** That is `quietloom/kilted-scot-site`, which deploys
  [kilted.scot](https://kilted.scot) and is kept clean of transient files. Do not put
  site assets here or media files there.
- **Not an archive.** Master files live with each series' own project. If the only copy
  of something is here, that is a mistake to fix, not a state to rely on.
- **Not permanent.** When this repo grows, it gets **deleted and recreated**. That is the
  intended lifecycle, not a failure. Every URL it has ever served is expected to break.

## Lifecycle

1. Drop the finished video in, commit, push.
2. **Wait, then verify.** A push is not a live URL. Measured on this repo's first deploy:
   two 404s before the file appeared, live at roughly 40–60 seconds. Confirm
   `200` with a `video/*` content type before handing the URL to any publishing tool —
   handing over a URL that is still 404ing wastes a container.
3. Publish. Instagram now holds its own copy.
4. Delete the file whenever convenient.
5. When the repo gets unwieldy, delete the whole thing and recreate it.

**Removal is not immediate, and must not be treated as a privacy control.** Measured
07/09/2026: a file deleted and pushed still returned `200` for at least 2.5 minutes
afterwards — GitHub Pages serves through a CDN with its own cache lifetime. That is
harmless for this repo's purpose, but it means deleting a file does not promptly make it
unreachable. Anything that must not be public must not be pushed here in the first
place.

## Licensing — read before adding anything

There is deliberately **no `LICENSE` file**, and one must not be added. Videos here may
contain third-party assets under their own terms (CC BY-SA and similar), and a blanket
repository licence would misstate the rights on someone else's work.

Pushing a video here makes it publicly downloadable, which is a **publishing event** in
its own right, not an implementation detail — see `VISUAL-SOURCING-STANDARD.md` in the
kilted.scot project. Attribution obligations that apply to the published video apply to
the copy here too. Check them before pushing, not after.
