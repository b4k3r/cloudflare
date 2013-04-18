NOTICE
------

In version 1.1.x some functions were renamed. Please see documentation.


CloudFlare
==========

It is a Ruby wrapper for the CloudFlare API.

Official home page is [here](https://github.com/B4k3r/cloudflare). The complete [RDoc](http://rdoc.info/github/B4k3r/cloudflare/) is online.

Visit also a CloudFlare API documentation:

-    [Client](http://www.cloudflare.com/docs/client-api.html)
-    [Host](http://www.cloudflare.com/docs/host-api.html)

Installation
------------

```
gem install cloudflare
```

Or, if use Rails, include the gem in your Gemfile:

```
gem 'cloudflare'
```

Usage
-----

**Example for Client API:**

```
require 'cloudflare'

cf = CloudFlare.new('user_api_key', 'user_email')
output = cf.rec_new('domain.com', 'A', 'subdomain', '212.11.6.211', 1)

if output['result'] == 'success'
  	puts 'Successfuly added DNS record'
else
	puts output['msg'] # error message
end
```

**Example for Host API:**

```
require 'cloudflare'

cf = CloudFlare.new('host_api_key')
output = cf.create_user('john@example.com', 'secret', 'john')

if output['result'] == 'success'
  	puts output['msg']
  	puts "Your login is #{output['response']['cloudflare_username']}" # => john
else
  	puts output['msg'] # error message
end
```

License
-------

Copyright &copy; 2012 - 2013. It is free software, and may be redistributed under the terms specified in the MIT-LICENSE file.






