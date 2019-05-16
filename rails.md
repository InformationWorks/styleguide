### Routes

* Use only single quotes for defining routes.

### Gemfile

* Use only single quotes for listing gems.

### Migrations

* Use references instead of integer id.

#### Good

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

#### Bad

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

## Reference Links

* [Rubocop Rails Style Guide](https://github.com/rubocop-hq/rails-style-guide)
* [Rubocop Ruby Style Guide](https://github.com/rubocop-hq/ruby-style-guide)
* [Airbnb Ruby Style Guide](https://github.com/airbnb/ruby)
* [Shopify Ruby Style Guide](https://shopify.github.io/ruby-style-guide/)
* [Ruby on Rails Official Coding Guide](https://guides.rubyonrails.org/contributing_to_ruby_on_rails.html#follow-the-coding-conventions)
