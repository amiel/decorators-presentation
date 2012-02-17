!SLIDE subsection

# AWESOME


!SLIDE small

## Before

    @@@ html
    <dl>
      <dt>Name</dt>
      <dd><%= @user.name %></dd>
      <dt>Role</dt>
      <dd>
        <%= @user.role.humanize if @user.role %>
      </dd>
      <dt>URL</dt>
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

## After


    @@@ html
    <dl>
      <dt>Name</dt>
      <dd><%= @user.name %></dd>

      <dt>URL</dt>
      <dd><%= @user.url %></dd>

      <dt>Role</dt>
      <dd><%= @user.role %></dd>
    </dl>
