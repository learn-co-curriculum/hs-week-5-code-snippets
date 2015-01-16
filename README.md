---
tags: sessions, kids, ruby, advanced, code snippets
language: ruby
level: 2
type: code snippets
---

## The Code Cherry On Top

We just need to make one small change to the Sinatra configurations in our application controller to enable sessions in our application by adding the following lines of code:

```ruby
enable :sessions
set :session_secret, 'fwitter'
```

You can actually set your session secret to anything that you want. It will be used to create a session_id (a unique string of numbers and letters) that is stored in a browser cookie. (If you missed class check out the All About Cookies section.)

This is a pretty minimal security feature, but the basic idea is that setting your :session_secret to a word that other people don’t know makes it harder for someone to create a fake session_id and hack into your site without signing up or signing in.

The configure block in your application controller should now look like this:

```ruby
class ApplicationController < Sinatra::Base
  
  configure do
    set :public_folder, 'public'
    set :views, 'app/views'
    enable :sessions
    set :session_secret, 'fwitter'
  end

end
```

You're ready to session! If you missed class, move on to the Sinatra Sessions Walkthrough.
