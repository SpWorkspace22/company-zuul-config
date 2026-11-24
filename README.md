# Company Zuul Configuration

## Purpose

This repository contains the centrally managed Zuul configuration
for the company's CI/CD environment.

It is maintained by the Platform Engineering team.

## Responsibilities

The central configuration controls:

- Company-wide Zuul pipeline definitions.
- Mandatory CI policies.
- Reusable project templates.
- Application project matching.
- Centrally approved policy exceptions.

## Repository Architecture

The company CI architecture uses three separate repositories.

| Repository | Responsibility |
|---|---|
| company-zuul-config | Central pipelines, policies and project templates |
| company-ci-jobs | Reusable CI job definitions and implementations |
| payment-service | Application source code and application-owned Zuul configuration |

## Pipeline Ownership

The Platform Engineering team defines and maintains the
company-wide `check` and `gate` pipelines.

Application teams cannot create or modify pipeline definitions.

Application teams use their own `.zuul.yaml` files to select
application-specific jobs for the existing pipelines.

## Mandatory CI Policies

Company-wide mandatory jobs, such as code quality and security
scanning, are centrally managed.

Application teams cannot independently remove mandatory policies.
Exceptions require approval from the Platform Engineering team.

## Trust Model

This repository is intended to be registered as a trusted
configuration project in the Zuul tenant.

Changes to this repository are controlled by the Platform
Engineering team.

## Related Repositories

- company-ci-jobs
- payment-service
