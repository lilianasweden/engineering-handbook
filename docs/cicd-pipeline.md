# CI/CD Pipeline Guide

## Overview
Our CI/CD pipeline is built on GitHub Actions and deploys to AWS via Terraform.
All services go through: build → test → staging → production.

## Pipeline Stages

### 1. Build
- Triggered on every push and on pull requests to `main`
- Docker images tagged with commit SHA
- Target: under 5 minutes

### 2. Automated Tests
- Unit tests (Jest / pytest) — 90%+ coverage required
- Integration tests run against staging database
- Security scan via Snyk on every PR

### 3. Staging Deployment
- Automatic on merge to `main`
- Smoke tests run after deploy
- URL: staging.internal

### 4. Production Deployment
- Manual approval from a senior engineer or team lead
- Blue/green deployment — zero downtime
- Rollback via `/rollback` Slack command in **#deployments**

## Current Status
~150 deployments/week. 99.4% success rate.
Average time merge → production: **12 minutes**.

## Common Issues

### Build fails on Docker layer cache miss
Run `make clean-cache` and re-push.

### Staging tests flaky on DB connections
Known issue — see Issue #3. Workaround: re-run the failed job.

### Production deploy pending approval >1h
Ping **#deployments** on Slack. Approvers: @tech-leads.
