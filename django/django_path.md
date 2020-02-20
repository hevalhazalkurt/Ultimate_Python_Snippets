# Ultimate Python Snippets
## Django
### `path()`


<br>

-----


#### What is `path()` for?



**Syntax**

```python
path(route, view, kwargs=None, name=None)
```


Returns an element for inclusion in `urlpatterns`. For example:

```python
from django.urls import include, path

urlpatterns = [
    path('index/', views.index, name='main-view'),
    path('bio/<username>/', views.bio, name='bio'),
    path('articles/<slug:title>/', views.article, name='article-detail'),
    path('articles/<slug:title>/<int:section>/', views.section, name='article-section'),
    path('weblog/', include('blog.urls')),
    ...
]
```


The `route` argument should be a string or `gettext_lazy()` that contains a URL pattern. The string may contain angle brackets (like `<username>` above) to capture part of the URL and send it as a keyword argument to the view. The angle brackets may include a converter specification (like the `int` part of `<int:section>`) which limits the characters matched and may also change the type of the variable passed to the view. For example, `<int:section>` matches a string of decimal digits and converts the value to an `int`.

The `view` argument is a view function or the result of `as_view()` for class-based views. It can also be an `django.urls.include()`.

The `kwargs` argument allows you to pass additional arguments to the view function or method.

The `name` argument is useful.
