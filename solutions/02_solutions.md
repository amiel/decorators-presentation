!SLIDE subsection

# Solutions

!SLIDE small

## Fat models, skinny controllers; right?

    @@@ ruby
    class User < ActiveRecord::Base
      ROLES = %w(admin user)
      # ...
      
      def humanize_role
        I18n.t role,
          scope: :user, default: role.humanize
      end
    end
    
Not too bad, but `#humanize_role` is a display-related method

!SLIDE small

## Isn't this what helpers are for?

    @@@ ruby
    module UserHelpers
      def user_role(user)
        I18n.t user.role,
          scope: :user, default: user.role.humanize
      end
      
      def display_user_role(user)
        if user.role
          user_role(user)
        else
          content_tag :span, 'None', class: 'empty'
        end
      end
    end

<!-- 
      def user_url(user)
        if @user.url.present?
          link_to @user.url, @user.url
        else
          content_tag :span,
            "None given", class: 'empty'
        end
      end
 -->

!SLIDE small

## But what happened to an object-oriented approach?

    @@@ ruby
    module UserHelpers
      def user_role(user)
        # ...
      end

      def user_url(user)
        # ...
      end

      def user_role_options
        # ...
      end
    end
