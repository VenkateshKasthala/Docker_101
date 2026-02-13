# Core Concepts

## The Three Pillars

Docker operates through a specific lifecycle: **Dockerfile → Image → Container**.

### Dockerfile (The Recipe)

A plain text file containing a list of instructions on how to assemble an environment. It defines the base OS, the required libraries, environment variables, and the application code.

### Image (The Snapshot)

A read-only, "frozen" file that contains the entire environment.

* Images are **immutable** (they cannot be changed once built).
* If the code or configuration changes, a new image must be built.
* Images are stored on the local disk or in a Registry.

### Container (The Process)

The active, running instance of an image.

* It is a "living" process isolated from the host machine.
* Multiple containers can run simultaneously from the same single image.
* Containers are **ephemeral**, meaning they are intended to be stopped and deleted without affecting the original image.

## Docker Architecture

* **Docker Client:** The command-line interface (CLI) used to type commands (e.g., `docker build`).
* **Docker Daemon (dockerd):** The background service that does the heavy lifting of building, running, and distributing containers.
* **Registry:** A storage system for images. **Docker Hub** is the largest public registry, allowing users to pull official images for databases, languages, and web servers.

## Analogies for Reference

| Term | Analogy |
| :--- | :--- |
| **Dockerfile** | A blueprint for a house. |
| **Image** | A standardized construction kit based on the blueprint. |
| **Container** | The actual house built from the kit where people live. |