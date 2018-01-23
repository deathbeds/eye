
`eye` imports notebooks as Interactive Modules.  With `eye` imports:

* Notebooks can be used as python source.
* The native `importlib.reload` object reloads `eye` modules.
* `eye` provides line level debugging to the source notebook.
* `paramterize` notebooks to makes them `callable`.


```python
    import eye.activate
    import readme
```

Imported notebooks are reloadable.


```python
    from importlib import reload
    assert reload(readme) is readme
```

The [`eye/tests`](eye/tests/) explains more about the basic and advanced features of `eye` 

> `eye.tests` are importable.


```python
    import eye.tests.test_basics
    assert eye.tests.test_basics.__complete__ is True
```

Partially loaded notebooks contain an `Exception` on the __complete__ attribute.


```python
    import eye.tests.debug
    assert type(eye.tests.debug.__complete__) is AssertionError
```


```python
    if __name__ == '__main__':
    #     !source activate p6 && python setup.py develop
        !source activate p6 && python setup.py pytest
        !jupyter nbconvert --to markdown --TemplateExporter.exclude_output=True readme.ipynb
```
