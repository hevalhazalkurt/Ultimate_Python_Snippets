# Ultimate Python Snippets
## Django
### `startproject`


<br>

-----


#### What is `startproject` for?

**Syntax**

```
django-admin startproject projectname [directory]
```

Creates a Django project directory structure for the given project name in the current directory or the given destination.


If only the project name is given, both the project directory and project package will be named `<projectname> `and the project directory will be created in the current working directory.


If the optional destination is provided, Django will use that existing directory as the project directory, and create `manage.py` and the project package within it. Use `‘.’` to denote the current working directory.


For example :

```
django-admin startproject myproject /Users/jezdez/Code/myproject_repo
```

<br>

| Parameter | Default | Definition | Example |
|--|--|--|--|
| `--template TEMPLATE` | | Specifies a directory, file path, or URL of a custom project template. | - `django-admin startapp --template=/Users/jezdez/Code/my_app_template myapp` <br> - `django-admin startapp --template=https://github.com/githubuser/django-app-template/archive/master.zip myapp`|
| - `--extension EXTENSIONS` <br> - `-e EXTENSIONS` | `py` | Specifies which file extensions in the project template should be rendered with the template engine. | `django-admin.py startproject --extension=py,rst,rb,html myproject` |
| - `--name FILES` <br> - `-n FILES` | `[]` | Specifies which files in the project template (in addition to those matching `--extension`) should be rendered with the template engine. | `django-admin startproject --template https://github.com/username/repo/archive/master.zip --name=Procfile newproject` |
