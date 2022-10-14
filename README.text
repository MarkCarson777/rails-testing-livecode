RAILS BASIC TESTING

Step 1 - Create your rails application

rails new airbnb-funsies

Step 2 - Add Bootstrap to the <head> in app/views/layouts/application.html.erb

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

Step 3 - Build your schema

rails db:migrate

Step 4 - Generate a new test in test/system

rails g system_test flats

Step 5 - Create the test in test/system/flats_test.rb

class FlatsTest < ApplicationSystemTestCase
test "visiting flats page" do
visit "/"

    assert_selector "h1", text: "Flats"

end
end

**Run test**

Step 6 - Enable headless browsers in test/application_system_test_case.rb

require "test_helper"

class ApplicationSystemTestCase < ActionDispatch::SystemTestCase
driven_by :selenium, using: :headless_chrome, screen_size: [1400, 1400]
end

**Run test**

Step 7 - Create a route in config/routes.rb

Rails.application.routes.draw do
root to: "flats#index"
end

**Run test**

Step 8 - Generate a controller

rails g controller flats

**Run test**

Step 9 - Create an action in app/controllers/flats_controller.rb

require "open-uri"

class FlatsController < ApplicationController
def index
url = "https://raw.githubusercontent.com/lewagon/flats-boilerplate/master/flats.json"
@flats = JSON.parse(URI.open(url).read)
end
end

**Run test**

Step 10 - Create a view in app/views/flats called index.html.erb

<h1>Flats</h1>
<ul>
  <% @flats.each do |flat| %>
    <li>
      <h2><%= flat["name"] %></h2>
      <p>💰 <%= flat["price"] %> <%= flat["priceCurrency"] %></p>
    </li>
  <% end %>
</ul>

**Run test**

Step 11 - You should be error free

FIN
