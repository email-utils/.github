# Contributing to email-utils

Thanks for helping. This guide covers every repository in the organization; the [developer docs](https://email-utils.github.io/meta/contributing/) go deeper.

## Set up

The packages live in separate repositories, tied together by the [meta](https://github.com/email-utils/meta) workspace and [mani](https://manicli.com):

```sh
brew install mani            # or see https://manicli.com for other installs
git clone git@github.com:email-utils/meta.git email-utils
cd email-utils
mani sync                    # clones every repo into the workspace
mani run install             # npm ci in each package
```

You need Node 24 for development (`.nvmrc`); the packages support Node 22 and later.

## Make a change

1. Pick or open an issue. Work tracked for v1.0 is on the [project board](https://github.com/orgs/email-utils/projects/1).
2. Branch from `main` as `<type>/<issue-number>-<slug>`, for example `fix/11-local-part-dots`.
3. Keep the checks green. lefthook runs the fast ones on every commit:

   ```sh
   npm run pre-commit        # lint, format:check, typecheck
   npm run test:coverage     # the tests, with coverage thresholds
   npm run build && npm run check:package
   ```

4. Open a pull request against `main` with a [Conventional Commits](https://www.conventionalcommits.org) title, such as `fix: reject leading dots in the local part`. PRs are squash-merged and the title becomes the commit, which decides the next version: `fix` is a patch, `feat` is a minor, and `!` (e.g. `feat!:`) is a major.
5. Link the issue in the description (`Closes #11`).

If you use [Claude Code](https://claude.com/claude-code), the workspace ships skills for this flow: `/email-utils:start`, `/email-utils:pr`, and friends.

## Releases

Maintainers release through release-please and npm trusted publishing; contributors never publish. See the [release process](https://email-utils.github.io/meta/contributing/releasing).

## Conduct

Everyone taking part agrees to the [Code of Conduct](CODE_OF_CONDUCT.md).
