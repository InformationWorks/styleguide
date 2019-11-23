### Use below tools in the project to maintain code quality

* [RDoc](https://ruby.github.io/rdoc/)
* [Simplecov](https://github.com/colszowka/simplecov)
* [Rubocop](http://www.rubocop.org/en/stable/)

### Models

#### Code Folding

Below are the regions for the Ruby classes. ([Example](https://gist.github.com/harshalbhakta/39a332a5792195a4380bb28b5cefc964))


````ruby
class User

  #=region Setup
  #=endregion
  
  #=region Validations
  #=endregion
  
  #=region Validation Functions
  #=endregion
  
  #=region belongs_to
  #=endregion
  
  #=region has_one
  #=endregion
  
  #=region has_many
  #=endregion
  
  #=region scopes
  #=endregion
    
  #=region before_callbacks
  #=endregion
  
  #=region after_callbacks
  #=endregion
  
  #=region Public Class Methods
  #=endregion
  
  #=region Public Instance Methods
  #=endregion
  
  private
  
  #=region Private Class Methods
  #=endregion
  
  #=region Private Instance Methods
  #=endregion

end

````

### Routes

* Use only single quotes for defining routes.

### Gemfile

* Use only single quotes for listing gems.

### Migrations

#### Database Fields Naming Convention

| Field Type  |  Prefix  | Suffix  | Example |
|---|---|---|----|
| Date  | - | _on | submitted_on |
| Datetime  | - | _at  | approved_at |
| Boolean  | is_ or has_ | - | is_active or has_access |

#### Use references instead of integer id.

##### Good

````ruby
class CreateStates < ActiveRecord::Migration[5.0]
  def change
    create_table :states do |t|
      .
      t.references :country, null: false, foreign_key: true
      .
    end
  end
end
````

##### Bad

````ruby
class CreateStates < ActiveRecord::Migration[5.0]
  def change
    create_table :states do |t|
      .
      t.integer :country_id, index: true
      .
    end
  end
end
````

### Namespacing Models & Controllers

Always use module nesting vs :: syntax for defining models and controllers within namespace.

#### Good

````ruby
# /app/models/billing/subscription.rb
module Billing
  class Subscription < ApplicationRecord
  end
end

# /app/controllers/billing/subscriptions_controller.rb
module Billing
  class SubscriptionsController < ApplicationController
  end
end
````

#### Bad

````ruby
# /app/models/billing/subscription.rb
class Billing::Subscription < ApplicationRecord
end

# /app/controllers/billing/subscriptions_controller.rb
class Billing::SubscriptionsController < ApplicationController
end
````

## Reference Links

* [Ruby Style Guide](https://rubystyle.guide/)
* [Rubocop Rails Style Guide](https://github.com/rubocop-hq/rails-style-guide)
* [Rubocop Ruby Style Guide](https://github.com/rubocop-hq/ruby-style-guide)
* [Airbnb Ruby Style Guide](https://github.com/airbnb/ruby)
* [Shopify Ruby Style Guide](https://shopify.github.io/ruby-style-guide/)
* [Ruby on Rails Official Coding Guide](https://guides.rubyonrails.org/contributing_to_ruby_on_rails.html#follow-the-coding-conventions)
