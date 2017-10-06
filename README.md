# instadb

A simple a light DB python package

## Features
- query from postgres and reshift
- load data into pandas dataframe
- query from sql or filename
- automatically setup connections from env variables
- automatic query annotation
- connect timeout retry with exponential backoff

### Installation

`pip install instadb`

### Basic Usage

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

### Query from file

```
  df = instadb.key.dataframe(filename='./users.sql')
```

### Query from file with arguments

```
select * from users where limit=
```

```
  df = instadb.key.dataframe(filename='./users.sql', limit=100)
```

## TODO
[] load data to list
[] insert and update queries
[] caching
