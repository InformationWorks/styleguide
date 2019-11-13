### Use below tools in the project to maintain code quality

* [RDoc](https://ruby.github.io/rdoc/)
* [Simplecov](https://github.com/colszowka/simplecov)
* [Rubocop](http://www.rubocop.org/en/stable/)

### Models

#### Code Folding

Below are the regions for the Ruby classes. ([Example](https://gist.github.com/harshalbhakta/39a332a5792195a4380bb28b5cefc964))


````ruby
class User

  #region Setup
  
  #region Validations
  
  #region Validation Functions
  
  #region belongs_to
  
  #region has_one
  
  #region has_many
  
  #region scopes
    
  #region before_callbacks
  
  #region after_callbacks
  
  #region Public Class Methods
  
  #region Public Instance Methods
  
  private
  
  #region Private Class Methods
  
  #region Private Instance Methods

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
