!SLIDE small

## Decorator

    @@@ ruby
    class UserDecorator < ApplicationDecorator
      decorates :user

      def url
        if model.url.present?
          h.link_to model.url, model.url
        else
          h.content_tag :span, 'None', class: 'empty'
        end
      end
    end


!SLIDE small

## View

    @@@ html
    <dl>
      <dt>URL</dt>
      <dd><%= @user.url %></dd>
    </dl>
    
