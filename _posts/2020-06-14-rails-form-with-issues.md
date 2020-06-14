---
layout: post
title: Rails Helper form_with Not Working As Expected
date: 2020-06-14 16:23:32 -0500
tags: [rails, ruby]
image: error.jpg
---
I recently encountered a stumbling block when using `form_with` in a Rails application I was building. No matter what I tried, the form did not work as I expected it to -- on submitting the form, nothing would happen. The button appears to press successfully, the parameters get sent to the server, but the information displayed in the current view would not change.

After hours of troubleshooting, Googling, and getting really frustrated in general, I discovered my blunder. Apparently, `form_with` was introduced in Rails 5.1, and with it came a new default form behavior: forms are remote by default, and are submitted with Ajax. Unfortunately, many of the learning materials currently available predate this change, so learners like me don't immediately know to add `local: true` to our form arguments. When I changed my form as follows, everything began to work as expected:

```
<%= form_with model: @flight, scope: 'flight', method: 'get', local: true do |f| %>
  <%= f.label(:origin_airport, 'Origin airport code:') %>
  <%= f.collection_select(:origin_airport, Airport.all, :id, :airport_code, {selected: @search_criteria[:origin_airport]}) %>
  <%= f.label(:destination_airport, 'Destination airport code:') %>
  <%= f.collection_select(:destination_airport, Airport.all, :id, :airport_code, {selected: @search_criteria[:destination_airport]}) %>
  <%= f.label(:num_passengers, 'Number of passengers:') %>
  <%= f.select(:num_passengers, options_for_select([['1', 1], ['2', 2], ['3', 3], ['4', 4]], @search_criteria[:num_passengers])) %>
  <%= f.label(:departure_date, 'Departure date:') %>
  <%= f.select(:departure_date, options_for_select(Flight.departure_dates_formatted, @search_criteria[:departure_date])) %>
  <%= f.submit('Search') %>
<% end %>
```

Ajax is a more modern means of integrating forms into your application, and it allows for partial rendering of your pages. In other words, the user can submit form data, and the server will return only the pertinent information back to the browser so that data can be updated in the current view. This makes for a faster, more seamless experience, while reducing the load on your server. I plan to do a post on Ajax in the near future. Please leave a comment about any stumbling blocks you've encountered while coding a Rails application.