
`cd` to this project's root directory, then start services using `docker-compose`:

```
docker-compose up -d
```

### Login atlas using Web UI

Open `http://localhost:21000` in your local browser, wait until you see the login page, use `admin` / `admin` to login.

### Run some hive `SQL`s

`bash` into the hive container:

```
docker-compose exec hive-server bash
```

Start beeline:

```
/opt/hive/bin/beeline -u jdbc:hive2://localhost:10000
```

Run some statements containing certain lineage info, e.g.:

```
create table t(i int);
create view v as select * from t;
```

### Check lineage in Web UI

Now refresh the atlas Web UI page, you'll see a bunch of hive entities captured, each of which containing the lineage info.

## References

[Doc of atlas's hive hook](http://atlas.apache.org/index.html#/HookHive)

[Solving incompatibility between latest atlas and hive](https://liangjunjiang.medium.com/deploy-atlas-hive-hook-fcb130b7db01)

[Docker atlas](https://github.com/sburn/docker-apache-atlas)

[Docker hive](https://github.com/big-data-europe/docker-hive)
