# Troubleshooting:
**ERROR: Could not install packages due to an OSError: [WinError 5] Access is denied: ... Check the permissions.**

Make sure you don't have ComfyUI running otherwise thie error may occur.

**In ComfyUI, errors regarding CUDA are popping up** 

Assuming you are using NVIDA GPU you might have to install the CUDA Toolkit. Take a look at this link ComfyUI might fail after installation, missing CUDA. Go ahead and install [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit)
