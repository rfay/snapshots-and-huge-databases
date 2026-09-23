# **DDEV Databases: Snapshots and Image Packaging for Huge Databases**

![DDEV Logo](images/ddev-logo.svg)

---

## Agenda

- Start recording
- Basics of DB management: `ddev import-db`, `ddev snapshot`, `ddev snapshot restore`
- New: "seed" snapshots
- Moshe: distributing databases for CI and local in Docker images

---

## The Problem: Big Databases

- Problem with big databases (local development and CI/testing)
  - Download takes too long
  - Loading takes too long
  - People rarely get around to building a proper minify script

---

## Snapshots

- Basic demo: `ddev snapshot`, `ddev snapshot restore`
- Compressed vs uncompressed snapshots

---

## `ddev pull <whatever>`

- Don't forget about custom `ddev pull`, which can easily pull a DB dump or snapshot, files, and can check a cached value before downloading

---

## Images with Baked-In Snapshots

- Images with baked snapshots
- Example: [weitzman/dbimage](https://github.com/weitzman/dbimage) — DDEV DB image with data baked in
  - Daily GitHub Actions workflow builds and publishes the image to GHCR
  - `.ddev/commands/web/pulldb` and `resetdb` convenience commands
  - `.ddev/config.yaml` wired to use the built image
- Alternate: build a seeded image from a snapshot — [build-and-push-seeded-image.sh](https://github.com/rfay/database-performance/blob/main/scripts/build-and-push-seeded-image.sh)

---

## Demonstration

- Demonstration GitHub Action
- Moshe: actual demo
- Show the action running
- Show real situation

