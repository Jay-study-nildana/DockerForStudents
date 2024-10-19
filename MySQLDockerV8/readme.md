# running mysql with docker

running mysql with docker (for version 8)

## some additional info

The focus of this docker image, is related to the issue with, 'command: --default-authentication-plugin=mysql_native_password'.

I have noticed that, this is something that is needed for a lot of node js related projects, where, if you the latest mysql, for example, version 9.0, there are plenty of breaking changes related to authentication. You might see errors like this.

```
sqlMessage: 'Client does not support authentication protocol requested by server; consider upgrading MySQL client'
```

more details can be found here

1. https://superuser.com/questions/1470388/mysql-error-1524-hy000-plugin-mysql-native-password-is-not-loaded
1. https://stackoverflow.com/questions/78445419/unknown-variable-default-authentication-plugin-mysql-native-password
1. https://stackoverflow.com/questions/49019652/not-able-to-connect-to-mysql-docker-from-local

## run and connect to the db

```
docker-compose up -d
docker exec -it mysql-container mysql -u root -p

```

note: I tried using MySQL WorkBench, but, it kept crashing. so, use the 2nd command above to use the terminal.

## simple queries

```

CREATE DATABASE my_database;

SHOW DATABASES;

USE my_database;


CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    hire_date DATE NOT NULL
);

INSERT INTO employees (first_name, last_name, email, hire_date) VALUES
('Amit', 'Sharma', 'amit.sharma@example.com', '2023-01-15'),
('Priya', 'Singh', 'priya.singh@example.com', '2023-02-20'),
('Rahul', 'Verma', 'rahul.verma@example.com', '2023-03-25'),
('Anjali', 'Patel', 'anjali.patel@example.com', '2023-04-10'),
('Vikram', 'Gupta', 'vikram.gupta@example.com', '2023-05-05');

SELECT * FROM employees;

SELECT first_name, last_name, email FROM employees;

SELECT * FROM employees WHERE hire_date > '2023-01-01';

SELECT * FROM employees ORDER BY last_name ASC;

SELECT * FROM employees LIMIT 5;

INSERT INTO employees (first_name, last_name, email, hire_date) VALUES
('Ravi', 'Kumar', 'ravi.kumar@example.com', '2023-06-15');


UPDATE employees
SET email = 'ravi.kumar123@example.com'
WHERE first_name = 'Ravi' AND last_name = 'Kumar';

DELETE FROM employees
WHERE first_name = 'Ravi' AND last_name = 'Kumar';


```

# book a session with me

1. [calendly](https://calendly.com/jaycodingtutor/30min)

# hire and get to know me

find ways to hire me, follow me and stay in touch with me.

1. [github](https://github.com/Jay-study-nildana)
1. [personal site](https://thechalakas.com)
1. [upwork](https://www.upwork.com/fl/vijayasimhabr)
1. [fiverr](https://www.fiverr.com/jay_codeguy)
1. [codementor](https://www.codementor.io/@vijayasimhabr)
1. [stackoverflow](https://stackoverflow.com/users/5338888/jay)
1. [Jay's Coding Channel on YouTube](https://www.youtube.com/channel/UCJJVulg4J7POMdX0veuacXw/)
1. [medium blog](https://medium.com/@vijayasimhabr)
