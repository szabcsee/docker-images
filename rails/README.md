# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

## System dependencies
everything is clearly described in the Dockerfile

### Ruby version 
   2.7.2

### Rails version
  6.3.1

### Yarn version
  1.22.10


## Configuration
  This setup is based on the git repository from harayama-developmer
  https://github.com/harayama-developmer/template-docker-rails-6-postgresql

### Initial run for new projects (if you use the docker files but no Rails app)
__run a rails new command with required parameters like:__

    docker-compose run --rm backend rails new  digitalyogis -d postgresql --skip-action-cable --skip-action-mailbox --skip-action-text --skip-bootsnap --skip-git --skip-keeps --skip-listen --skip-spring --skip-sprockets --skip-system-test --skip-test --skip-webpack-install --skip-yarn

  1. run 
     
    docker-compose build
  2. Initialize database at first run 
     
    docker-compose run --rm backend rails db:create
  3. Install webpacker (optional if you use webpacker)
     
    docker-compose run --rm backend bundle exec rails webpacker:install

  4. Further packages can be added by yarn

    docker-compose run --rm backend yarn add jquery 
  
* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
