!SLIDE subsection

# The Problem #

## OR, how much logic is ok in your views ##


!SLIDE small

## How's this? ##

    @@@ html
    <dl>
      <dt>Role</dt>
      <dd>
        <% @user.role.humanize if @user.role %>
      </dd>
    </dl>

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

!SLIDE small

## or even... ##

    @@@ html
    <div id="profile">
      <%= link_to_if @user.url.present?,
        image_tag("avatars/#{avatar_name(@user)}",
          class: "avatar"),
        @user.url %>
      <h1>
        <%= link_to_if @user.url.present?,
          (@user.full_name.present? ?
            @user.full_name :
            @user.username),
          @user.url %>
      </h1>
      ...
