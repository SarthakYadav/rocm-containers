## Latest PyTorch (2.1.x) with ROCm 5.6.1

Essentially setting up a [miniconda](https://docs.conda.io/projects/miniconda/en/latest/) environment using the official [rocm ubuntu-22.04](https://hub.docker.com/r/rocm/dev-ubuntu-22.04) docker image. Add/remove frameworks as necessary.

### Instructions

1. Build docker image
```
sudo docker build --ulimit nofile=65536:65536 --shm-size=2g --ulimit stack=67108864 -t ubuntu-22.04-rocm-5.6.1-torch-2.1 -f BaseDockerfile .
```

2. If you need a singularity image (.sif file) for running on clusters, run the following
```
sudo singularity build ubuntu-22.04-rocm-5.6.1-torch-2.1.sif singularity.def
```

This is confirmed to run on MI250x GPUs, supporting Multi-GPU and mixed-precision training.
