# avbase


1. Checkout the repo

```
cd ~/code
git clone https://github.com/aidanvan/avbase.git
cd avbase
pipenv shell
```

2. If using postgres db locally, in settings.py, comment out the sqlite block and uncomment the postgres block, updating the db info.

```
psql -h localhost
CREATE DATABASE avbase_db;
CREATE ROLE localuser WITH LOGIN PASSWORD 'localpassword';
GRANT ALL PRIVILEGES ON DATABASE avbase_db TO root;
\q
```

3. Set environmental variables

```
export SECRET_KEY='secret_key'
export EMAIL_PASS=''
```

