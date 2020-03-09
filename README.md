# Boilerplatform

This is a boilerplate for API Platform and React using github pages and Heroku.
The aim is to use nothing in local environment but the client.

## Requirements
* Docker
* Docker compose
* Heroku client
* Basic understanding of PHP
* Basic understanding of Javascipt ES6
* Basic understanding of Symfony
* Basic understanding of API Platform
* Basic understanding of React

If you have all the requirements, you are 1 hour from having your app ready and deployed !
## Installation
* git clone the repository
* cd the folder
* docker-compose pull
* docker-compose up -d
## Configuration
### API
#### Api platform
* cd api/
* composer update
* git init 
* git add .
* git commit -m "First commit"
#### Heroku
* cd api/ (but u should already be there)
* heroku login
* heroku create
* go to the heroku project web page
* go to settings
* jump to the config vars section and set these :
APP_ENV = prod
CORS_ALLOW_ORIGIN = https?:\/\/localhost(:[0-9]+)?|https?:\/\/0.0.0.0(:[0-9]+)?|https:\/\/MYGITHUBACCOUNTNAME.github.io (replace with your github account name)
TRUSTED_HOSTS = .
JWT_PASSPHRASE = pass
JWT_PUBLIC_KEY = %kernel.project_dir%/config/jwt/public.pem
JWT_SECRET_KEY = %kernel.project_dir%/config/jwt/private.pem
SYMFONY_ENV = prod
* git push heroku master
* come back to the heroku project web page and add Heroku Postgres free add on (check the installation by looking after DATABASE_URL config var)
### Client
#### Create react app
* cd client
* yarn install or npm install
* Update public/manifest.json
    * short_name
    * name
    * icons
    * colors
* Update public index.html title tag
* Update .env REACT_APP_API_ENTRYPOINT
#### Github Pages
* Update composer.json home and deploy properties with your github repository
* Turn on gh pages in the github repository settings
* yarn deploy or npm run deploy
* Set default branch to gh-pages in the repo settings (it may be already setted)

