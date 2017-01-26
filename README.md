[![Build Status](http://ci.sagrid.ac.za/buildStatus/icon?job=einstein-deploy)](http://ci.sagrid.ac.za/job/einstein-deploy/)
# Einstein Toolkit

A repository containing einstein toolkit installation scripts used by Jenkins.
This repository builds the einstein toolkit with various configurations.

# how to use this repo

This repo is used entirely by Jenkins to build site-specific  libraries, in order to simulate sites.
Some sites have customised TORQUEs, and we need to build flavourse of applications, such as OpenMPI, against these configurations.

# Contents of the repo
This repo contains three scripts

  1. `build.sh`
  2. `check-build.sh`
  3. `deploy.sh`

These define basically two test phases, the **build** and **functional** test phases, as well as the deploy phase respectively

## Branches

The branches track configurations of einstein toolkit. The master branch is the *vanilla* configuration.

## Build Test Phase

The build phase does the following things

  1. Set up the build environment variables
  2. Downloads the source code via multiple git clones/pulls.
  4. Compile the source into an executable form.
  5. Create a modulefile which loads the dependencies and sets the environment variables needed to execute the application.

The build phase should pass iff the expected libraries and executable files are present. **It is your responsibility to define where these files are, on a case-by-case basis**.

## Functional test phase

The test phase does the following things :

  1. Loads the modulefile created by `check-build.sh`
  2. installs the libraries into the `$SOFT_DIR` directory

# When things go wrong

If you have a legitimate error, or need support, please [open an issue](../../issues)
