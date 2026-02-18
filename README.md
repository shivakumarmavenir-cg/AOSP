AOSP Pipeline Documentation

AOSP CI Pipeline Guide

This document describes a complete CI/CD pipeline setup for building AOSP using GitLab CI, along with Jenkins and GitHub Actions alternatives. It includes best practices for Docker-based builds, caching, reproducibility, signing, and artifact handling.

1. Goals
- Deterministic builds with manifests
- Fast iterations using cache and incremental workspace reuse
- Parallel builds across product targets
- Traceable artifacts and metadata
- Secure optional signing

2. Prerequisites
- 16–32 CPU cores, 64–128 GB RAM, 500GB–1TB NVMe disk
- Docker image containing AOSP dependencies
- Access tokens for private manifests
- Optional signing keys for release builds

3. GitLab CI Pipeline (.gitlab-ci.yml)
Includes stages for prepare, sync, build (matrix), package, sign, and publish. Uses ccache and incremental workspace artifacts.

4. Jenkinsfile Alternative
A parallel matrix build configuration suitable for Jenkins.

5. GitHub Actions Alternative
Self-hosted runner workflow for AOSP builds.

6. Local Manifests Example
Example XML snippet for device/vendor/kernel repositories.

7. Performance Tips
- Enable large ccache (100–200GB)
- Use repo sync optimizations
- Use NVMe storage
- Use hermetic Docker builds



