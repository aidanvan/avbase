# avbase


1. Checkout the repo

```
cd ~/code
git clone https://github.com/aidanvan/avbase.git
cd avbase
pipenv shell
```

2. If using postgres db locally, in settings.py, comment out the sqlite block and uncomment the postgres block

3. Set environmental variables

```
export SECRET_KEY='secret_key'
export EMAIL_PASS=''
```

