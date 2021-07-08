# semver Q&A

Running live [here](https://semver-questions.netlify.app)

[quick primer](https://semver.org) on semantic versions

This is a micromaterial to practice reading and understanding semantic versioning (semver).

It's based on the [questions template](https://github.com/questions-template/questions-template.github.io) by the amazing Julia Evans. You can see her much better version [here](https://questions.wizardzines.com/).

## Reading Semantic Version numbers

Sometimes, you have a bunch of dependabot alerts and automated PRs raised to address security vulnerabilities. One of the big questions is, "will merging this break anything?"

Semver can help answer that question, since usually anything with only a MINOR or PATCH version upgrade _should_ have backwards compatibility, even if new features were introduced.

So if the update is something like:

- 2.14.8 => 2.14.9

OR

- 1.1.0 => 1.2.0

you can probably merge it in and it'll be fine. But always test this out somehow (either manually, or via an automated build pipeline) to be sure!

## Choosing which number to bump

Other times, you're updating your own library that other people and systems might be dependent on. The last thing you'd want to do is surprise them by breaking their software!

So if you only fixed some bugs and nothing else, you can convey that by just incrementing the PATCH version.

If, on the other hand, you removed *ANYTHING* from the public API of your library, even if it's not something you think anyone is using, best practice is to bump the major version.

## running locally

use whatever local webserver you want, since it'll just serve the index.html from the root. One easy one is

```bash
python -m http.server
```

### license

Everything in this repository is MIT licensed.
