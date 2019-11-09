---
layout: post
title:      "Models, Views, and Controllers in an App"
date:       2019-11-09 11:46:41 -0500
permalink:  models_views_and_controllers_in_an_app
---


Models, Views, and Controllers are a framework for organizing a program's files.  You separate code by its function.

I'm studying Sinatra right now, and at first I had a hard time trying to delineate these concepts from each other.  In a Ruby App, you will need these 3 parts.  To break it down simply:

A **model** is what things are.

A **view** is what things look like.

A **controller** is what things do.



**A controller looks like this.  There's a lot of "getting" and "setting".  It shows what an object does.**

class ApplicationController < Sinatra::Base
  register Sinatra::ActiveRecordExtension
  set :session_secret, "my_application_secret"
  set :views, Proc.new { File.join(root, "../views/") }

  get '/' do
    erb :index
  end
end


**A model looks like this.  It defines what a genre is in the application.**

class Genre < ActiveRecord::Base
  has_many :song_genres
  has_many :songs, through: :song_genres
  has_many :artists, through: :songs

  def slug
    name.downcase.tr(' ', '-')
  end

  def self.find_by_slug(slug)
    Genre.all.find { |genre| genre.slug == slug }
  end
end


**A view looks like this.  It describes how the information will actually look like to the user.**

  
<ul>
  <% @artist.songs.each do |song| %>
    <li><a href="/songs/<%= song.slug %>"><%= song.name %> </a></li>
  <% end %>
</ul>

<ul>
  <% @artist.genres.each do |genre| %>
    <li><a href="/genres/<%= genre.slug %>"><%= genre.name %> </a></li>
  <% end %>
</ul>



The above examples are from my current lab.  As you can see, the controllers and models are Classes.  The view is in html, because it is the visual look of things.



