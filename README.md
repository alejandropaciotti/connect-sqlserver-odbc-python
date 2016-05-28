### ** Conectarse a sql server vía odbc con python


```shell
sudo apt-get install unixodbc unixodbc-dev freetds-dev sqsh tdsodbc
sudo apt-get install python2.7-dev
sudo pip install pyodbc

sudo vim /etc/odbcinst.ini
```
And write:

```shell
[FreeTDS]

Description=FreeTDS
Driver=/usr/lib/x86_64-linux-gnu/odbc/libtdsodbc.so
Setup=/usr/lib/odbc/libtdS.so
FileUsage=1
CPTimeout=5
CPResue=20
Threading=1
```

Una utilidad importante (pero no necesaria)
```shell
odbcinst -j
```

Y luego:

import pyodbc  
```python
cnxn = pyodbc.connect('DRIVER={FreeTDS};SERVER=servername.ddns.net;PORT=1433;DATABASE=DatabaseName;UID=userName;PWD=yourpassword')
```
