# Python Virtual Environment

See [venv documentation](https://docs.python.org/3/tutorial/venv.html).

## Initialize

Create a virtual environment in folder (e.g. `.venv`)

```sh
cd PROJECT_DIR
python -m venv .venv
```

Activate this virtual environment

- Linux/MacOS: `source .venv/bin/activate`
- Windows: `.venv\Scripts\activate.bat`

Manage Pip packages inside the virtual environment

```sh
pip install -r requirements.txt
pip show PACKAGE_NAME
```
