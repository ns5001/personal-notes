## Javascript and rails stuff

### Serializers
----

AMS is only concerned with the number of the relationship, not the direction. 
So it only knows has_one and has_many. This is because it's not describing a data/model relationship, 
but the relationship as defined by the JSON. [Source](https://learn.co/tracks/full-stack-web-development/rails-and-javascript/building-apis/using-active-model-serializer)


### Enable root key when using ActiveModelSerializer (v.10.x)

[How to add root key](https://github.com/rails-api/active_model_serializers/blob/master/docs/howto/add_root_key.md)

Create a new file in initializers, call it `json_api.rb` and add the below

```ruby
require 'active_model_serializers/register_jsonapi_renderer'

ActiveModelSerializers.config.adapter = :json
```

----

Some labs use older version of Active Model Serializer and the lessons are not up to date.

1. In order to display root key specify adapter

```ruby
render json: @product, adapter: :json
```

2. I order to display nested attributes use include option

```ruby
render json: @product, adapter: :json, include: { orders: [:products] }
```

The solution is using 0.9+ and current AMS master is 0.10+. Most likely version related.