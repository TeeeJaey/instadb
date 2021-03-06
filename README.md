# instadb 🔌

A simple and light DB python package

[![PyPI version](https://badge.fury.io/py/instadb.svg)](https://badge.fury.io/py/instadb)

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

```python
  import instadb
  db = instadb.Connection(url=database_url)
  df = db.dataframe("select * from users limit 10")
```

If you have env variables that match the pattern `<key>_DATABASE_URL` then you can directly do:

```python
  import instadb
  df = instadb.key.dataframe("select * from users limit 10")
```

You can look at the available connections with `instadb.connections`

### Query from file

```python
  df = instadb.key.dataframe(filename='./users.sql')
```

### Query from file with arguments

```sql
# users.sql
select id, name from users order by name asc limit={limit}
```

```python
  df = instadb.key.dataframe(filename='./users.sql', limit=100)
```

## TODO
- [ ] load data to list
- [ ] insert and update queries
- [ ] caching
- [ ] Redshift load and unload
