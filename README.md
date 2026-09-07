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
2. Wait for Pages to deploy, then confirm the URL returns `200` with a `video/*`
   content type before handing it to any publishing tool.
3. Publish. Instagram now holds its own copy.
4. Delete the file whenever convenient — the URL is dead the moment the post exists.
5. When the repo gets unwieldy, delete the whole thing and recreate it.

## Licensing — read before adding anything

There is deliberately **no `LICENSE` file**, and one must not be added. Videos here may
contain third-party assets under their own terms (CC BY-SA and similar), and a blanket
repository licence would misstate the rights on someone else's work.

Pushing a video here makes it publicly downloadable, which is a **publishing event** in
its own right, not an implementation detail — see `VISUAL-SOURCING-STANDARD.md` in the
kilted.scot project. Attribution obligations that apply to the published video apply to
the copy here too. Check them before pushing, not after.
