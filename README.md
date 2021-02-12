# @jcoreio/semantic-release-monorepo

[![CircleCI](https://circleci.com/gh/jcoreio/semantic-release-monorepo.svg?style=svg)](https://circleci.com/gh/jcoreio/semantic-release-monorepo)
[![Coverage Status](https://codecov.io/gh/jcoreio/semantic-release-monorepo/branch/master/graph/badge.svg)](https://codecov.io/gh/jcoreio/semantic-release-monorepo)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![npm version](https://badge.fury.io/js/%40jcoreio%2Fsemantic-release-monorepo.svg)](https://badge.fury.io/js/%40jcoreio%2Fsemantic-release-monorepo)

`semantic-release-monorepo` determines which commits apply to a given packages by seeing if they touched files in that package.

This fork instead uses only the commit messages to determine which packages are affected. In accordance with `cz-lerna-changelog`,
the fork in this folder looks for a line in the commit message like

```
affects: @jcoreio/license-api, @jcoreio/license-api-backend
```

This is for special cases where the packages to publish are built by scripts in such a way that looking at which files were affected by a commit can't always determine which packages were actually affected.

# Usage

Run `semantic-release` in the **root of a monorepo package** and apply `@jcoreio/semantic-release-monorepo` via the [`extends`](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md#extends) option.

On the command line:

```bash
$ npm run semantic-release -e @jcoreio/semantic-release-monorepo
```

Or in the [release config](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md#configuration-file):

```json
{
  "extends": "@jcoreio/semantic-release-monorepo"
}
```
