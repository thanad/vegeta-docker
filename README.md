# Vegeta Docker
[![](https://images.microbadger.com/badges/image/peterevans/vegeta.svg)](https://microbadger.com/images/peterevans/vegeta)
[![CircleCI](https://circleci.com/gh/peter-evans/vegeta-docker/tree/master.svg?style=svg)](https://circleci.com/gh/peter-evans/vegeta-docker/tree/master)

Docker image for the [Vegeta](https://github.com/tsenart/vegeta) HTTP load testing tool.

## Supported tags and respective `Dockerfile` links

- [`6.9.1`, `6.9`, `latest`, `6.9.1-vegeta12.8.4`, `6.9-vegeta12.8.4`, `latest-vegeta12.8.4`  (*6.9/Dockerfile*)](https://github.com/peter-evans/vegeta-docker/tree/v6.9.1)
- [`6.9.0`, `6.9.0-vegeta12.8.3`, `6.9-vegeta12.8.3`, `latest-vegeta12.8.3`  (*6.9/Dockerfile*)](https://github.com/peter-evans/vegeta-docker/tree/v6.9.0)
- [`6.8.1`, `6.8`, `6.8.1-vegeta12.8.3`, `6.8-vegeta12.8.3`,  (*6.8/Dockerfile*)](https://github.com/peter-evans/vegeta-docker/tree/v6.8.1)
- [`6.7.0`, `6.7`  (*6.7/Dockerfile*)](https://github.com/peter-evans/vegeta-docker/tree/v6.7.0)
- [`6.6.0`, `6.6`  (*6.6/Dockerfile*)](https://github.com/peter-evans/vegeta-docker/tree/v6.6.0)
- [`6.5.0`, `6.5`  (*6.5/Dockerfile*)](https://github.com/peter-evans/vegeta-docker/tree/v6.5.0)

For earlier versions see [releases](https://github.com/peter-evans/vegeta-docker/releases) and the available [tags on Docker Hub](https://hub.docker.com/r/peterevans/vegeta/tags/).

## Usage

To display help:
```bash
docker run --rm -i thanad/vegeta-docker
```
Example:
```bash
docker run --rm -i thanad/vegeta-docker sh -c \
"echo 'GET https://www.example.com' | vegeta attack -rate=10 -duration=30s | tee results.bin | vegeta report"
```
For full documentation see [Vegeta](https://github.com/tsenart/vegeta).

## Usage in Kubernetes

To display help:
```bash
kubectl run vegeta --rm --attach --restart=Never --image="thanad/vegeta-docker"
```
Example:
```bash
kubectl run vegeta --rm --attach --restart=Never --image="thanad/vegeta-docker" -- sh -c \
"echo 'GET https://www.example.com' | vegeta attack -rate=10 -duration=30s | tee results.bin | vegeta report"
```

## License

MIT License - see the [LICENSE](LICENSE) file for details
