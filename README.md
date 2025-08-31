# ComfyUI & SageAttention Setup on Windows

This document provides a step-by-step guide for accessing the ComfyUI Python environment, installing required libraries (such as Triton), enabling Sage Attention in ComfyUI, and addressing Windows-specific issues.


## Table of Contents
1. [Install steps](#install-steps)
2. [Understanding Python Virtual Environments](PYTHON_ENV_VAR.md)
3. [Best Practices](#best-practices)
4. [Troubleshooting](TROUBLESHOOTING.md)

---

## 🚀 Install steps 

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

## 💡 Best Practices (assumes you already in the desired environment)

- Always use `python -m` prefix inside the environment to prevent using `pip` or `python` on the global scope (machine).  
- Verify which Python your environment is using:
- Close any Python processes before installing compiled libraries.  
- Restart ComfyUI after installing SageAttention or other new packages.  




