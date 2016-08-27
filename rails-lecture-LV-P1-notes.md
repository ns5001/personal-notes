## These are notes taken while watching Rails Lecture - LV - Part 1 - Take 1

[Learn lesson](https://learn.co/tracks/full-stack-web-development/rails/introduction-to-rails/rails-hello-world)

[Video URL](https://www.youtube.com/watch?v=KKQ8lpEyw2g)

Rail Routing Image

![Rail Routing](http://i.imgur.com/lGvsqIA.png)

Basic Feature Concept

![Basic Feature Concept](http://i.imgur.com/He1p0wy.png)

## Simple blog app using rails

#### Mapping out URLs

* GET /posts -> show an index of all my blog posts
* GET /posts/:id -> show a particular blog post by id
* GET /posts/new -> a form for new blog posts
* POST /posts -> submitting the new blog post
* GET /posts/:id/edit -> editing a blog post

### Planning out the project:

* URLS
* Routes
* Controller Actions
* Models
* Database
* Views

#### Rails Generators:

Auto generates various files based on inputs

* Scaffold -> Controller, routes, models, migration, views (most extensive)
* Resource -> Controller, routes, models, migration
* Controller -> Controller, views, assets
* Model -> Model, Migration (for that model)
* Migration - > Migration

eg: generate a controller
`rails genearate controller static about team`
                                    actions


#### Detailed steps

1. Plan out some URLs for the feature you are building
2. Ask, does my database need to change? Yes, I need a new table.
    * Do I have the corresponding model? No. use the model generator.
4. After generating new model, migrate DB. Confirm models
    * Use `rails console` command to make sure models are legit


#### Active Record Conventions

* Table name: lowercase plural name of model - eg: posts
* Model filename: singular lowercase (underscored) - eg: post.rb
* Class name for model: singular camelcase - eg: Post


#### Routes controllers and actions

A Rails route maps a URL to a Controller and Action
                                Class        Method

rails route examples:

```ruby
get({'/hello_world' => 'posts#home'    })
        URL             controller#action
                        (class#method)
```

```ruby
get '/posts' => 'posts#index'
```

```ruby
get '/about' => 'static#about'
get '/team' => 'static#team'
```

![PostsController](http://i.imgur.com/y7jYRgr.png)

**Because of Implicit Rendering Convetion**

If you dont give specific (explicit) rendering instructions, then rails falls back on implicit.

Rails looks for:

`app/views/[conroller_name]/[action_name].html.erb`

### More on routes

* `rake routes` shows the routing table
    * names
    * method (action)
    * urls
    * mapping (controller#action)
* while in rails console `app.route_name_path` returns the route
    * eg: app.about_path

When building out the views. You want to rely on the built in rails methods (eg: route helpers) as
much as possible.

Prefer this:
```ruby
 <%= link_to("About Page", about_path) %>
```

Over this:
```html
    <a href="/about">About Page</a>
```

#### Route variables

```ruby
get '/posts/:id' => 'posts#show', :as => :post
```

Whenever a route has a route variabled (in the above case [:id]), the route helper you would use to generate that route accepts an argument for each variable in this route.

`app.post_path(argument)`

NOTE: When using `app.post_path(post_instance)` Rails will automatically try to get the ID of said instance. **That is the prefered convention** over passing in ID directly.

EG:

Prefer this:
```ruby
    <%= link_to(post.title, post_path(post)) %>
```

OR (the most abstract version)
```ruby
    <%= link_to(post.title, post) %>
```

Over this:
```html
    <a href="/posts/<%= post.id %>"><%= post.title%></a>
```

### Additional Notes

* Instance variables we define in our controller actions get passed to the views.
* `render` command that is used in controllers is similar to `erb` in sinatra


### What was covered:

* The Rails Application Layout
* Migration Generator
* Model Generator
* Controller Generator
* Controllers being classes and actions being methods
* Routes
* Mapping a URL to a Controller Action through routes
* Implicit Rendering
* Explicit Rendering



