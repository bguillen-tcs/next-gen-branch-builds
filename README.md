# Next Gen Branch Builds

## Description

Project used to explore how we can leverage [Netlify](https://www.netlify.com/) to automate the builds for our branches in and out of pull requests.

## Why

We want to explore this to get a better idea of how we want to build static sites within our workflows moving forward.  Essentially, **we just want to map out the options available and then be able to choose what works best for us, as we get started with Next Gen.**

## How

To explore this, we will be looking at two approaches:

1. Initially, we will be leveraging Netlify's build hook (i.e. on every push)
2. Second, we will look at using a GH Workflow to deploy by using the [Netlify Deploy](https://github.com/marketplace/actions/netlify-deploy) Action; this'll help give us more control over when to build (i.e. run tests after build is successful or run tests before building application)

The reason both will be looked at is that we want to build incrementally.  I've personally never tried branched builds on Netlify.

This is why, first, getting branched builds to work on every push would be valuable to ensure the branch is building successfully.  Then, we could go ahead and automate that another way via the GH workflow to see what that looks like.

## Use Cases Considered

* Developer wants to build `master`
* Developer wants to build `master` on merge
* Developer wants to build `master` on merge and run tests after
* Developer wants to build some branch (e.g. `feature/some-widget`) before opening PR
* Developer wants to build some branch after opening PR (i.e. on push)
* Developer wants to build some branch before opening PR, and then run tests
* Developer wants to build some branch after opening PR, and then run tests