# Small size nghttp2 Docker image

Small size (11MB) Docker image for [nghttp2](https://nghttp2.org/).

It has the latest version of nghttp2 (v1.42.0).

## Why this image is better than other images:

[centminmod/docker-ubuntu-nghttp2-minimal](https://github.com/centminmod/docker-ubuntu-nghttp2-minimal) and [svagi/nghttp2](https://hub.docker.com/r/svagi/nghttp2) has older versions of nghttp2.

[centminmod/docker-ubuntu-nghttp2](https://github.com/centminmod/docker-ubuntu-nghttp2) is updated but is hugh (5.88GB).

I needed h2load with the arg `--connect-to` that was added in v1.40.0.
So I created this image.

I only tested it with h2load.

Location in Docker Hub: <https://hub.docker.com/r/erezarbell/nghttp2>

## Usage:
```
docker run --rm erezarbell/nghttp2 h2load ...
```
