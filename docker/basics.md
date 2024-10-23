# Docker Basics

Docker is used to run virtual containers that have a virtual operating system
as base to run commands from. The goal is to have a consistent environment
amongst different machines.

(Add more content here)

## Some concepts

(Explain images, containers, dockerfiles, docker compose, etc)

## Some commands

(Add some commands here later)

## Commands that have been used

1. To build and run frontend:

```bash
docker build -t interncomp-frontend -f Dockerfile.dev .
docker run interncomp-frontend
```

2. To run docker-compose:

```bash
docker compose -f docker-compose.dev.yml up
```

Use `docker compose -f docker-compose.dev.yml down` if needed.

3. Cleanup

`docker image rm interncomp-platform-backend interncomp-platform-frontend postgres:15-alpine`