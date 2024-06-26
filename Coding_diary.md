# active-record-migrations
Following https://guides.rubyonrails.org/active_record_migrations.html
1. Connected to sqlite3 db via this URL: `jdbc:sqlite:storage/development.sqlite3`
2. `rails generate migration CreateUsers`
3. `rails generate migration CreateProducts`
4. `bin/rails generate migration AddDetailsToProducts part_number:string price:decimal`
5. `bin/rails generate migration RemovePartNumberFromProducts part_number:string`
6. `bin/rails generate migration AddUserRefToProducts user:references`
7. `bin/rails generate migration CreateJoinTableCustomerProduct customer product`
8. `rails db:migrate`
9. Stopped at [2.6 Model Generators](https://guides.rubyonrails.org/active_record_migrations.html#model-generators)

# rubyonrails-getting-started
Following https://guides.rubyonrails.org/getting_started.html
1. `bin/rails generate controller Articles index --skip-routes`
    - Created ArticlesController and its index action
    - Now visit http://localhost:3000/articles, and see our text displayed!
2. `bin/rails generate model Article title:string body:text`
    - `bin/rails db:migrate`
    - `article = Article.new(title: "Hello Rails", body: "I am on Rails!")`
    - `article.save`
    - `article`
3. `bin/rails routes`
    - Created Resourceful Routing that can be seen with routes command
4. Site http://127.0.0.1:3000/articles/new is accessible from the browser if `app/views/articles/new.html.erb` is created even without defining `def new` controller in `app/controllers/articles_controller.rb`
5. `bin/rails generate model Comment commenter:string body:text article:references` + `bin/rails db:migrate`
    - Create a Comment model to hold a reference to an article
6. `bin/rails generate controller Comments`
7. ` bin/rails generate migration AddStatusToArticles status:string ` + `bin/rails generate migration AddStatusToComments status:string`
    - Added status to Articles and Comments
8. Now if article or comment status is `archived` it is not displayed
