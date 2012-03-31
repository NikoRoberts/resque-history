# Resque Pause [![alt build status][1]][2]

[1]: https://secure.travis-ci.org/ilyakatz/resque-history.png?branch=master
[2]: http://travis-ci.org/#!/ilyakatz/resque-history


A [Resque][rq] plugin. Requires Resque

resque-history adds functionality record recently history of job executions

Usage / Examples
----------------

### Single Job Instance

```ruby
    require 'resque-history'

    class UpdateNetworkGraph
      extend Resque::Plugins::History
      @queue = :network_graph

      def self.perform(some_id)
        do_stuff(some_id)
      end
    end
```

Resque-Web integration
----------------------

You have to load ResquePause to enable the Pause tab.

```ruby
    require 'resque-pause/server'
```

Install
=======

    $ gem install resque-pause
    
Add to routes.rb file

    require 'resque-history/server'

[rq]: http://github.com/defunkt/resque