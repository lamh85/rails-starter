Start new app

```sh
rails new myapp --database=postgresql
```

Set up CORS

```ruby
gem 'rack-cors'

# config/initializers/cors.rb
Rails.application.config.middleware.insert_before 0, Rack::Cors do
  if Rails.env == 'development'
    allow do
      origins '*'
      resource '*', headers: :any, methods: :any
    end
  end
end
```

Migration
* How to generate specific migration syntax by using `generate migration` and file name convention: https://guides.rubyonrails.org/active_record_migrations.html#adding-new-columns
  * ```sh
    # Examples:

    bin/rails generate migration AddPartNumberToProducts part_number:string

Other useful gems
```ruby
gem 'dotenv-rails'
```

# Bash Aliases

```sh
alias ber='bundle exec bin/rails'
alias berg='bundle exec bin/rails generate'
```