# Docker Playground

A simple repository for learning and experimenting with **Docker** concepts, commands, and containerized applications.

## Tech Stack

* Docker
* Docker Compose (where applicable)

## Getting Started

### Build an image

```bash
docker build . -t <app-name>
```

### Run a container

```bash
docker run -p 3000:3000 <app-name>
```

### Using Docker Compose (if available)

```bash
docker compose up
```