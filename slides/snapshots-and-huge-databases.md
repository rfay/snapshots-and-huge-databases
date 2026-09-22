# **DDEV Databases: Snapshots and Image Packaging for Huge Databases**

![DDEV Logo](images/ddev-logo.svg)

---

## Agenda

- [ ] Start recording
- [ ] Moshe: the story of the problem you've been solving all these years, and how

---

## The Problem: Big Databases

- [ ] Problem with big databases (local development and CI/testing)
- [ ] Alternatives: reduce the database for this reason

---

## Snapshots

- [ ] Snapshots, seed (demo seed)
- [ ] `ddev pull`
- [ ] Compressed vs uncompressed snapshots

---

## Images with Baked-In Snapshots

- [ ] Images with baked snapshots
- [ ] Example: [weitzman/dbimage](https://github.com/weitzman/dbimage) — DDEV DB image with data baked in
  - Daily GitHub Actions workflow builds and publishes the image to GHCR
  - `.ddev/commands/web/pulldb` and `resetdb` convenience commands
  - `.ddev/config.yaml` wired to use the built image
- [ ] Alternate: build a seeded image from a snapshot — [build-and-push-seeded-image.sh](https://github.com/rfay/database-performance/blob/main/scripts/build-and-push-seeded-image.sh)

---

## Demonstration

- [ ] Demonstration GitHub Action
- [ ] Moshe: actual demo
- [ ] Show the action running
- [ ] Show real situation

