# best_buy_laptop_scraper
Primary for scraping and analysing laptop data from best buy Canada.


# Project Setup Guide

This guide outlines the steps to set up the development environment for a project that involves Python Jupyter Notebook & Mysql.

## Prerequisites

Ensure that you have the following installed on your Ubuntu system:

- Python 3
- Jupyter Notebook
- MySQL Server (for database management)

## Steps to Install/Configure

### 1. Install pip

Pip is the package installer for Python. You can install it by running:

```bash
sudo apt update
sudo apt install python3-pip
```

### 2. Install MySQL Server
```bash
sudo apt install mysql-server
```

After installation, you can secure your MySQL installation by running:


```bash
sudo mysql_secure_installation
```

### 3. Configure MySQL Database
This would ensure mysql is configured for a new user apart from root, makes best_buy database and starts it's service if not running.
```bash
sudo service mysql start
mysql -u root -p
CREATE DATABASE best_buy;
USE best_buy;
SELECT DATABASE();
EXIT;
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost';
FLUSH PRIVILEGES;
```

## Create a Virtual Environment and install jupyter notebook
```bash
python3 -m venv myvenv
pip install jupyter
pip install -r requirements.txt
```

## Setup virtual env variables -> Contains mysql connection stuff and activates myvenv
```bash
source local_config.sh
```

Contents example:
```bash
source myvenv/bin/activate

export MYSQL_HOST="localhost"
export MYSQL_USER="your_user_name"
export MYSQL_PASSWORD="your_password"
export MYSQL_DATABASE="best_buy"
```

## Run Jupyter notebook
```bash
jupyter notebook
```