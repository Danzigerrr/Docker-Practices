# Task description
I was following this [docker-tutorial](https://stavshamir.github.io/python/dockerizing-a-flask-mysql-app-with-docker-compose/).

## Files
```
Flask with MySQL/
├── app
│   └── app.py
└── db
    └── init.sql
```
There are two files:
- *app.py* — contains the Flask app which connects to the database and exposes one REST API endpoint
- *init.sql* — an SQL script to initialize the database before the first time the app runs

## Running the docker-compose.yml file

Use this command to run the dockerized app:
```
docker-compose up -d
```

When finished, after entering *http://localhost:5000/* you should see the following output:
```
{"favorite_colors": [{"Lancelot": "blue"}, {"Galahad": "yellow"}]}
```
