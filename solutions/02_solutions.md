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

!SLIDE small

## Isn't this what helpers are for?

    @@@ ruby
    module UserHelpers
      def user_url(user)
        if @user.url.present?
          link_to @user.url, @user.url
        else
          content_tag :span,
            "None given", class: 'empty'
        end
      end
    end

!SLIDE small

## What happened to an object-oriented approach?

    @@@ ruby
    module UserHelpers
      def user_url(user)
        # ...
      end
      
      def user_full_name(user)
        # ...
      end
      
      def user_avatar(user)
        # ...
      end
    end
