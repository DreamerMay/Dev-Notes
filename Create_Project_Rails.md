#Create Project CRUD in Rails

## Create Rails Project
create with PostgreSQL - for heroku
`rails new tuna --skip-git -T -d postgresql`

## Add Gems required
* `gem 'jquery-rails'`
    ```
    Application.js
    add this before turbolinks and tree
    //= require jquery
    as long as you include jquery , remove
    //= require turbolinks
    ```
*  gem 'pry-rails'
*  gem 'pry-stack_explorer'
*  gem 'annotate'
*  gem 'meta_request'
*  gem 'jquery-rails'

rails db:create

## Generate Model
`rails generate model Artist name:text image:text`
* :date
* user for password use `password_digest:text`
* avoid writing in hand `rails generate migration add_species_to_kitten`

## Setup Model Association
* for password `has_secure_password`
* `validation :email, :presence => true, uniqueness => true`

## Setup Join table
 `rails generate migration create_genres_songs`
 * setup joint table
   ```
    t.integer :genre_id`
    t.integer :song_id`
   ```

rails db:migrate

##Password Encryption
`gem 'bcrypt'`

add below in User Model
`has_secure_password`

## Setup routes
```
  root :to => 'pages#home'

  resource :users
  resource :trips
  resource :lists
```

## Setup controller

## Setup views
