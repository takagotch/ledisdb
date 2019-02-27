### ledisdb
---
https://github.com/siddontang/ledisdb

```go
import (
  lediscfg "github.com/siddontang/ledisdb/config"
  "github.com/siddontang/ledisdb/ledis"
)

cfg := lediscfg.NewConfigDefault()
l, _ := ledis.Open(cfg)
db, _ := l.Select(0)

db.Set(key, value)

db.Get(key)
```

```sh
mkdir $WORKSPACE
cd $WORKSPACE
git clone git@github.com:siddontang/ledisdb.git src/github.com/siddontang/ledisdb

cd src/github.com/siddontang/ledisdb

source dev.sh

make
make test

sudo sh tools/build_leveldb.sh

source dev.sh

./bin/ledis-server -config=/etc/ledis.conf
./bin/ledis-cli -p 6380
set a 1
get a
curl http://127.0.0.1:11181/SET/world
curl http://127.0.0.1:11181/0/GET/hello?type=json

ledis-cli -p 6381
```

```
db_name = "leveldb"

ledis-server -config=/etc/ledis.conf -db_name=leveldb
```


