flaskr-heroku
=============

This repository is meant as a code-examples version of the Flaskr tutorial at
http://flask.pocoo.org/docs/0.10/tutorial/, except with a few modifications
meant to make it easy to run on Heroku with Postgres.

To download and run locally, you should need Git, Python and Postgres, and you should
run the code inside of a virtual environment. For the early rounds of this, you'll
need SQLite instead of Postgres. Everything else should be installed from within the virtual
environment with Pip.

1. Setting up the Environment
-----------------------------

First, get yourself into the the directory where you want to store this project,
like `cd ~/projects/`, and clone this repository with `git clone https://github.com/michaelsnook/flaskr-heroku.git`. Then cd into `flaskr-heroku`.

Next, if you haven't run virtualenv.py recently, go ahead and re-clone it with
`git clone https://github.com/pypa/virtualenv.git /tmp/virtualenv`. Then set up
this project's virtual environment with `python /tmp/virtualenv/virtualenv.py ./ve`.

When you want to run the app, or use Pip to install new Python packages or run
any of the database update scripts, you'll activate the virtual environment with
`source /path/to/ve/bin/activate`, and if you want to leave the ve and switch to another
project, you just type `deactivate`.

2. Running the app for the first time
-------------------------------------

*Note: this section will change over time! If you want to run the app in different
stages, you should revert your entire repository to that point and refer to this
section in the README at that point.*

The first time you run the application, you'll need to activate your virtual
environment and run `pip install -r 'requirements.txt'`. Then you'll need to
follow the instructions on [this page](http://flask.pocoo.org/docs/0.10/tutorial/dbinit/#tutorial-dbinit) which
explain how to create the database from `schema.sql` and how to run `init_db()`
for the first time.

**Now you're ready to go!**

While still inside the virtual environment, run the Flask web server
with `python flaskr.py`.

3. Running the app on Heroku
----------------------------

First, head over to this [Heroku Dev Center help page](https://devcenter.heroku.com/articles/getting-started-with-python#set-up).
Install the Heroku toolbelt, and set up a free Heroku account. If you have
Homebrew, use `brew install heroku-toolbelt`.

Run `heroku login` and give it your credentials. Verify your keys are working and go to the next step. You can skim over [the next step](https://devcenter.heroku.com/articles/getting-started-with-python#prepare-the-app)
because you've already created the app.

Now for the moment of truth! Run `heroku create` and `git push heroku master`
and that really should be it.
