# Quickstart Guides

[![Build Status](https://build.developer.rackspace.com/rackerlabs/docs-quickstart/badge?branch=master)](https://build.developer.rackspace.com/rackerlabs/docs-quickstart/)

These are the "getting started" guides from [developer.rackspace.com](https://developer.rackspace.com). They're intended to demonstrate the basic operations and flow of working with Rackspace services in each of our supported SDKs.

## Updating from Upstream

This repository has been split from [the monolithic developer.rackspace.com repository](https://github.com/rackerlabs/developer.rackspace.com) during the transition to hosting on [deconst](http://deconst.devsupport.me/). Until the transition is complete, new work not related to working on deconst should be done on the parent repository.

To bring this repository up to date, fork and clone the [the original repository](https://github.com/rackerlabs/developer.rackspace.com), then:

```bash
# Add your fork of this repository as a remote.
git remote add docs-quickstart git@github.com:${GITHUB_USERNAME}/docs-quickstart.git

# Split or re-split the quickstart directory onto its own branch.
git checkout master
git subtree split --prefix=src/docs --branch=docs-only

# Push the newly updated branch to your fork.
git checkout docs-only
git push -u docs-quickstart docs-only:upstream-update
```

Finally, open a [pull request](https://github.com/rackerlabs/docs-quickstart/compare) between the branch you just pushed and the `master` branch on this repository and merge it to complete the update.
