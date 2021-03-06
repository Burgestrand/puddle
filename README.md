# Performer

[![Build Status](https://travis-ci.org/Burgestrand/performer.svg?branch=master)](https://travis-ci.org/Burgestrand/performer)
[![Code Climate](https://codeclimate.com/github/Burgestrand/performer.png)](https://codeclimate.com/github/Burgestrand/performer)
[![Gem Version](https://badge.fury.io/rb/performer.png)](http://badge.fury.io/rb/performer)

```
gem install performer
```

Performer is a tiny gem for scheduling blocks in a background thread,
and optionally waiting for the return value.

## Usage

``` ruby
performer = Performer.new

result = performer.sync { 2 + 1 }
result # => 3

future = performer.async { 2 + 1 }
future.value # => 3

future = performer.shutdown do
  puts "Performer has been properly shutdown."
end

future.value # wait for shutdown
```

See documentation for [Performer](http://rdoc.info/github/Burgestrand/performer/master/Performer)
and [Performer::Task](http://rdoc.info/github/Burgestrand/performer/master/Performer/Task).
