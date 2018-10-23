# Rails

## CRUD
### #1 Planning
* Plan module of data is very imporant

### #2 Creat Project
* `rails new project_name --skip-git`

### #3 Customized Gem
* gem 'pry-rails'
* gem 'annotate'
* gem 'meta_request'
* to install `bundle`
* `bundle show [gemname]` to show installed gem

### #4 Setup Routes
* in main.rb file
* root :to => 'pages#home'
* get '/home' => 'pages#home'
* run server `rails s`

### #5 Create Controller
* create **page_controller.rb** in app/controllers/folder
* Define your method with def / end

### #6 Create view
* `mkdir app/views/pages`
* `touch app/views/pages/home.html.erb`

Repeat from step 4 - 8

## Conventions

### Models
* Singular
* Capitalized class name
* inherit from ActiveRecord::Base

### Controller
* Plural
* PascalCase calss name
* inherit from ApplicatoinController

### Views
* Plural
* name of the file is the associated action

### Helpers
* Assets = image_tage( 'path', options)
* URL
  link_to('Home', root_path) ; link_to( 'Work Path', work_path( work.id))
  button_to( 'Test Path', root_path, :method => 'GET')

### Customized and Automation
* rails new
  ```
  rails new app_name
  rails new app_name -T # Skips the Test Suite
  rails new app_name --database=postgresql # Specifies the Database (changes it from sqlite3)
  rails new app_name -d postgresql
  ```

* rails sever
  ```
  rails server
  rails s # Shorthand for rails server
  rails server -p 3001 # Specifies another port (have multiple servers at once!)
  rails server -e production # Changes the state of the application
  ```

* rails destroy
  ```
  rails destroy controller Kittens
  rails destroy model Kitten
  rails destroy scaffold Kittens
  ```
