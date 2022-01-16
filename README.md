# Flask-Blog
A simple blog written with Flask framework.

## Installation
 
    $ git clone https://github.com/djeada/Minimal-Flask-App.git
    $ cd Minimal-Flask-App
    $ python3 -m venv myenv
    $ source myenv/bin/activate
    $ python3 src/app.py

## How to setup the database?

Easiest way to locally setup a MySQL database is using docker.

```bash
docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=secret_pass mysql
docker exec -it <container-name> bash
# after p goes the password that you used when creating the container
mysql -u root -psecret_pass
```

Let's call our database flask_db.

```MySQL
create database flask_db;
USE flask_db;
```

We need two tables: articles and users.

```MySQL
CREATE TABLE IF NOT EXISTS articles (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    body LONGTEXT NOT NULL,
    author VARCHAR(255) NOT NULL,
    date DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    image VARCHAR(255) default '/static/images/default.jpg'
);
```
    
```MySQL
CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(20) NOT NULL,
    email VARCHAR(40) NOT NULL,
    username VARCHAR(20) NOT NULL,
    password VARCHAR(255) NOT NULL
);
```


## How to use?


## TODO

- [ ] Add exception handling to all python files that are interacting with the DB.
- [ ] Introduce variables to CSS.
- [ ] Test on different devices.
- [ ] Make full project specification.
- [x] Enable storing of images in the database.
- [ ] Add tags to the database.

