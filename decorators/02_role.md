!SLIDE small


## View

    @@@ html
    <dl>
      <dt>Role</dt>
      <dd><%= @user.role %></dd>
    </dl>



## Decorator

    @@@ ruby
    class UserDecorator < ApplicationDecorator
      decorates :user

      def role
        I18n.t model.role,
          scope: :user,
          default: model.role.humanize
      end
    end

