# Deploying Apps from Github to Heroku

---

# Escape from local!

- Your app currently lives on your local machine

- In order to release it to the world, it needs to live somewhere online!

---

# What is Heroku?

- Heroku has enabled a technological revolution.

- In the past, tech companies had to have their own infrastructure

- Heroku hosts your application and handles the process of putting your app up on server infrastructure

- Hosted on AWS

---

# Getting Started

- Signup for a Heroku account:
  [Heroku signup](https://id.heroku.com/signup)

- Confirm your e-mail address

- Install the Heroku toolbelt:
  [Heroku CLI Download](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)

- Login to the Heroku Command Line Interface from the Terminal:

```bash
  $ heroku login
```

---

# Files to put in the main directory of your folder

- composer.json
  - the contents of this file will just be an empty object, as so:

```bash
{}
```

- index.php
  - the contents of this file will be:

```bash
<?php include_once("path/to/html"); ?>
```

- <strong>Please view this project as an example</strong>
---

# Deploying

- Deploy your code. Start by pushing up your code to github: <br />
  `$ git add .` <br />
  `$ git commit -m 'commit message'` <br />
  `$ git push origin main` <br />

- Once you've dealt with these issues, create a new app on Heroku from the Terminal: <br />
  `$ heroku create` <br />

- Then, when you're ready, push your code to production:<br />
  `$ git push heroku main` <br />

- `$ heroku open`
  to open your new app in the browser!

- Heroku creates a random janky app name for you. Before you forget to do it later you should change the name now with this command:<br />
  `$ heroku apps:rename <newname>`<br />

---

# Deploying Database

- You'll probably have to migrate the database as Heroku has a different database than your local machine's database

- The copy Heroku has is called the *production* database, while your local copy is called the *development* database

- To migrate your database on Heroku:
  `heroku run rake db:migrate`

---

# Troubleshooting

- To see the latest from the logs, use:
  `$ heroku logs --tail`

- To run an IRB console:

```bash
  $ heroku run irb
  > require './app'
```
- To run a rake task:
  `$ heroku run rake db:migrate`

---

# Troubleshooting

- To restart your Heroku app:
  `$ heroku restart`

---

# More

Want to know more about the technical details of how Heroku works?
[How Heroku works](https://devcenter.heroku.com/articles/how-heroku-works)

---

# Exercise

- Try deploying your app to Heroku!
