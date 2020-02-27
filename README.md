 
# Made to simplify work with sqlite3

## How to use:
```python3
from sql_request import *
db = DataBase('database')
db.version #get version

# add table: (name, columns(name, type, PRIMARY KEY)) PRIMARY KEY is not necessary
columns = {  'id': 'int',
            'name': 'str'
        }
db.add_table('users', columns, 'id') 

# make a request
db.request('''select * from messages;''')
db.request('''select * from messages WHERE name = "%s";''', 'Dan')
db.request('''select * from messages WHERE name = "%s" and old = %s;''', ('Dan', 10))

#close
db.close()
```
