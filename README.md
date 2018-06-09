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

## Setup vue

Add `vue-turbolinks` dependency

```
yarn add vue-turbolinks
```

Add to `app/views/layouts/application.html.erb`

```
<%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
```

```html
    <div data-behaviour="vue">
      <%= yield %>
    </div>
```

Initialize Vue by adding the following code in the `app/javascript/packs/application.js` file:

```javascript
import TurbolinksAdapter from 'vue-turbolinks';
import Vue from 'vue/dist/vue.esm'
import App from '../app.vue'

Vue.use(TurbolinksAdapter)

document.addEventListener('turbolinks:load', () => {
  const app = new Vue({
    el: '[data-behaviour="vue"]',
    components: { App }
  })
})
```

