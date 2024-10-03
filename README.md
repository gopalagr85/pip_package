**Step 1: Create an importable module!**

Since `pip` is going to install modules that we can `import`, we need to have one ready first. Let's create `my_pip_package.py`:
```python
def hello_world():
    print("This is my first pip package!")
```
Confirm that it can be imported properly:

```bash
$ python -c "import my_pip_package; my_pip_package.hello_world()"
This is my first pip package!
```

**Step 2: Create setup.py**

```python
from setuptools import setup, find_packages

setup(
    name='custom_pip_package',
    version='1.0.0',

    url='https://github.com/gopalagr85/pip_package',
    author='Ghanshyam',
    author_email='gopalagr85@gmail.com',

    packages=find_packages(),
)
```
If you have pushed your code to a git hosting service, you should be able to install it anywhere right now:

```bash
pip install git+https://github.com/gopalagr85/pip_package.git#egg=custom_pip_package
```

