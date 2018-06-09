# Rails with vue

## Create a new Rails project
Create a new plain rails project:
```
rails new rails-vue
```

## Add webpacker

Add the webpacker gem to the `Gemfile`:

```
gem 'webpacker', '~> 3.5'
```

Install webpacker:

```
rails webpacker:install
```

Note: it is possible to create a new rails project with webpack installed
```
rails new rails-vue --webpack
```

## Install vue

```
rails webpacker:install:vue
```

Note: it is possible to create a new rails project with webpack and vue installed
```
rails new rails-vue --webpack=vue
```

## Adding a landing page

```
rails g controller LandingPage index
```

Set `landing_page#index` as root

config/routes.rb
```
root 'landing_page#index
```