* rails
```
rails --tasks # Lists everything it can do

rails about # Lists everything about your Rails app

rails db:drop # DROPS THE DATABASE
rails db:create # CREATES THE DATABASE
rails db:migrate # MIGRATES TABLES INTO THE DATABASE (FROM db/migrations)
rails db:rollback # GOES BACK ONE STEP IN THE DATABASE (BACK ONE MIGRATION)
rails db:seed # SEED database

rails routes # LIST ALL OF YOUR ROUTES

rails stats # LINES OF CODE ETC.
```
rails notes [SEE HERE](http://guides.rubyonrails.org/v4.2/command_line.html#notes)

## Basic project Setup (with database)
1. Planning - Association is important
2. Create new rails app - `rails new kitten_party`
3. Move to new apps dir
4. Add development Gems -/Gemfile
5. Bundle Gems `bundle`
6. Create Database `rails db:create`
7. Generate first model  `rails generate model Kitten name:string age:integer`
8. Edit migration is required /db/migrate/[migration].rb
9. Generate first controller `rails generate controller Kittens`  `rails generate controller Kittens index show edit new`
10. Add methods to controller - /app/controllers/kittens_controller.rb
11. Add views for your action
12. configure routes `root :to => "kittens#index"
resources :kittens`
13. Repeat form step 7-12.

## Ruby on Rails Migration
`rails generate model Kitten`
`rails generate migration add_species_to_kitten`
* basic setup
```
class CreateKittens < ActiveRecord::Migration
  def change
    create_table :kittens do |t|
      t.string :name
      t.string :name
      t.integer :age
      t.timestamps null: false
    end
  end
end
```
* rails db:migrate

## Migrations to modify a table
`rails generate migration AddBreedToKittens breed:string`

## Generators
```
rails generate controller ControllerName list of actions
rails generate controller Greetings index create
rails g controller Greetings index create
# THIS WILL CREATE VIEWS, JS, CSS AND ACTIONS IN CONTROLLERS (PLUS TESTS)

rails g model ModelName field:type
rails g model Painting name:string year:date
# THIS WILL CREATE MODELS, MIGRATIONS, AND TESTS

rails g scaffold ModelName field:type field:type
rails generate scaffold Painting name:string year:date
# THIS WILL CREATE EVERYTHING

```

## Form Helpers
```
<%= form_for @artist do |f| %>
  <fieldset>
    <%= f.label :name %>
    <%= f.text_field :name %>
  </fieldset>
```
* Partial create `_form.html.erb`
  - @artist which tells the form how to behave
```
<h1>Edit Artist</h1>
<%= render :partial => 'form' %>
```

## Strong Parameters
```
# Strong params: create a whitelist of permitted parameters
  private
  def artist_params
    params.require(:artist).permit(:name, :nationality, :dob, :period, :image )
  end
```

## Associations
```
class Order < ActiveRecord::Base
    belongs_to :customer
  end
```
1. belongs_to
  - singular form of the model must be used for association to work.
  - order table must include `customer_id`
  - has `has_one` or `has_many`

```
class Customer < ActiveRecord::Base
  has_many :orders
end
```
2. has_many
  - associate with `belongs_to`
  - pluralizad form model (orders)
  - does not store 'foreign key', key store in `belongs_to`
3. has_one
  - setting one to one use `has_one` & `belongs_to`
4. has_many "through"
  ` has_many :patients, through: :appointments`
5. has_and_belongs_to_many



# Authentication
* we don't store passwords in plain text, we store => `password_digest` (encrypted password)
* User model and database table creation
```
# Create our User model and the migration for creating the users table in the database.
rails generate model User name:string password_digest:string age:integer email:string

# Run the migration generated to create the users table in the database.
rake db:migrate
```
* add `gem 'bcrypt'`
* add `has_secure_password` in user model on top line to set and authenticate encrypted password
* database table must add `password_digest` in order for `has_secure_password` to work.
* `has_secure_password` validation with password:
  - password must be present when User object is created
  - must be <= 72 chracters long
  - password and password_confirmation must match `password == password_confirmation` (validation)


## Session
* Appliction check for cookie containing vlid session ID in client.

### Session Hash
* Collection of key/value pair
* Includes a session_id
* unique to each user
* private between the user and server

* `user_id` - key to effective authorization in Rails, store in session hash.

### Flash Hash
* cleared after each HTTP request - useful for passing error msg
* collection of key/value pair
* `flash[:notice]` or `flash[:success]` success msg
* `flash[:error]` error message
* available for current request and subsequent request (unless `flash.now` is used and only available for current action) before it is destroyed (unless `flash.keep` is used and will keep flash for more than one controller action)
* Example usage :
```
  def create
    user = User.create(user_params)
    if @user.save
      flash[:notice] = 'User was successfully created'
      redirect_to user_path(user)
    else
      flash.now[:error] = 'Could not create user'
      render 'new'
    end
  end
```

## Create a session controller (store userid when sign-in)
`rails generate controller Session new create destroy`

* remove :
`rm app/views/session/create.html.erb`
`rm app/views/session/destroy.html.erb`
`get 'session/new'`
`get 'session/create' `
`et 'session/destroy'. `

* Setup login routes
  ```
  root :to => 'pages#home'

  get '/login' => 'session#new'
  post '/login' => 'session#create'
  delete '/login' => 'session#destroy'
  ```

* Setup session controller actions
  - handle login/logout
  - when login - user_id store in session hash, removed when logout.
```
class SessionController < ApplicationController


  def new
  # This is the action for user login. The view will have the login form template.
  end

  def create
  # This is the action to which the login form post request is posted. It will add the user's id to the session hash, which will be used for authentication and authorization throughout the session.
    user = User.find_by :email => params[:email]
    if user.present? && user.authenticate(params[:password])
      # If a user record with the entered in the form is present AND the user is authenticated (using bcrypt's authenticate method and the password entered in the form), store their id in the session hash and redirect them to the root path.
      session[:user_id] = user.id
      flash[:notice] = "User created!"
      redirect_to root_path
    else
      # If the user cannot be authenticated, redirect them to the login_path.
      flash[:error] = "User could not be created!"
      redirect_to login_path
    end
  end

  # This is the action to which the user sign-out delete request is posted.
  def destroy
    session[:user_id] = nil
    redirect_to root_path
  end
end
```

* Add sign-up/log-in/sign-out links to layout
```
<ul>
  <li><%= link_to("Sign Up", new_user_path %>) %></li>
  <li><%= link_to("Sign In", login_path %>) %></li>
  <li><%= link_to("Log Out", login_path, :method => :delete %>) %></li>
</ul>
```

## Validation
* create
* create!
* save
* save!
* update
* update!
* `:validate => false` to save method

## Test validity
* valid?
* invalid?
* if it's invalid, acceed errors easily - `.errors.messages`

## Validation Helper
1.
```
class User < ActiveRecord::Base
  has_many :books
  validates :column_name, :key => value
end
```

2. acceptance
```
validates :terms_of_service, acceptance: true
# It defaults to "1", if you want to accept something else
validates :terms_of_service, acceptance = { :accept => "yes" }
```

3. validates_associated
`validates_associated :column_name`

4. confirmation
```
validates :email, :confirmation => true
# This should always work with a nil check as well
validates :email_confirmation, :presence => true
```

5. presence - check if it's nil or empty
`validates :email, :presence => true`

[more reference](https://johnofsydney.gitbooks.io/wdi-28/week_05/wk05_day04.html)

# Authorisation
* Since we have many user, in app/controllers/application_controller.rb
```
class ApplicationController < ActionController::Base

  # Before any action is performed, call the fetch_user method.
  before_action :fetch_user

  private

  def fetch_user
    # Search for a user by their user id if we can find one in the session hash.
    if session[:user_id].present?
      @current_user = User.find_by :id => session[:user_id]

      # Clear out the session user_id if no user is found.
      session[:user_id] = nil unless @current_user
    end
  end


  def authorize_user
    redirect_to root_path unless @current_user.present?
  end
end
```

# Rails and jQuery
1. add `gem 'jquery-rails'` under `gem 'bcrypt'` in Gemfile
2. `bundle`
3. restart server
4. Open `applicatoin.js` and remove `require turbo-link` and replace `require jquery`
5. go to browser's console to check jQuery by running `$` or `jQuery`

# Bootstrap
1. add `gem 'bootstrap-sass'` in Gemfile (might need to check the compatibility version)
2. `bundle`
3. Create a new file in app/assets/stylesheets/ and name it `_boostrap-includes.scss` and add
```
@import "bootstrap-sprockets";
@import "bootstrap";
```
4. in application.js, add `require bootstrap-sporckets`, must be under `require jquery`
