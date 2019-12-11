---
layout: post
title:      "Making a simple search bar in Ruby with .try"
date:       2019-12-11 17:20:39 +0000
permalink:  making_a_simple_search_bar_in_ruby_with_try
---


The method .try will return nil instead of raising an exception when it's called on something that doesn't respond to it.
We can use this to make our search bar query multiple tables. In this example we will be searching by a book's title or author. 

First we make a form in our view 

``` <%= form_tag(books_path, method: :get) do %>
    <p>Search for a book by title or author</p> 
    <%= text_field_tag :search, params[:search] %>
    <%= submit_tag 'Search', name: nil %>
<% end %>``` 

Then in the controller we use .try which let's us pass in a block, so we tell it to try finding a book then an author.

```def index 
        #handles a get request from the index view to return a book or author by name
        if params[:search]
            @book = Book.try(:find_by, title: params[:search])
            @author = Author.try(:find_by, name: params[:search])
        end 
    end ```
		
Now we go back to the same view as before and add a little conditional under our search form.

```
<% if @book %>
    <h4> - <%= link_to "#{@book.title}", @book %> </h4>   
<%end%>
<% if @author %> 
    <h4> - <%= link_to "#{@author.name}", @author %> </h4>   
<%end%>```


