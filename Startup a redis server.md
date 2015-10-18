##Starting a redis server

1. Download and install Redis server to your local system and server.

With Homebrew: 

> brew install redis

On Ubuntu: Follow this tutorial: [Tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-redis)

2. Once installed install a nodejs server to your own project. You can use a sample server. We also need to install Foreman. Install this in your root project folder.

> gem install foreman

> git clone git://github.com/mikeatlas/realtime-server.git

> cd realtime-server

> sudo npm install

3. Time to start the servers.

> redis-server

> foreman start

> rails server

It's important to start your redis server first. Foreman searches for the redisserver and communicates with it. Rails server obviously runs your project.

### Test your redis server:
The standard channel where the realtime-server listnes to is "realtime_msg".
You can check if your publish/subscribe system is working in rails console:

> $redis.subscribe('realtime_msg') do |on|

> on.message do |channel, msg|

> puts "I heard [#{msg}] on channel [#{channel}]"

> end

> end

Now run this to publish command:

> $redis.publish 'realtime_msg', 'Test message'.to_json











