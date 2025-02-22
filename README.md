# heroku-buildpack-bun

Heroku buildpack for [Bun.js](https://bun.sh/) - allows you to run Bun on Heroku.

Largely copied from the [Deno buildpack](https://github.com/chibat/heroku-buildpack-deno).

## How to use

To add the buildpack to your Heroku app, visit the settings page for your app on Heroku, then under 'Buildpacks' add the URL `https://github.com/jakeg/heroku-buildpack-bun`.

You'll need a [`Procfile`](https://devcenter.heroku.com/articles/procfile) in the root folder of your app, with eg `web: bun index.js` in it.

Pin a certain Bun version with a `runtime.bun.txt` or `runtime.txt` with e.g. `v1.0.7` in it.

## Potential issues

~Be aware that Heroku doesn't use a new enough version of the Linux kernel to support `io_uring`, which is needed for `Bun.write()`. Use `node:fs.writeFile()` instead.~ - this [seems now to be fixed](https://devcenter.heroku.com/changelog-items/2713).

Use the Issues tab to report any issues.
