Report the latest available version of the API

```
curl -u jeekhen:cloudera http://master:7180/api/version
```

Report the CM version

```
curl -u jeekhen:cloudera http://master:7180/api/v14/cm/version
```


List all CM users

```
curl -u jeekhen:cloudera http://master:7180/api/v14/users
```


Report the database server in use by CM

```
curl -u jeekhen:cloudera http://master:7180/api/v14/cm/scmDbInfo
```