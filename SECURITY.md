# Security policy

## Supported versions

| Package                  | Supported           |
| ------------------------ | ------------------- |
| `@email-utils/*` 1.x     | ✅                  |
| `@email-utils/*` 0.0.1-x | ❌ (please upgrade) |

Until 1.0.0 ships, fixes land on `main` only.

## Reporting a vulnerability

Please **don't** open a public issue. Report privately through GitHub: open the affected repository's **Security** tab and choose **Report a vulnerability**.

Include the package and version, what an attacker can do, and a minimal reproduction. You'll get an acknowledgement within a week, and we'll keep you updated until a fix is released. We're glad to credit you in the advisory.

## Scope

Examples of what counts: input that makes a validator hang or grow memory (ReDoS, unbounded work), results an attacker can control in ways the docs say are impossible, and anything in how the packages are built and published.
