# Virtualenv in Python


# 1. Introduction

Python projects often require different versions of packages.

Example:

* Project A requires:

  * Django 3.2
* Project B requires:

  * Django 5.0

Installing both globally can create conflicts.

To solve this problem, Python provides **virtual environments**.

A virtual environment creates an isolated Python workspace for each project.

---

# 2. What is a Virtual Environment?

A **virtual environment** is an isolated directory containing:

* A separate Python interpreter
* Separate installed packages
* Independent package management

It prevents dependency conflicts between projects.

---

# 3. Why Virtual Environments are Important

Without virtual environments:

* Global Python becomes messy
* Package versions conflict
* Projects break unexpectedly
* Reproducibility becomes difficult

With virtual environments:

* Each project has isolated dependencies
* Cleaner system Python installation

---

# 4. Understanding Environment Variables

Environment variables are key-value pairs maintained by the shell and operating system.

Examples:

```bash
HOME=/home/vikas
USER=vikas
PATH=/usr/bin:/bin:/usr/local/bin
```

They influence program behavior---

# 5. Understanding `$PATH`

`$PATH` is one of the most important environment variables.

It contains directories where the shell searches for executables.

Example:

```bash
echo $PATH
```

Output:

```bash
/usr/local/bin:/usr/bin:/bin
```

---

# 6. The `printenv` Command

The `printenv` command prints environment variables.

Syntax:

```bash
printenv
```

Example output:

```bash
HOME=/home/vikas
USER=vikas
PATH=/usr/local/bin:/usr/bin:/bin
SHELL=/bin/bash
```

Print a specific variable:

```bash
printenv PATH
```

Equivalent:

```bash
echo $PATH
```

---

# 7. The `source` Command

The `source` command executes a script in the current shell.

Syntax:

```bash
source filename
```

Example:

```bash
source venv/bin/activate
```

---

# 8. Installing `virtualenv`

Python provides two major tools:

* `venv` (built into Python 3)
* `virtualenv` (external package)

Install virtualenv:

```bash
pip install virtualenv
```

Verify:

```bash
virtualenv --version
```

---

# 9. Complete Lifecycle of a Virtual Environment

---

# Step 1 — Create Project Directory

```bash
mkdir myproject
cd myproject
```

---

# Step 2 — Create Virtual Environment

Using `venv`:

```bash
python3 -m venv venv
```

Using `virtualenv`:

```bash
virtualenv venv
```

This creates a directory named `venv`.

---

# Step 3 — Examine Directory Structure

```bash
tree venv
```

Typical structure:

```text
venv/
├── bin/
├── include/
├── lib/
├── pyvenv.cfg
```

---

# Step 4 — Activate Virtual Environment

Linux/macOS:

```bash
source venv/bin/activate
```

---

# Step 5 — Observe Shell Changes

Before activation:

```bash
which python
```

Output:

```bash
/usr/bin/python
```

After activation:

```bash
which python
```

Output:

```bash
/home/vikas/myproject/venv/bin/python
```

Shell prompt changes:

```bash
(venv) vikas@linux:~/myproject$
```

---

# Step 6 — Check Environment Variables

Before activation:

```bash
printenv VIRTUAL_ENV
```

Output:

```bash
(no output)
```

After activation:

```bash
printenv VIRTUAL_ENV
```

Output:

```bash
/home/vikas/myproject/venv
```

---

# Step 7 — Observe `$PATH` Modification

Before activation:

```bash
echo $PATH
```

Example:

```bash
/usr/local/bin:/usr/bin:/bin
```

After activation:

```bash
echo $PATH
```

Example:

```bash
/home/vikas/myproject/venv/bin:/usr/local/bin:/usr/bin:/bin
```

Notice:

```text
venv/bin
```

is added at the beginning of `$PATH`.

This causes shell to prioritize:

```bash
venv/bin/python
venv/bin/pip
```

instead of global executables.

---

# Step 8 — Install Packages

Example:

```bash
pip install requests
```

Installed only inside virtual environment.

Check:

```bash
pip list
```

---

# Step 9 — Freeze Dependencies

```bash
pip freeze > requirements.txt
```

Example output:

```text
requests==2.32.0
urllib3==2.2.1
```

---

# Step 10 — Deactivate Environment

```bash
deactivate
```

Effects:

* Removes virtual environment from `$PATH`
* Removes `VIRTUAL_ENV`
* Restores original shell state

---

# Step 11 — Delete Environment

Virtual environments are disposable.

Delete simply by removing directory:

```bash
rm -rf venv
```

---

# 10. Internal Structure of a Virtual Environment

## `bin/`

Contains executables:

```text
python
pip
activate
```

---

## `lib/`

Contains installed packages.

Example:

```text
site-packages/
```

---

## `include/`

Contains C headers.

Useful for compiling extensions.

---

## `pyvenv.cfg`

Configuration file.

Example:

```text
home = /usr/bin
include-system-site-packages = false
version = 3.12.0
```

---

# 11. How Activation Changes `$PATH`

The activation script temporarily modifies environment variables.

Main modification:

```bash
export PATH="/path/to/venv/bin:$PATH"
```

This prepends virtual environment binaries.

---

## PATH Resolution Example

Suppose:

```bash
PATH=/usr/bin:/bin
```

After activation:

```bash
PATH=/home/vikas/project/venv/bin:/usr/bin:/bin
```

Now when shell searches for `python`:

1. Checks `venv/bin`
2. Finds virtual environment Python
3. Stops searching

This mechanism powers isolation.

---

# 12. Environment Variables Modified by Virtualenv

---

## `VIRTUAL_ENV`

Points to active virtual environment.

Example:

```bash
/home/vikas/project/venv
```

---

## `PATH`

Modified to prioritize virtual environment executables.

---

## `PS1`

Shell prompt modified.

Example:

```bash
(venv)
```

added to prompt.

---

# 13. `venv` vs `virtualenv`

| Feature                   | `venv`   | `virtualenv` |
| ------------------------- | -------- | ------------ |
| Built into Python         | Yes      | No           |
| Speed                     | Moderate | Faster       |



---

# 14. Common Commands

## Create

```bash
python3 -m venv venv
```

---

## Activate

```bash
source venv/bin/activate
```

---

## Deactivate

```bash
deactivate
```

---

## Remove

```bash
rm -rf venv
```

---

## Install Package

```bash
pip install flask
```

---

## Save Dependencies

```bash
pip freeze > requirements.txt
```

---

## Install From Requirements

```bash
pip install -r requirements.txt
```

---

# 15. Best Practices

---

## Use `.gitignore`

Never commit virtual environments.

`.gitignore`:

```gitignore
venv/
```

---

## Always Use Requirements File

```bash
pip freeze > requirements.txt
```

---

## One Environment Per Project

Avoid sharing environments.


---

# 16. Real Project Workflow

## Create Project

```bash
mkdir flask_app
cd flask_app
```

---

## Create Environment

```bash
python3 -m venv venv
```

---

## Activate

```bash
source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install flask
```

---

## Save Requirements

```bash
pip freeze > requirements.txt
```

---

## Work on Project

```bash
python app.py
```

---

## Exit Environment

```bash
deactivate
```

---

# 17. Conclusion

Virtual environments are fundamental to professional Python development.

Key concepts:

* `virtualenv` creates isolated Python environments
* `source` executes activation script in current shell
* `$PATH` determines executable resolution
* `printenv` helps inspect environment variables
* `deactivate` restores original shell state


