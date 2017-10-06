# instadb

A simple a light DB python package

### Installation

`pip install instadb`

### Usage

```
  import instadb
  db = instadb.Connection(url=database_url)
  df = db.dataframe("select * from users limit 10")
```

If you have env variables that match the pattern `<key>_DATABASE_URL` then you can directly do:

```
  import instadb
  df = instadb.key.dataframe("select * from users limit 10")
```
