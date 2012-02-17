!SLIDE subsection

# The Problem

## View logic

!SLIDE small

## Not too bad

    @@@ html
    <dl>
      <dt>Role</dt>
      <dd>
        <%= @user.role.humanize if @user.role %>
      </dd>
    </dl>

!SLIDE small

## but then...

    @@@ html
    <dl>
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

## or even...

    @@@ html
    <%= f.input :role,
      collection: User::ROLES.map { |r|
        [r, r.humanize]
      }
    %>

## which becomes

    @@@ html
    <%= f.input :role,
      collection: User::ROLES.map { |r|
        [r, I18n.t(r, default: r.humanize, ...)]
      }
    %>
