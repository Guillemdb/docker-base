# docker-base ![Docker Build Status](https://img.shields.io/docker/build/guillemdb/docker-base.svg) ![Docker Pulls](https://img.shields.io/docker/pulls/guillemdb/docker-base.svg)

Bleeding edge Docker image with:

- Ubuntu 18.04
- Python 3.7b3
- NVIDIA driver
- CUDA 9.2.88
- cuDNN 7.1.4.18
- Tensorflow 1.9
- Python packages (latest version to build date): numpy. scipy, keras, h5py, Pillow-simd, matplotlib, **jupyter**

The default command launches Jupyter on port 8080.

```
docker run -d -p 80:8080 guillemdb/docker-base
```

### Features

- Tensorflow is compiled during image build, easy to update
- No Python 3.6 inside the image
- Image size is as small as possible (send PRs if you know size reduction tricks which were not used!)
- Contains the minimal build environment to install further Python packages in subsequent layers

### Customization

- `JUPYTER_PASSWORD` is the security token for Jupyter, **you should change it from the default "mallorca"**!
- `NVIDIA_DRIVER_VERSION` must be set to the one your host system is running
- `CUDA_VERSION` sets the CUDA version
- `NPY_NUM_BUILD_JOBS` should be set to the number of cores in your host
- `BAZEL_VERSION` sets the version of Bazel - Tensorflow's build system
- `TENSORFLOW_BRANCH` chooses the Tensorflow version
- TODO: Python packages selection

### Contributing

Please submit PRs to improve! E.g. we can optionally switch to [nvidia-docker](https://github.com/NVIDIA/nvidia-docker).

### License

MIT.
