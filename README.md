# love2d-callback-timer
A simple timer lib for love2d with callbacks.

Originally made to send some stuff with [sock.lua](https://github.com/camchenry/sock.lua) after some time, maybe it can help someone other.
Feel free to use and/or modify.

#### Parameters
- name
- time until callback (seconds)
- callback function
- loop (default: false)

# Usage
Simple, just require Timer and do stuff like this:

```lua
-- Require the Timer
local CallbackTimer = require 'CallbackTimer';

function love.load()
  -- Add new basic timer
  CallbackTimer:add('basicTimer', 5, function() 
    -- Trigger Event, do some debugging stuff, send stuff to server/client, ...
    -- For now, we just print something
    print('something');
  end)
  
  -- A new timer that loops
  CallbackTimer:add('loopedidoop', 5, function() 
    print('I get called every 5 seconds');
  end, true)
  
  -- Start the timers
  CallbackTimer:start('basicTimer');
  CallbackTimer:start('loopedidoop');
end

function love.update(dt)
  CallbackTimer:update(dt);
end
```
