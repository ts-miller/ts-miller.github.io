---
layout: post
title:      "Posting Messages using Sinatra/Flash"
date:       2020-10-11 19:12:43 +0000
permalink:  posting_messages_using_sinatra_flash
---


While we hope that our website has clear enough instruction and a straight forward interface, there will undoubtably be user errors that will redirect our user to pages that they don't expect. Sometimes it will be a password incorrectly entered or a user name that is already taken upon signup. However, if a user is redirected but no explanation is given for why, it will end with them being quite confused. It's imperative that we can communicate with the user.

That's where Sinatra/Flash comes in. It's a very usefull gem that also requires the use of sessions. It allows the programmer to set a message that will be displayed on the next page that is displayed (often through a redirect). Here is how you set it up and use it:

**Setup**

First, make sure you install the gem from your terminal with:

```
$ gem install sinatra-flash
```

or by adding `gem sinatra-flash` to your gemfile and then runing `bundle install` from the terminal.

It was not very clear in the documentation but I had trouble getting it to work at first because you have to add a line of code to your Application Controller - `register Sinatra::Flash`

```
class ApplicationController < Sinatra::Base

   configure do
      register Sinatra::Flash
   end
end
```

From there, in your layout.erb file, add this block just before your yield:

```
<% flash.keys.each do |type| %>
       <div class="<%= type %> alert-box radius">
            <%= flash[type] %>
            <a href="#" class="close">&times;</a>
       </div>
<% end %>  
```

**Use**

And then, this is how it's used in the controller to add messages:

```
 if pc.save
         flash[:success] = "Added PC successfully"
         redirect "/users/#{session[:user_id]}"
 else
         flash[:error] = "Make sure all fields are filled out correctly."
         redirect '/pcs/new'
 end
```

You can also add classes to your CSS to put the alert in a box and specify what color different kind of alerts should be:

```
.alert-box {
    border-style: solid;
    border-width: 1px;
    display: block;
    font-size: 0.72222rem;
    font-weight: normal;
    margin-bottom: 1.11111rem;
    padding: 0.77778rem 1.33333rem 0.77778rem 0.77778rem;
    position: relative;
    transition: opacity 300ms ease-out;
    background-color: #f04624;  /* sets default color */
    border-color: #791403;  /* sets default color */
    color: #FFFFFF;
}

.error {
    background-color: #f04624;
    border-color: #791403;
    color: #FFFFFF;
}

.success {
    background-color: #0aa55a;
    border-color: #014625;
    color: #FFFFFF;
}
```

