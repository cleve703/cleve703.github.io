---
layout: post
title: How to Delete from a Join Table in Rails
date: 2020-05-23 09:23:43 -0500
tags: [rails, ruby]
image: InnerJoin.svg
---
While working on a project within [theOdinProject's](https://theodinproject.com) curriculum, I found myself facing a challenge: How to create a link in my Rails app that would delete the record in the join table that establishes a relationship between two objects. In my specific project, "private-events," I had several users, and several events, which were connected through a join table of invitations. My goal was to build a dynamic link to delete the record in the join table that connects the user with the event he was attending.

For greater context on the structure of my models, I've included a screenshot of each model below. Also, feel free to view the whole app at [Github](https://github.com/cleve703/private-events).

![app/models/user.rb](/assets/img/user-model-pe.png)

![app/models/event.rb](/assets/img/event-model-pe.png)

![app/models/invitation.rb](/assets/img/invitation-model-pe.png)

The thing that made this situation challenging was that I needed to be able to identify both an event and a user, and send that data with your delete method in order to successfully remove the record from the invitation (join) table. The way I overcame this challenge was to alter my routes so that both the event ID and the attending user ID were stored in the link to delete the invitation.

![config/routes.rb](/assets/img/config-routes-pe.png)

Upon updating the routes, you can confirm how the routes are structured by running "rails routes" in the terminal. In order to cut down on extraneous information, my preferred method of doing this is to filter my results with "grep." For example, `rails routes | grep invit` will yield only routes involving invitations. In my situation, the route for deleting invitations is `/events/:event_id/invitations/:id`. In other words, if we wish to delete an invitation to event #3 for user #8, the path would be `/events/3/invitations/8.`

Now, it's just a matter of building a link to that path that utilizes the "delete" method. I used the following for my link: `<%= link_to 'Uninvite', "#{@event.id}/invitations/#{attendee.id}", method: 'delete' %>`.