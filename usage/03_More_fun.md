!SLIDE title center

# More interesting use cases

!SLIDE title center

## Use case #3
# Rate limiting

!SLIDE code small

## Rate limiting Rack middleware

    @@@ruby
    require 'rack'
    require 'rack/throttle'
    require 'application'

    # Limit to 1000 requests per day, by ip address.
    use Rack::Throttle::Daily, :max        => 1000,
                               :cache      => Redis.new,
                               :key_prefix => :throttle

    run Application

!SLIDE title center

# rack-throttle

### github.com/datagraph/rack-throttle

!SLIDE title center

## Use case #4
# Feature switches

!SLIDE bullets incremental

# Feature switch?

* Conditionally rollout features to a subset of users
* Activate a feature for a percentage of users
* Deactivate a feature if it breaks

!SLIDE code small

    @@@ruby
    $rollout = Rollout.new(Redis.new)

    # Check if the feature is active for a user
    $rollout.active?(:chat, current_user)

    # Activate a feature for a percentage of users
    $rollout.activate_percentage(:chat, 20)

    # If a feature breaks, deactivate it for everyone
    $rollout.deactivate_all

!SLIDE bullets incremental

# More use cases!

* Job queues
* A/B testing
* Fast autocomplete
* Pub-sub
* Realtime event tracking

!SLIDE bullets incremental

# Other coolness

* [redis-objects](https://github.com/nateware/redis-objects)
* [object-hash mapping](https://github.com/soveran/ohm)
* [degrade](https://github.com/jamesgolick/degrade)

!SLIDE bullets small

# Links

* [github.com/ezmobius/redis-rb](https://github.com/ezmobius/redis-rb)
* [github.com/jodosha/redis-store](https://github.com/jodosha/redis-store)
* [github.com/datagraph/rack-throttle](https://github.com/datagraph/rack-throttle)
* [github.com/jamesgolick/rollout](https://github.com/jamesgolick/rollout)
