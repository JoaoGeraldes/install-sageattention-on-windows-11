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
