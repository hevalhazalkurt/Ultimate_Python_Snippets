# Ultimate Python Snippets
## Python MySQL
### `mysql.connector`


<br>

-----


#### What is `mysql.connector` for?

MySQL Connector enables Python programs to access MySQL databases, using an API.

It supports for :
* Almost all features provided by MySQL Server up to and including MySQL Server version
* If also supports X DevAPI.
* Converting parameter values back and forth between Python and MySQL data types, for example Python `datatime` and MySQL `DATETIME`. It can turn automatic conversion on for convenience, or off for optimal performance.
* All MySQL extensions to standart SQL syntax.
* Protocol compression, which enables compressing the data stream between the client and server.
* Connections using TCP/IP sockets and on Unix using Unix sockets.
* Secure TCP/IP connections using SSL.
* Self-contained driver. Connector/Python does not require the MySQL client library or any Python modules outside the standard library.


**Installing**

```python
pip3 install mysql-connector-python
```

<br>

-----

<br>

#### `mysql.connector.connect()`


The `.connect()` constructor creates a connection to the MySQL server and returns a `MySQLConnection` object.


Arguments required to connect MySQL from Python:
* `username` : The username that you use to work with MySQL Server. The default username for the MySQL database is a root
* `password` : Password is given by the user at the time of installing the MySQL database. If you are using root then you won’t need the password.
* `host` : It is the server name or Ip address on which MySQL is running. if you are running on localhost, then you can use `localhost`, or it’s IP, i.e. `127.0.0.1`
* `database` : Database name to which you want to connect.

The following examples shows how to connect to the MySQL server:

```python
import mysql.connector

con = mysql.connector.connect(
    host="127.0.0.1",
    user="username",
    password="password",
    database="thedatabase"
)

print(con)
```

**Output**

```
<mysql.connector.connection_cext.CMySQLConnection object at 0x10542fd10>
```


We can also use `username` and `localhost` like below :

```python
import mysql.connector

con = mysql.connector.connect(
    host="localhost",
    username="username",
    password="password",
    database="thedatabase"
)

print(con)
```

**Output**

```
<mysql.connector.connection_cext.CMySQLConnection object at 0x10d396e10>
```


<br>

--------

<br>


#### `connection.MySQLConnection()`

It is also possible to create connection objects using the `connection.MySQLConnection()` class :


```python
from mysql.connector import (connection)

con = connection.MySQLConnection(
    host="localhost",
    username="user",
    password="password",
    database="thedatabase"
)

print(con)
```

**Output**

```
<mysql.connector.connection.MySQLConnection object at 0x1030ded90>
```


<br>

--------

<br>


#### Handling connection errors

**`errors.Error`**

To handle connection errors, we can use the `try` statement and catch all errors using the `errors.Error` exception:

```python
import mysql.connector
from mysql.connector import errorcode

try :
    con = mysql.connector.connect(
        host="localhost",
        username="user",
        database="wrongdatabase"
    )
except mysql.connector.Error as err:
    if err.errno == errorcode.ER_ACCESS_DENIED_ERROR:
        print("Database does not exits")
    elif err.errno == errorcode.ER_BAD_DB_ERROR:
        print("Database does not exist")
    else:
        print(err)
else:
    con.close()
```

**Output**

```
Database does not exits
```


Defining connection arguments in a dictionary and using the `**` operator is another option:


```python
import mysql.connector

config = {
    "username": "user",
    "password": "password",
    "host": "localhost",
    "database": "thedatabase",
    "raise_on_warning": True
}

con = mysql.connector.connect(**config)
print(con)
```

<br>

--------
