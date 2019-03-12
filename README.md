# base

## Local set up

1. Checkout the repo

```
cd ~/code
git clone https://github.com/aidanvan/base.git
cd base
pipenv shell
pipenv install
```

2. If using postgres db locally, in settings.py, comment out the sqlite block and uncomment the postgres block, updating the db info.

```
psql -h localhost
CREATE DATABASE base_db;
CREATE ROLE localuser WITH LOGIN PASSWORD 'localpassword';
GRANT ALL PRIVILEGES ON DATABASE base_db TO localuser;
\q
```

3. Set environmental variables

```
export SECRET_KEY='secret_key'
export EMAIL_PASS=''
```

4. Run django set up commands

```
python manage.py collectstatic
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver 8080
```


## Committing changes to base repo

```
git add .
git commit -m "changes"
git push -u origin master
```

## Creating a new project based on the repo



## Deploying to Heroku

1. Create a new github repo

2. Push the project to the new repo

```
git add .
git commit -m "changes"
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin master
```

3. Create a dyno with a Postgres DB

4. Link the dyno to the new github repo and deploy

5. Set the env vars on heroku 

```
heroku config:set SECRET_KEY=secret_key --app appname
heroku config:set EMAIL_PASS= --app appname
```

6. Run django set up scripts

```
heroku run python manage.py collectstatic --app appname
heroku run python manage.py migrate --app appname
heroku run python manage.py createsuperuser --app appname
```

