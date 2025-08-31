# ComfyUI & SageAttention Setup on Windows

This document provides a step-by-step guide for accessing the ComfyUI Python environment, installing required libraries (such as Triton), enabling Sage Attention in ComfyUI, and addressing Windows-specific issues.


## Table of Contents
1. [Install steps](#install-steps)
2. [Understanding Python Virtual Environments](#understanding-python-virtual-environments)
3. [Checking Installed Versions](#checking-installed-versions)
4. [Best Practices](#best-practices)

---

## Install steps 

1. Navigate to your ComfyUI folder via  command line / terminal:

```cmd
#Example: cd C:\Users\Joe\Documents\ComfyUI

cd <your ComfyUI directory>
```

2. Activate the virtual environment:

    _Note: To check whether you are in the environment you might see (in your terminal) some prefix in parenthesis such as:
    (ComfyUI) C:\Users\Joe\Documents\ComfyUI>_

```cmd
.venv\Scripts\activate
```

3. Install triton (download it from this repo) based on your Python version
- If you are on Python 3.12 (on ComfyUI environment)
    ```
    python -m pip install triton_windows-3.4.0.post20-cp312-cp312-win_amd64.whl
    ```
- If you are on Python 3.12 (on ComfyUI environment)
    ```
    python -m pip install triton_windows-3.4.0.post20-cp312-cp312-win_amd64.whl
    ```
    For more information about these `.whl` packages and other versions check [this link](https://pypi.org/project/triton-windows/#files) 
    **(Author: Philippe Tillet, Dian Wu)**

4. Once done with Triton installation (required for Sage Attention) you can then install sageattention following the steps in [this repository](https://github.com/thu-ml/SageAttention?tab=readme-ov-file) for the latest updates or simply use the V1:
   ```
   python -m pip install sageattention==1.0.6
   ```


## Understanding Python Virtual Environments (Nice to know)

- (✅ This is what we want) Using `python -m pip install` ensures that **we are using pip within the desired environment (which in this case is ComfyUI)**. 
- (❌ We don't want to do this - This will install globally on your machine) Direct `pip install` can accidentally install packages in the global Python installation.

Example:

```cmd
python -m pip install <package-name>

# Assuming you are already in the desired python environment (in our case ComfyUI)
```

---

# Check where are your python executables
```cmd
where python
```
- Should return something like (in the first line):
```
<your ComfyUI directory>\.venv\Scripts\python.exe
```

## Best Practices (assumes you already in the desired environment)

- Always use `python -m pip` inside the venv.  
- Verify which Python your venv is using:

```cmd
where python
python -m pip --version
```

- Close any Python processes before installing compiled libraries.  
- Restart ComfyUI after installing SageAttention or other new packages.  

---




# Troubleshooting:
**ERROR: Could not install packages due to an OSError: [WinError 5] Access is denied: ... Check the permissions.**

Make sure you don't have ComfyUI running otherwise thie error may occur.

**In ComfyUI, errors regarding CUDA are popping up** 

Assuming you are using NVIDA GPU you might have to install the CUDA Toolkit. Take a look at this link ComfyUI might fail after installation, missing CUDA. Go ahead and install [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit)


