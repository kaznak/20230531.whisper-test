# Whisper test

Whisper installation on WSL2

## Prerequests

### ffmpeg

```
sudo apt install ffmpeg
```

### NVIDIA CUDA

refer https://docs.nvidia.com/cuda/wsl-user-guide/index.html

```
sudo apt-key del 7fa2af80
wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.0-1_all.deb
sudo apt install ./cuda-keyring_1.0-1_all.deb
sudo apt update
sudo apt install cuda-11-7
```

### NVIDIA cuDNN

refer https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html

Debian local installation

cuDNN for CUDA11.x

```
sudo apt install ./cudnn-local-repo-ubuntu2004-8.9.1.23_1.0-1_amd64.deb
sudo cp /var/cudnn-local-repo-ubuntu2004-8.9.1.23/cudnn-local-D953484A-keyring.gpg /usr/share/keyrings/
sudo apt update
sudo apt install libcudnn8{,-dev,-samples}=8.9.1.23-1+cuda11.8
```

cuDNN for CUDA12.x

```
sudo apt install ./cudnn-local-repo-ubuntu2004-8.9.1.23_1.0-1_amd64.deb
sudo cp /var/cudnn-local-repo-ubuntu2004-8.9.1.23/cudnn-local-A9C84908-keyring.gpg /usr/share/keyrings/
sudo apt update
sudo apt install libcudnn8{,-dev,-samples}=8.9.1.23-1+cuda12.1
```

### NCCL: NVIDIA Collective Communication Library

refer https://docs.nvidia.com/deeplearning/nccl/install-guide/index.html

choose `Download NCCL 2.18.1, for CUDA 11.0, May 4th, 2023`, then `O/S agnostic local installer`.

GNU stow is useful for installation
