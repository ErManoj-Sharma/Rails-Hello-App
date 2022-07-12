# Requirments
```
ruby -v
->ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x86_64-linux]
```
### Install Rails
```
gem install rails 6.1.4
```
### Check version 
```
rails -v
->Rails 6.1.4
```
# To Install Application In Your System
```
git clone https://github.com/ErManoj-Sharma/Rails-Hello-App.git
```
```
cd hello_app/
```
```
bundle install
``` 
# To Start Application
``` ruby
rails server
```
### Go to localhost:3000 or 127.0.0.1:3000]


# Build from Scratch
```
mkdir Rails-Project
```
```
cd Rails-Project/
```
```
rails _6.1.4_ new sample_app
```
```
cd sample_app
```
```
bundle install
```
## Git Setup
```
git init
```

```
git remote add origin https://github.com/<UserName>/Rails-sample-App.git
```
```
git add -A
```
```
git commit -m "initial commit"
```
```
git push origin master
```
```
git checkout -b <Branch_Name>
```
```
git push --set-upstream origin <Branch_Name>
```


## Application setup
#### 1. Allow Connection to local webserver
``` ruby
config/enviroments/development.rb

Rails.application.configure do
.
# allow connection to local server
config.hosts.clear
end
``` 
#### 2. Update Gemfile 
```ruby
hello_app/Gemfile
# add this two group in your Gemfile 
# for heroku deployment purpose
group :development,:test do 
   gem 'sqlite3' ,'1.4.1'
   gem 'byebug','11.0.1',plateforms: [:mri,:mingw,:x64_mingnw]
end
group :production do 
   gem 'pg','1.1.4'
end
```
```ruby
# it will run bundle with installing production group gems
bundle install --without production
```
### Now Our Application is ready for Development ,Add required functionality in application and test it locally by 
```
rails s
```
#### to generate controller
```ruby
-> rails generate controller StaticPages home help contact about
-> rails generate controller Users new 
```
#### to destroy controller 
```ruby
rails destroy controller StaticPages home help contact about
```
#### to generate model 
```ruby
rails generate model User name:string email:string
```
#### to destroy model 
```ruby
rails destroy model User
```
#### to generate migrations
```ruby
rails generate migration <migration_name> password:string
```
#### to reset database migration
```
rails db:migrate:reset
```
#### to generate integration tests
```
rails generate integration_test <test_name>
```
##### run test by 
```ruby
rails test
rails test:integration
rails test:model
```

## Usefull gems
```ruby
gem 'bootstrap-sass','3.4.1'
gem 'rubocop'
```





## Deployment
#### Check heroku version 
```
heroku -v
->heroku/7.60.1 linux-x64 node-v14.19.0
```
``` ruby
heroku login --interactive  
# interactive option prevents heroku from trying to spawn browser 
```
```ruby
heroku create
# create new heroku app
```
```ruby
git add -A
git commit -m "final commit"
git push origin master
```
```ruby
git push heroku master
# if you are not working on master branch then 
git push heroku <Branch_Name>:master
# it will push your branch on heroku master branch
```
