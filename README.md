# Coffee Shop Full Stack

## Full Stack Nano - IAM Final Project

Udacity has decided to open a new digitally enabled cafe for students to order drinks, socialize, and study hard. But they need help setting up their menu experience.

You have been called on to demonstrate your newly learned skills to create a full stack drink menu application. The application must:

1. Display graphics representing the ratios of ingredients in each drink.
2. Allow public users to view drink names and graphics.
3. Allow the shop baristas to see the recipe information.
4. Allow the shop managers to create new drinks and edit existing drinks.

## Backend 
### Virtual Environment

We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organized. Instructions for setting up a virtual environment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

### PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the `/backend` directory and running:

```bash
pip install -r requirements.txt
```

This will install all of the required packages we selected within the `requirements.txt` file.

#### Key Dependencies

- [Flask](http://flask.pocoo.org/) is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) and [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) are libraries to handle the lightweight sqlite database. Since we want you to focus on auth, we handle the heavy lift for you in `./src/database/models.py`. We recommend skimming this code first so you know how to interface with the Drink model.

- [jose](https://python-jose.readthedocs.io/en/latest/) JavaScript Object Signing and Encryption for JWTs. Useful for encoding, decoding, and verifying JWTS.

### Running the server

From within the `./src` directory first ensure you are working using your created virtual environment.

Each time you open a new terminal session, run:

```bash
export FLASK_APP=api.py;
```

To run the server, execute:

```bash
flask run --reload
```

The `--reload` flag will detect file changes and restart the server automatically.

### Test endpoints with [Postman](https://getpostman.com).
- Register 2 users - assign the Barista role to one and Manager role to the other.
- Sign into each account and make note of the JWT.
- Import the postman collection `./starter_code/backend/udacity-fsnd-udaspicelatte.postman_collection.json`
- Right-clicking the collection folder for barista and manager, navigate to the authorization tab, and including the JWT in the token field (you should have noted these JWTs).
- Run the collection and correct any errors.
- Export the collection.

#### Tokens for Barista:
(I set the expiration period = 500,000 seconds, should be enough for project review)
```
eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6Ii1MdHFvUXhpeGhJZWRSM0Zob3F3ZSJ9.eyJpc3MiOiJodHRwczovL2Rldi10YzdsNHFxMWczZjdiamp1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NjYzNmNjNTc0OWEyMWFlMTI1NGZmZmQiLCJhdWQiOiJzYXJhaGNvZmZlZSIsImlhdCI6MTcxODA4ODk3NSwiZXhwIjoxNzE4MDk2MTc1LCJzY29wZSI6IiIsImF6cCI6IlhQcDZkRjFqbDhKRXNhRXVPbmg5WlJoMWZXbjl4clkwIiwicGVybWlzc2lvbnMiOlsiZ2V0OmRyaW5rcy1kZXRhaWwiXX0.LlzM9zXaD4yc_ejuVgqKhC0_9NpJqKH8bUSY3tquwfqtEQ4gI3vGf5JYC3hWCL_TcGPJU8tNQeypTIYOrTZMxaLrOqkpJRSoxdLK5DXvLfB5qraj8hNDiua343yYjJh9j9Laq5p46mc3Mx46P2RTSMlTEGiLV8xMs5AxSzSXZngd98fx7CZAD_aaa43hRNwHnuMU9CqejUnHpk9A8GZfUXtxVxXEwyh2v1kqlQmCD_JLhMNEmEWXsjCEINc0MC0mAI3RoyxgnIog2sL2E_avEhd_EUN7E6x-Tjso4WVb4IU64ic6dkJ1UQVVlhYEC1DEksnK-VYTbj8QaPVaqg2YpA
```

#### Tokens for Manager:
(I set the expiration period = 500,000 seconds, should be enough for project review)
```
eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6Ii1MdHFvUXhpeGhJZWRSM0Zob3F3ZSJ9.eyJpc3MiOiJodHRwczovL2Rldi10YzdsNHFxMWczZjdiamp1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NjYzNmJiOGY0Mzk4NTczMzQ3MDE0NDIiLCJhdWQiOiJzYXJhaGNvZmZlZSIsImlhdCI6MTcxODA4ODgxOCwiZXhwIjoxNzE4MDk2MDE4LCJzY29wZSI6IiIsImF6cCI6IlhQcDZkRjFqbDhKRXNhRXVPbmg5WlJoMWZXbjl4clkwIiwicGVybWlzc2lvbnMiOlsiZGVsZXRlOmRyaW5rcyIsImdldDpkcmlua3MtZGV0YWlsIiwicGF0Y2g6ZHJpbmtzIiwicG9zdDpkcmlua3MiXX0.aTxtwS7KKVOZCwkGorqh-xs8Lm9pWpnmYqCN0qpr-mke6QRpKmTuQ8pH1qgy0_HYAamLQjuZzBrLiZM2sjeIm0Gr9AHl-z0JETTD2E4z0Mj-Lw74vcCD31d61SN9sB0yciPGwbyFWL1ZT8H7mNQC-GAAFAhcXj_yVWfoVuJsnrmT2Esh-xBVPH_h8DUlAjTzhq6CEN9AxtrKeh6DPn998Z_TSNqFJJ5FDzNiYKy9XE-3Phh_rJ5lAKMJWwVJI7S1NO-W6ASTl2j8jLianOW5qOph5NiRQA4DO8Pk8QyzS0x97wOGx8iyRt7_NDUB7XIDA9W7CLWZBDUcz-wBSYrQaw
```

## Frontend

> _tip_: this frontend is designed to work with [Flask-based Backend](../backend). It is recommended you stand up the backend first, test using Postman, and then the frontend should integrate smoothly.

### Installing Dependencies

#### Installing Node and NPM

This project depends on Nodejs and Node Package Manager (NPM). Before continuing, you must download and install Node (the download includes NPM) from [https://nodejs.com/en/download](https://nodejs.org/en/download/).

#### Installing Ionic Cli

The Ionic Command Line Interface is required to serve and build the frontend. Instructions for installing the CLI is in the [Ionic Framework Docs](https://ionicframework.com/docs/installation/cli).

#### Installing project dependencies

This project uses NPM to manage software dependencies. NPM Relies on the package.json file located in the `frontend` directory of this repository. After cloning, open your terminal and run:

```bash
npm install
```

> _tip_: **npm i** is shorthand for **npm install**


## Running Your Frontend in Dev Mode

Ionic ships with a useful development server which detects changes and transpiles as you work. The application is then accessible through the browser on a localhost port. To run the development server, cd into the `frontend` directory and run:

```bash
ionic serve
```

> _tip_: Do not use **ionic serve** in production. Instead, build Ionic into a build artifact for your desired platforms.
> [Checkout the Ionic docs to learn more](https://ionicframework.com/docs/cli/commands/build)

## Trouble Shooting

### Backend
* Use conda virtual environment if for apple M2 ARM chip (if `python -m virtualenv env` not working)
```
conda create --prefix ./myenv python=3.11
conda activate ./myenv
conda deactivate
```
> Tips: Be sure to deactivate the env if you are want a package to install globally for the computer

* Create an application context if using python 3.11
  (add the following line to api.py)
```
app.app_context().push()
```

* **Localhost.5000 for macbook is forbiden get request**

> Tips: Use http://127.0.0.1:5000 can working

**Debug reference:** https://stackoverflow.com/questions/77240858/how-to-fix-cannot-import-name-request-ctx-stack-from-flask

### Frontend
* Don't use node-sass anymore. (node-sass is now deprecated. You can easily fix it by the following.)
```
npm install
npm uninstall node-sass
npm install sass

export NODE_OPTIONS=--openssl-legacy-provider
ionic serve
```
**Debug references:**
* https://stackoverflow.com/questions/73144960/error-error0308010cdigital-envelope-routinesunsupported-at-new-hash-nodei
* https://stackoverflow.com/questions/74501317/whats-the-fix-for-error-node-sass-version-8-0-0-is-incompatible-with-4-0-0

### Auth0 setup
* This a very clear and detailed guide for setting up Auth0 for this project:
https://github.com/jungleBadger/udacity_coffee_shop/blob/master/troubleshooting/generate_token.md







