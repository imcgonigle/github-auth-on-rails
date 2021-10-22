# GitHub Auth on Rails
This Rails application has no functionality other than allowing a user to authenticate using GitHub or create an account with an email.

## Gettings Started
To get the app running for the first time you'll need to create an OAuth application in GitHub, setup the env variables, install the gems, initialize the database and then start the server.

### Create an OAuth application in GitHub
Go to you GitHub settings and in the side go down to developer settings. From that page you can go to the OAuth application tab and create a new OAuth app.

GitHub will for your applications **Homepage URL** and a **Authorization callback URL**. Set them to the values below:

**Homepage URL:** `http://localhost:3000`

**Authorization callback URL:** `http://localhost:3000/users/auth/github/callback`

After you creat the app you'll be taken to a screen that has the `github_app_id` and the `github_app_secret` that you'll need whenever you setup the environment variables below.

### Env variables
Copy `config/application.yml.sample` to `config/application.yml` and set the `github_app_id` and the `github_app_secret` to the values from the GitHub OAuth application page.

### Install Gems
To install the gems running

`$ bundle install`

### Initializeing the Database
The first time your run the app you'll have to setup the database by running

`$ rails db:setup`

### Starting the application
After you've set everything up you can run start the server by running

`$ rails server`

## Database
This application uses SQLite

## Gems
The only gems I added are:
```
# Environment Variables
gem 'figaro'

# Authentication
gem 'devise'
gem 'omniauth-github', github: 'intridea/omniauth-github'
gem 'omniauth-rails_csrf_protection'
```
