!SLIDE title center

## Use case #1
# Caching

!SLIDE code

## Cache store Rails 3.x

    @@@ruby
    # Gemfile
    gem 'redis'
    gem 'redis-store', '1.0.0.rc1'

    # config/environments/production.rb
    config.cache_store = :redis_store

!SLIDE code small

## Rack::Cache Redis store

    @@@ruby
    require "rack"
    require "rack/cache"
    require "redis-store"
    require "application"

    use Rack::Cache,
      :metastore   => 'redis://localhost:6379/0/metastore',
      :entitystore => 'redis://localhost:6380/0/entitystore'
    run Application.new

!SLIDE title center

## Use case #2
# Sessions

!SLIDE code

## Rack::Session Redis store

    @@@ruby
    require "rack"
    require "redis-store"
    require "application"

    use Rack::Session::Redis
    run Application.new

!SLIDE code small

## Rack::Session Redis store + Rails

    @@@ruby
    # Gemfile
    gem 'rails', '3.0.10'
    gem 'redis'
    gem 'redis-store', '1.0.0.rc1'

    # config/initializers/session_store.rb
    App::Application.config.session_store :redis_session_store

!SLIDE title center

# redis-store

    gem install redis-store
