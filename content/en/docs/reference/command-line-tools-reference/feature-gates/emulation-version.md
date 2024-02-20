---
title: EmulationVersion
content_type: feature_gate
_build:
  list: never
  render: false

stages:
  - stage: alpha
    defaultValue: false
    fromVersion: "1.31"
---
Enables a `--emulated-version` command line argument for Kubernetes server components, that allows the component to emulate the behavior (APIs, features, ...) of an earlier version of Kubernetes.

When used, the capabilities available will match the emulated version. 
Any capabilities present in the binary version that were introduced after the emulation version will be unavailable. 
Any capabilities removed after the emulation version will be available. 
This enables a binary from a particular Kubernetes release to emulate the behavior of a previous version with sufficient fidelity that interoperability with other system components can be defined in terms of the emulated version.
