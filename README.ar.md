# مكتبة SQLite للغة الأسس
[[English]](README.md)

<div dir=rtl>

## التثبيت

يجب تثبيت sqlite3 أولاً ثم يمكنك استخدام المكتبة. <br/>
على توزيعة Debian (و _Ubuntu_)

<div dir=ltr>

```
apt install libsqlite3-0
```

</div>

استيراد المكتبة

<div dir=ltr>

```
import "Apm.alusus";
Apm.importFile("Alusus/Sqlite");
```

</div>

## الدوال

<div dir=ltr>

```
Sqlite.exec(sql: ptr[array[Char]]): Array[ColumnMap];
Sqlite.exec(sql: ptr[array[Char]], errmsg: ptr[array[Char]]): Array[ColumnMap];
```

</div>


## العمليات

<div dir=ltr>

```
this = ptr[array[Char]]
```

</div>

تهيئة Sqlite باسم ملف "db":

<div dir=ltr>

```
def mydb: Sqlite = "mydb.db";
```

</div>


## مثال

<div dir=ltr>

```
def sqlite: SQLite3 = "mydb.db";

sqlite.exec("CREATE table teachers(id INTEGER PRIMARY KEY AUTOINCREMENT, name TEXT, section INT)");

sqlite.exec("INSERT INTO teachers VALUES(NULL, 'Mohammed', 1);");

def cm: Array[ColumnMap] = sqlite.exec("SELECT * FROM teachers;");
Console.print("ROW 0 COLUMN 'NAME': %s\n", cm(0)("name"))
```

</div>

ستجد المزيد من الأمثلة في `./Examples`

## الرخصة

<div dir=ltr>

```
Apache License
==============

_Version 2.0, January 2004_  
_&lt;<http://www.apache.org/licenses/>&gt;_

### Terms and Conditions for use, reproduction, and distribution

#### 1. Definitions

“License” shall mean the terms and conditions for use, reproduction, and
distribution as defined...
```

</div>

</div>

