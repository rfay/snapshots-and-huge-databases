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
- Compressed and uncompressed snapshots

---

## The Magic Snapshot Named "seed"

Normally DDEV starts with a built-in snapshot in the stock DB docker image. But it has no tables or content.

But you can `ddev snapshot --name=seed` and that snapshot will be used instead in the future. 

This means an "empty" or fresh project will always start with that seed.

It can even be checked in.

---

## `ddev pull <whatever>`

Don't forget about custom `ddev pull`, which can easily pull a DB dump or snapshot, files, and can check a cached value before downloading

---

## Images with Baked-In Snapshots

- Moshe has been working with images with baked-in snapshots for years. Now it's a DDEV feature.
- Advantages: Distribution, CI, etc

---

## Example: `dbimage`

[weitzman/dbimage](https://github.com/weitzman/dbimage) — DDEV DB image with data baked in

- Daily GitHub Actions workflow builds and publishes the image to GHCR
- `.ddev/commands/web/pulldb` and `resetdb` convenience commands
- `.ddev/config.yaml` wired to use the built image

---

## Alternate: Build Your Own

Build a seeded image directly from a snapshot:

[build-and-push-seeded-image.sh](https://github.com/rfay/database-performance/blob/main/scripts/build-and-push-seeded-image.sh)

---

## Demonstration

- Show the GitHub Action
- Show the action running
- Show real situation

---

## Resources

- These [slides](https://rfay.github.io/snapshots-and-huge-databases/) and their [repo](https://github.com/rfay/snapshots-and-huge-databases)
- Script: [build-and-push-seeded-image.sh](https://github.com/rfay/database-performance/blob/main/scripts/build-and-push-seeded-image.sh)
- Repo: [weitzman/dbimage](https://github.com/weitzman/dbimage)
- Blog: [DDEV Snapshots: Checkpoints, Restores, and Seeded Databases](https://ddev.com/blog/ddev-snapshots/)
- Docs: [Database Management](https://docs.ddev.com/en/stable/users/usage/database-management/)
- Docs: [Hosting Provider Integration (`ddev pull`)](https://docs.ddev.com/en/stable/users/providers/)
- Example Drupal11 demo_umami database images in several forms: [huge compressed](https://hub.docker.com/r/randyfay/compressed-2g/tags), [huge uncompressed](https://hub.docker.com/r/randyfay/uncompressed-2g/tags), [ordinary demo_umami install](https://hub.docker.com/r/randyfay/d11_normal/tags)

