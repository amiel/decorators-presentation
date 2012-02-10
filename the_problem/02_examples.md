!SLIDE subsection

# The Problem #

## OR, how much logic is ok in your views ##


!SLIDE small

## How's this? ##

    @@@ html
    <div id="cart">
      <% if cart.value.zero? %>
        <span class="empty">empty</span>
      <% else %>
        <%= number_to_currency cart.value %>
      <% end %>
    </div>

!SLIDE small

    @@@ html
    <dl>
      <dt>Url:</dt>
      <dd>
        <% if @user.url.present? %>
          <%= link_to @user.url, @user.url %>
        <% else %>
          <span class="empty">
            None given
          </span>
        <% end %>
      </dd>
    </dl>

Example from from http://railscasts.com/episodes/286-draper

!SLIDE small

## Or even... ##

    @@@ html
    <div id="profile">
      <%= link_to_if @user.url.present?,
        image_tag("avatars/#{avatar_name(@user)}",
          class: "avatar"),
        @user.url %>
      <h1><%= link_to_if @user.url.present?,
        (@user.full_name.present? ?
          @user.full_name :
          @user.username),
        @user.url %></h1>
      ...

      
Example from from http://railscasts.com/episodes/286-draper
      