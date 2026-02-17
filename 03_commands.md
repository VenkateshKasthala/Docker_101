# Docker Hands-on

Interaction with Docker happens through the Terminal via the **Docker CLI**. Commands are sent to the **Docker Daemon**, which manages the lifecycle of images and containers.

## Essential Commands

* **docker pull [image]:** Downloads an image from Docker Hub to the local machine without running it.
* **docker images:** Lists all images currently stored on the local disk. Shows the Repository, Tag, and Image ID.

### Container Lifecycle

* **docker run [image]:** The most common command. It combines `docker pull` (if missing), `docker create`, and `docker start`.
* **docker ps:** Displays a table of all containers currently **running**.
* **docker ps -a:** Displays **all** containers, including those that have exited or stopped. Essential for cleaning up.
* **docker stop [container_id]:** Sends a shutdown signal to a running container.
* **docker rm [container_id]:** Deletes a stopped container.
* *Note: You cannot delete a container while it is still running.*

## The "Run" Process

When `docker run` is executed:

1. Docker checks the local **Image Cache**.
2. If the image is missing, it performs a **Pull** from the Registry.
3. It creates a new **Writeable Layer** on top of the read-only image.
4. It starts the container's primary process.

## Key Takeaways

* **Images vs. Containers:** `docker images` shows what you've downloaded; `docker ps` shows what is actually active.
* **Cleanup:** Containers stay on the system in an "Exited" state after they finish. They must be removed with `docker rm` to free up resources.
* **IDs and Names:** Every container gets a unique ID (e.g., `d1f2...`) and a random name (e.g., `determined_hopper`). Either can be used to stop or remove them.
