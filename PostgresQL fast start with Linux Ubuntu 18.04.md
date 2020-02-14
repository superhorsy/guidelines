# PostgreSQL fast start with Linux Ubuntu 18.04 #
**Starting out  with package manager update**:

```bash
sudo apt update
```
**Installing postgres**:
```
sudo apt install postgres-10
```

**After installation creating a password for postgres user**:
```
sudo passwd postgres
```
**Login as postgres and going to config file:**
``` 
su postgres
vi /etc/postgresql/10/main/pg_hba.conf
```
**Add a new entry into config file to grant access to your postgres server:**
>\# TYPE DATABASE USER CIDR-ADDRESS  METHOD
>
>host  all  all 0.0.0.0/0 md5

**You can also change a access parameters to grant access from any IP address you like, just change
just change**
>listen_addresses = ‘localhost’

**to**

> listen_addresses = ‘*’

**Create a new user:**

```
pgsql
createuser --interactive --pwprompt
```
**Create datebase:**

```
createuser --O "Your username here" "Database name here" 
```

**All set, ready to start:**
```
/q
exit
sudo service postgresql start
```






