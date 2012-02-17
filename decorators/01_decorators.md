!SLIDE subsection

# Enter Decorators

## with the draper gem


!SLIDE small

## Controller

    @@@ ruby
    def show
      @user = UserDecorator.find params[:id]
    end
