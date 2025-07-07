# test_api

```py
version: '3.2'
services:
  oracle-db:
    container_name: oracle
    image: container-registry.oracle.com/database/express:21.3.0-xe
    environment:      
      - ORACLE_PDB=db
      - ORACLE_PWD=1234
    ports:
      - 1521:1521
      - 5501:5500
      
    volumes:
      - oracle-data:/opt/oracle/oradata
      - oracle-backup:/opt/oracle/backup
    healthcheck:
      test:
        [
          "CMD",
          "sqlplus",
          "-L",
          "sys/1234@//localhost:1521/db as sysdba",
          "@healthcheck.sql",
        ]
      interval: 30s
      timeout: 10s
      retries: 5
volumes:
  oracle-data:
  oracle-backup:



```


```py


```




```py


```





```py


```





```py


```



