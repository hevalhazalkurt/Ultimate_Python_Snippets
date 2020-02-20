# Ultimate Python Snippets
## Django
### `include()`


<br>

-----


#### What is `include()` for?



**Syntax**

```
include(module, namespace=None)
include(pattern_list)
include((pattern_list, app_namespace), namespace=None)
```

A function that takes a full Python import path to another URLconf module that should be “included” in this place. Optionally, the application namespace and instance namespace where the entries will be included into can also be specified.

Usually, the application namespace should be specified by the included module. If an application namespace is set, the `namespace` argument can be used to set a different instance namespace.

`include()` also accepts as an argument either an iterable that returns URL patterns or a 2-tuple containing such iterable plus the names of the application namespaces.



<br>

| Parameter | Default | Definition |
|--|--|--|
| `module` | | URLconf module (or module name) |
| `namespace` | `None` | Instance namespace for the URL entries being included |
| `pattern_list` | | Iterable of `path()` and/or `re_path()` instances. |
| `app_namespace` | | Application namespace for the URL entries being included
 |


**Examples**

```python
urlpatterns = [
        `path('', include(qanda.urls, namespace='qanda'))`,
        `path('', include('books.urls'))`,
]
```
