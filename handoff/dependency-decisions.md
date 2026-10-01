# DevPortal Dependency Decisions

## Platform

Backstage release: 1.55.3

Architecture:
- New Frontend System
- New Backend System

## GitHub

Included:
- GitHub authentication provider
- GitHub catalog discovery
- GitHub scaffolder integration
- GitHub Actions UI

## Jenkins

Included:
- Jenkins frontend plugin
- Jenkins backend plugin

## Argo CD

Included:
- Argo CD frontend plugin
- Argo CD backend plugin

Purpose:
Deployment lifecycle and deployment-status visibility.

Argo CD is not used by Backstage as an infrastructure provisioning mechanism.

## AWS

Included:
- AWS Config catalog backend module
- Incremental catalog ingestion module

Purpose:
AWS infrastructure discovery and catalog ingestion.

Infrastructure provisioning is expected to use scaffolding/IaC rather than
direct AWS Cloud Control provisioning from Backstage.

## Tech Insights

Included:
- Tech Insights frontend
- Tech Insights backend
- JSON fact checker backend module

Purpose:
Scorecards, checks, and engineering insight framework.

Tech Insights itself is not the source of DORA metrics. DORA fact sources
must be defined separately.

## JFrog Artifactory

Not installed.

Reason:
The evaluated community JFrog Artifactory plugin does not meet the target
New Frontend System architecture requirement.

JFrog remains the target package curation/artifact-management platform,
but its Backstage UI plugin is excluded from this dependency baseline.

## Toolchain Constraints

The following root Yarn resolutions are intentional toolchain dependency
constraints:

- @yarnpkg/cli = 4.18.0
- @yarnpkg/core = 4.9.1

These are not functional DevPortal capabilities.
