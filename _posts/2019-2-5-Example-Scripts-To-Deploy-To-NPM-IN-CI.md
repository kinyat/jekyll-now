---
layout: post
title: Example Script to Deploy to NPM in CI
---

```sh
#!/bin/sh -xe

###
# Deploy to NPM
#
# Expecting two variables to be passed by the CI
#   1. $NPM_TOKEN contains the token for auth
#   2. $RELEASE_VERSION contains a valid version (see: https://docs.npmjs.com/cli/version.html)
#
# The whole deployment process is as following
#   1. Build project
#   2. `npm version` which will create a new tag for deployment
#   3. `npm publish` which will push files to NPM and publish a new version
#   4. Push the new tag to GitHub
###

# Build project
yarn build

# Set up environment
git config user.email "ci.bot@example.com"
git config user.name "CI BOT"

echo "//registry.npmjs.org/:_authToken=$NPM_TOKEN" > .npmrc

# Npm version and publish
npm version "$RELEASE_VERSION" -m "[ci skip] Upgrade to %s"
npm publish --access public

# Push new tags to GitHub
git remote add github "git@github.com:kinyat/example.git" || true
git push --tags github

git push github HEAD:develop
```
