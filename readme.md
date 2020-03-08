# SQLite Library for ALUSUS

## installation
You should install sqlite3 first then you can use Library. <br/>
on Debian (and _Ubuntu_) distro
```
apt install libsqlite3-0
```

import library
```
import "Apm.alusus";
Apm.importFile("Alusus/Sqlite");
```

## Methods
- Sqlite.exec(sql: ptr[array[Char]]): Array[ColumnMap];
- Sqlite.exec(sql: ptr[array[Char]], errmsg: ptr[array[Char]]): Array[ColumnMap];

## Operators
- this = ptr[array[Char]] <br>
```
    // init Sqlite with "db" filename
    def mydb: Sqlite = "mydb.db";  
```

## Example
```
def sqlite: SQLite3 = "mydb.db";

sqlite.exec("CREATE table teachers(id INTEGER PRIMARY KEY AUTOINCREMENT, name TEXT, section INT)");

sqlite.exec("INSERT INTO teachers VALUES(NULL, 'Mohammed', 1);");

def cm: Array[ColumnMap] = sqlite.exec("SELECT * FROM teachers;");
Console.print("ROW 0 COLUMN 'NAME': %s\n", cm(0)("name"))
```
you will find more examples in `./Examples`

## License
``` Apache License
==============

_Version 2.0, January 2004_  
_&lt;<http://www.apache.org/licenses/>&gt;_

### Terms and Conditions for use, reproduction, and distribution

#### 1. Definitions

“License” shall mean the terms and conditions for use, reproduction, and
distribution as defined...
```