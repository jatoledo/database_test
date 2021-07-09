usage:

```bash
$ git clone https://github.com/jatoledo/database_test.git
$ cd database_test
```



step 1

```bash

docker run --name npd-bench-mysql -v data:/data -e MYSQL_ROOT_PASSWORD=root -d -p 3306:3306 -h 127.0.0.1 mysql:5.7
```

step 2

```bash

docker exec -i npd-bench-mysql sh -c 'exec mysql --local-infile -uroot -proot' < npd1_schema.sql
```



Config:

```bash
db_url: mysql+pymysql://root:root@localhost:3306/npd
```

