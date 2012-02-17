!SLIDE small


## View
    @@@ html
    <%= f.input :role,
        collection: UserDecorator.role_options
    %>

!SLIDE small

## Decorator

    @@@ ruby
    class UserDecorator < ApplicationDecorator
      decorates :user

      def role
        self.class.humanize_role model.role
      end

      def self.humanize_role(role)
        I18n.t role, ...
      end
      
      def self.role_options
        User::ROLES.map { |r| [humanize_role(r), r] }
      end
    end

