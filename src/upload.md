# How to upload to PyPi

1. go to root directory
2. `python3 -m pip install --user --upgrade setuptools wheel twine`
3. `python3 setup.py sdist bdist_wheel`
4. `python3 -m twine upload dist/*`
