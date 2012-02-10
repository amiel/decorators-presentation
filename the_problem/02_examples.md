!SLIDE subsection

# The Problem #

!SLIDE small

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

!SLIDE small

## Or even... ##

    @@@ html
    