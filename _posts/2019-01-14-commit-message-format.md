---
title:  "Commit message format"
date:   2019-01-14 03:57:00
categories: Software-Engineering
summary: Commit message format
---

Each commit message consists of a **header**, a **body** and a **footer**. The header has a special format that includes
a **type**, an _optional_ **scope** (_when applicable_) and a **subject**:

#### Without scope

```
<type>: <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

#### With scope

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer 100 characters. This allows the message to be easier to read on GitHub as
well as in various git tools.

Footer should contain a [closing reference to an issue](https://help.github.com/articles/closing-issues-using-keywords/)
if any.

Samples:

```
docs(changelog): update change log to alpha.9
```

```
fix(release): need to depend on package

The version in our package.json gets copied to the one we publish, and users need the latest of these.
```

### Revert

If the commit reverts a previous commit, it should begin with `revert:`, followed by the header of the reverted commit.
In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Type

Must be one of the following: _build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test_

- **build**: Changes that affect the build system or external dependencies (example scopes: gulp, npm, webpack)
- **chore**: Chore
- **ci**: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, etc)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **revert**: Revert change
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- **test**: Adding missing tests or correcting existing tests

### Subject

The subject contains succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- don't capitalize first letter
- no dot (.) at the end

### Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes". The body should include
the motivation for the change and contrast this with previous behavior.

### Footer

The footer should contain any information about **Breaking Changes** and is also the place to reference GitHub issues that
this commit **Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit
message is then used for this.

---
> Good, better, best. Never let it rest. 'Til your good is better and your better is best.
> <small>- [St. Jerome](https://www.brainyquote.com/quotes/st_jerome_389605)</small>