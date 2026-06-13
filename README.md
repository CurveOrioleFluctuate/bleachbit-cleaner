# BleachBit

BleachBit is a system cleaner for Windows and Linux. This repository contains files used for building BleachBit packages with the Open Build Service (OBS), with a focus on Debian and Ubuntu package workflows.

[Download]()

## Overview

This repository is not a general application source tree. It mirrors packaging-related files used to build BleachBit packages through OBS.

The documented workflow uses the `osc` command-line tool to:

- check out package files from OBS
- compare OBS files with this repository
- run local package builds
- branch the OBS package for test builds
- inspect build results and logs

## Package Build Workflow

The packaging workflow is centered on Open Build Service.

Typical tasks include:

- installing and configuring `osc`
- checking out the OBS package working copy
- comparing local packaging files against OBS
- running a local build for a configured distribution target
- branching the package for testing
- reviewing build status and build logs

Example OBS targets referenced by the existing workflow include Ubuntu-based build names such as `xUbuntu_20.10`, `xUbuntu_20.04`, and `xUbuntu_18.04`.

## Main Capabilities

This repository is useful for maintainers working with BleachBit package builds because it provides a place to track packaging files related to OBS.

Supported maintenance activities include:

- Debian/Ubuntu package build preparation
- local package build testing through `osc`
- OBS package branching for experimental builds
- build status inspection
- build log review

## Windows and Linux Context

BleachBit itself is described as a system cleaner for both Windows and Linux. This repository, however, documents packaging activity for Debian and Ubuntu builds through OBS.

For Windows users, BleachBit remains relevant as a Windows system cleaner and desktop utility. For maintainers, this repository is specifically about package build files and OBS-based Linux packaging workflows.

## Getting Started

To work with the OBS packaging workflow, install the `osc` tool and use an OBS account. The package workflow includes checking out the OBS package, comparing files, and running builds for configured repositories.

Common commands used in this workflow include:

```bash
osc checkout home:andrew_z bleachbit -o /tmp/obsfiles
diff -u3 /tmp/obsfiles .
```

A local build can be started from an `osc` checkout:

```bash
osc build xUbuntu_20.10
```

A package branch for testing can be created with:

```bash
osc branch home:andrew_z bleachbit
```

Build status and logs can be inspected with:

```bash
osc results
osc buildlog xUbuntu_20.10
```

## FAQ

### What is this repository for?

It contains files used for building BleachBit packages with Open Build Service.

### Is this the BleachBit application source code?

The available documentation describes this directory as a mirror of package build files, not as the main application source tree.

### Is BleachBit for Windows?

BleachBit is described as a system cleaner for Windows and Linux. This repository’s documented workflow focuses on Debian and Ubuntu package builds.

### What tool is used for the package workflow?

The documented package workflow uses `osc`, the Open Build Service command-line tool.

### What distributions are referenced?

The existing workflow references Ubuntu-style OBS build targets such as `xUbuntu_20.10`, `xUbuntu_20.04`, and `xUbuntu_18.04`.

## Summary

This repository tracks OBS packaging files for BleachBit, a system cleaner for Windows and Linux. It is primarily useful for maintainers working on Debian and Ubuntu package builds through Open Build Service.
