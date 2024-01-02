# Purpose

Recently I've been starting many new Rails apps. I tend to forget to configure the same thing like CORS. This is a guide to help me remember.

Stretch goal: Write a Bash script to automate this.

# Starting a new app

```sh
rails new myapp --database=postgresql --minimal --skip-javascript
```

Options: https://gist.github.com/kirillshevch/1b52f711e66b064416d746f07e834c00

About `--minimal`: https://www.bigbinary.com/blog/rails-6-1-adds-minimal-option-support

# Configuration

## CORS

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

## Other

Database name in `database.yml`.

# Migration

How to generate specific migration syntax by using `generate migration` and file name convention: https://guides.rubyonrails.org/active_record_migrations.html#adding-new-columns

```sh
# Examples:

bin/rails generate migration AddPartNumberToProducts part_number:string
````

# Useful Gems

```ruby
gem 'dotenv-rails'
```

# Bash Aliases

```sh
alias ber='bundle exec bin/rails'
alias berg='bundle exec bin/rails generate'
```