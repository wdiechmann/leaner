# Not Done Yet

## Install GitLabHQ for local github like service
https://github.com/gitlabhq/gitlabhq/blob/master/doc/install/installation.md

## Use Loader.IO for testing resilience and stamina of the service once operational

## Validate MX records for supplied email addresses
See the implementation here: http://2n.pl/blog/validating_email_address


## Use Postgresql and custom_fields to allow STI
A very convincing example of how to implement STI: https://netguru.co/blog/posts/renewed-life-for-sti-with-postgresql-json-type

## Use Royce instead of Pundit
https://github.com/MartinJNash/Royce


# Installed Docco on 29-08-2014
A vital helper for building on-line documentation is Docco - which will provide beautiful online documenation

```
RailsProjects/ $ sudo npm install -g docco
Password:
/usr/local/bin/docco -> /usr/local/lib/node_modules/docco/bin/docco
docco@0.6.3 /usr/local/lib/node_modules/docco
├── commander@2.3.0
├── underscore@1.7.0
├── marked@0.3.2
├── highlight.js@8.2.0
└── fs-extra@0.11.0 (jsonfile@2.0.0, rimraf@2.2.8, ncp@0.6.0, mkdirp@0.5.0)
RailsProjects/ $ docco

  Usage: docco [options] files

```


# Installed a Rails test app (searchapp) to try out Elasticsearch on 28-08-2014
Trying out Elasticsearch is not easy but luckily I found a [great resource](https://github.com/elasticsearch/elasticsearch-rails/blob/master/elasticsearch-rails/README.md) on how to!

But my Rails version was ahead (and the 4.1.1 was broken on how to use the console in the configuration DSL anyway) - so I had to download the [basic template](https://raw.github.com/elasticsearch/elasticsearch-rails/master/elasticsearch-rails/lib/rails/templates/01-basic.rb)
rename it like elastic__template.rb 

```
gsub_file "Gemfile", %r{gem 'rails', '4.1.1'$}, <<-CODE
  gem 'rails', '4.1.4'
CODE
```
and insert the previous 3 lines of code (at about line 100) to have it run properly

```
RailsProjects/ $ rails new searchapp --skip --skip-bundle --template ./elastic_template.rb
      create  
      create  README.rdoc
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/assets/javascripts/application.js
      create  app/assets/stylesheets/application.css
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/views/layouts/application.html.erb
      create  app/assets/images/.keep
      create  app/mailers/.keep
      create  app/models/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/bundle
      create  bin/rails
      create  bin/rake
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/secrets.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/session_store.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/favicon.ico
      create  public/robots.txt
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/test_helper.rb
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor/assets/javascripts
      create  vendor/assets/javascripts/.keep
      create  vendor/assets/stylesheets
      create  vendor/assets/stylesheets/.keep
       apply  /Users/walther/Documents/RailsProjects/elastic_template.rb
         run    touch tmp/.gitignore from "."
      append    .gitignore
         run    git init from "."
Initialized empty Git repository in /Users/walther/Documents/RailsProjects/searchapp/.git/
         run    git add . from "."
         run    git commit -m 'Initial commit: Clean application' from "."
[master (root-commit) 4458246] Initial commit: Clean application
 54 files changed, 755 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 Gemfile
 create mode 100644 README.rdoc
 create mode 100644 Rakefile
 create mode 100644 app/assets/images/.keep
 create mode 100644 app/assets/javascripts/application.js
 create mode 100644 app/assets/stylesheets/application.css
 create mode 100644 app/controllers/application_controller.rb
 create mode 100644 app/controllers/concerns/.keep
 create mode 100644 app/helpers/application_helper.rb
 create mode 100644 app/mailers/.keep
 create mode 100644 app/models/.keep
 create mode 100644 app/models/concerns/.keep
 create mode 100644 app/views/layouts/application.html.erb
 create mode 100755 bin/bundle
 create mode 100755 bin/rails
 create mode 100755 bin/rake
 create mode 100644 config.ru
 create mode 100644 config/application.rb
 create mode 100644 config/boot.rb
 create mode 100644 config/database.yml
 create mode 100644 config/environment.rb
 create mode 100644 config/environments/development.rb
 create mode 100644 config/environments/production.rb
 create mode 100644 config/environments/test.rb
 create mode 100644 config/initializers/assets.rb
 create mode 100644 config/initializers/backtrace_silencers.rb
 create mode 100644 config/initializers/cookies_serializer.rb
 create mode 100644 config/initializers/filter_parameter_logging.rb
 create mode 100644 config/initializers/inflections.rb
 create mode 100644 config/initializers/mime_types.rb
 create mode 100644 config/initializers/session_store.rb
 create mode 100644 config/initializers/wrap_parameters.rb
 create mode 100644 config/locales/en.yml
 create mode 100644 config/routes.rb
 create mode 100644 config/secrets.yml
 create mode 100644 db/seeds.rb
 create mode 100644 lib/assets/.keep
 create mode 100644 lib/tasks/.keep
 create mode 100644 log/.keep
 create mode 100644 public/404.html
 create mode 100644 public/422.html
 create mode 100644 public/500.html
 create mode 100644 public/favicon.ico
 create mode 100644 public/robots.txt
 create mode 100644 test/controllers/.keep
 create mode 100644 test/fixtures/.keep
 create mode 100644 test/helpers/.keep
 create mode 100644 test/integration/.keep
 create mode 100644 test/mailers/.keep
 create mode 100644 test/models/.keep
 create mode 100644 test/test_helper.rb
 create mode 100644 vendor/assets/javascripts/.keep
 create mode 100644 vendor/assets/stylesheets/.keep

      README    Adding Readme...
--------------------------------------------------------------------------------

      remove    README.rdoc
      create    README.rdoc
        gsub    Gemfile
         run    git add . from "."
         run    git commit -m '[01] Added README for the application' from "."
[master 50450e8] [01] Added README for the application
 1 file changed, 14 insertions(+), 28 deletions(-)
 rewrite README.rdoc (98%)

    Rubygems    Adding Thin into Gemfile...
--------------------------------------------------------------------------------

     gemfile    thin
     gemfile    turn
     gemfile    mocha
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile

    Rubygems    Adding Elasticsearch libraries into Gemfile...
--------------------------------------------------------------------------------

     gemfile    git://github.com/elasticsearch/elasticsearch-ruby.git
     gemfile    git://github.com/elasticsearch/elasticsearch-rails.git
     gemfile    git://github.com/elasticsearch/elasticsearch-rails.git
         run    git add Gemfile* from "."
         run    git commit -m 'Added libraries into Gemfile' from "."
[master e136a3d] Added libraries into Gemfile
 1 file changed, 11 insertions(+), 4 deletions(-)

 Application    Disabling asset logging in development...
--------------------------------------------------------------------------------

     gemfile    quiet_assets
         run    git add Gemfile* from "."
         run    git add config/ from "."
         run    git commit -m 'Disabled asset logging in development' from "."
[master 93b8385] Disabled asset logging in development
 2 files changed, 3 insertions(+), 1 deletion(-)

    Rubygems    Installing Rubygems...
--------------------------------------------------------------------------------

         run    bundle install from "."
Fetching git://github.com/elasticsearch/elasticsearch-ruby.git
Updating git://github.com/elasticsearch/elasticsearch-rails.git
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Using rake 10.3.2
Using i18n 0.6.11
Using json 1.8.1
Using minitest 5.4.0
Using thread_safe 0.3.4
Using tzinfo 1.2.2
Using activesupport 4.1.4
Using builder 3.2.2
Using erubis 2.7.0
Using actionview 4.1.4
Using rack 1.5.2
Using rack-test 0.6.2
Using actionpack 4.1.4
Using mime-types 1.25.1
Using polyglot 0.3.5
Using treetop 1.4.15
Using mail 2.5.4
Using actionmailer 4.1.4
Using activemodel 4.1.4
Using arel 5.0.1.20140414130214
Using activerecord 4.1.4
Using ansi 1.4.3
Using bundler 1.7.2
Using coffee-script-source 1.8.0
Using execjs 2.2.1
Using coffee-script 2.3.0
Using thor 0.19.1
Using railties 4.1.4
Using coffee-rails 4.0.1
Using daemons 1.1.9
Using multi_json 1.10.1
Using elasticsearch-api 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using multipart-post 2.0.0
Using faraday 0.9.0
Using elasticsearch-transport 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using elasticsearch 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Installing hashie 3.3.1
Using elasticsearch-model 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using elasticsearch-rails 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using eventmachine 1.0.3
Using hike 1.2.3
Using jbuilder 2.1.3
Using jquery-rails 3.1.1
Installing libv8 3.16.14.3
Installing metaclass 0.0.4
Installing mocha 1.1.0
Using quiet_assets 1.0.3
Using tilt 1.4.1
Installing sprockets 2.12.1
Using sprockets-rails 2.1.3
Using rails 4.1.4
Using rdoc 4.1.1
Using ref 1.0.5
Using sdoc 0.4.1
Using spring 1.1.3
Using sqlite3 1.3.9
Installing therubyracer 0.12.1
Using thin 1.6.2
Using turbolinks 2.3.0
Using turn 0.9.6
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.

       Model    Generating the Article resource...
--------------------------------------------------------------------------------

    generate    scaffold
      invoke  active_record
      create    db/migrate/20140828132315_create_articles.rb
      create    app/models/article.rb
      invoke    test_unit
      create      test/models/article_test.rb
      create      test/fixtures/articles.yml
      invoke  resource_route
       route    resources :articles
      invoke  scaffold_controller
      create    app/controllers/articles_controller.rb
      invoke    erb
      create      app/views/articles
      create      app/views/articles/index.html.erb
      create      app/views/articles/edit.html.erb
      create      app/views/articles/show.html.erb
      create      app/views/articles/new.html.erb
      create      app/views/articles/_form.html.erb
      invoke    test_unit
      create      test/controllers/articles_controller_test.rb
      invoke    helper
      create      app/helpers/articles_helper.rb
      invoke      test_unit
      create        test/helpers/articles_helper_test.rb
      invoke    jbuilder
      create      app/views/articles/index.json.jbuilder
      create      app/views/articles/show.json.jbuilder
      invoke  assets
      invoke    js
      create      app/assets/javascripts/articles.js
      invoke    css
      create      app/assets/stylesheets/articles.css
      invoke  css
      create    app/assets/stylesheets/scaffold.css
       route    root to: 'articles#index'
        rake    db:migrate
== 20140828132315 CreateArticles: migrating ===================================
-- create_table(:articles)
   -> 0.0010s
== 20140828132315 CreateArticles: migrated (0.0010s) ==========================

         run    git add . from "."
         run    git commit -m 'Added the generated Article resource' from "."
[master 53091fa] Added the generated Article resource
 21 files changed, 509 insertions(+)
 create mode 100644 Gemfile.lock
 create mode 100644 app/assets/javascripts/articles.js
 create mode 100644 app/assets/stylesheets/articles.css
 create mode 100644 app/assets/stylesheets/scaffold.css
 create mode 100644 app/controllers/articles_controller.rb
 create mode 100644 app/helpers/articles_helper.rb
 create mode 100644 app/models/article.rb
 create mode 100644 app/views/articles/_form.html.erb
 create mode 100644 app/views/articles/edit.html.erb
 create mode 100644 app/views/articles/index.html.erb
 create mode 100644 app/views/articles/index.json.jbuilder
 create mode 100644 app/views/articles/new.html.erb
 create mode 100644 app/views/articles/show.html.erb
 create mode 100644 app/views/articles/show.json.jbuilder
 create mode 100644 db/migrate/20140828132315_create_articles.rb
 create mode 100644 db/schema.rb
 create mode 100644 test/controllers/articles_controller_test.rb
 create mode 100644 test/fixtures/articles.yml
 create mode 100644 test/helpers/articles_helper_test.rb
 create mode 100644 test/models/article_test.rb

       Model    Adding search support into the Article model...
--------------------------------------------------------------------------------

         run    rm -f app/models/article.rb from "."
      create    app/models/article.rb
         run    git commit -a -m 'Added Elasticsearch support into the Article model' from "."
[master ea4cfec] Added Elasticsearch support into the Article model
 1 file changed, 3 insertions(+)

  Controller    Adding controller action, route, and HTML for searching...
--------------------------------------------------------------------------------

      insert    app/controllers/articles_controller.rb
      insert    app/views/articles/index.html.erb
      insert    app/views/articles/index.html.erb
        gsub    config/routes.rb
        gsub    test/controllers/articles_controller_test.rb
      insert    test/controllers/articles_controller_test.rb
         run    git commit -a -m 'Added search form and controller action' from "."
[master fbca5b3] Added search form and controller action
 4 files changed, 37 insertions(+), 2 deletions(-)

    Database    Seeding the database with data...
--------------------------------------------------------------------------------

      remove    db/seeds.rb
      create    db/seeds.rb
         run    rails runner 'Article.__elasticsearch__.create_index! force: true' from "."
        rake    db:seed
Deleting all articles...
Creating articles...
         run    git add db/seeds.rb from "."
         run    git commit -m 'Added the database seeding script' from "."
[master 3724322] Added the database seeding script
 1 file changed, 29 insertions(+), 7 deletions(-)
 rewrite db/seeds.rb (100%)

         Git    Details about the application:
--------------------------------------------------------------------------------

         run    git tag basic from "."
         run    git log --reverse --oneline from "."
4458246 Initial commit: Clean application
50450e8 [01] Added README for the application
e136a3d Added libraries into Gemfile
93b8385 Disabled asset logging in development
53091fa Added the generated Article resource
ea4cfec Added Elasticsearch support into the Article model
fbca5b3 Added search form and controller action
3724322 Added the database seeding script

       ERROR    Some other application is running on port 3000!
--------------------------------------------------------------------------------
  Please provide free port: 3010

================================================================================
        DONE    Starting the application.
================================================================================

         run    rails server --port=3010 from "."
=> Booting Thin
=> Rails 4.1.4 application starting in development on http://0.0.0.0:3010
=> Run `rails server -h` for more startup options
=> Notice: server is listening on all interfaces (0.0.0.0). Consider using 127.0.0.1 (--binding option)
=> Ctrl-C to shutdown server
Thin web server (v1.6.2 codename Doc Brown)
Maximum connections set to 1024
Listening on 0.0.0.0:3010, CTRL+C to stop


Started GET "/" for 127.0.0.1 at 2014-08-28 15:23:59 +0200
  ActiveRecord::SchemaMigration Load (0.1ms)  SELECT "schema_migrations".* FROM "schema_migrations"
Processing by ArticlesController#index as HTML
  Article Load (0.2ms)  SELECT "articles".* FROM "articles"
  Rendered articles/index.html.erb within layouts/application (8.6ms)
Completed 200 OK in 310ms (Views: 296.9ms | ActiveRecord: 0.4ms)
^C
RailsProjects/ $ Stopping ...
Exiting

RailsProjects/ $ rails new searchapp --skip --skip-bundle --template https://raw.github.com/elasticsearch/elasticsearch-rails/master/elasticsearch-rails/lib/rails/templates/02-pretty.rb
       exist  
        skip  README.rdoc
   identical  Rakefile
   identical  config.ru
        skip  .gitignore
        skip  Gemfile
       exist  app
   identical  app/assets/javascripts/application.js
   identical  app/assets/stylesheets/application.css
   identical  app/controllers/application_controller.rb
   identical  app/helpers/application_helper.rb
   identical  app/views/layouts/application.html.erb
   identical  app/assets/images/.keep
   identical  app/mailers/.keep
   identical  app/models/.keep
   identical  app/controllers/concerns/.keep
   identical  app/models/concerns/.keep
       exist  bin
   identical  bin/bundle
   identical  bin/rails
   identical  bin/rake
       exist  config
        skip  config/routes.rb
   identical  config/application.rb
   identical  config/environment.rb
        skip  config/secrets.yml
       exist  config/environments
        skip  config/environments/development.rb
   identical  config/environments/production.rb
   identical  config/environments/test.rb
       exist  config/initializers
   identical  config/initializers/assets.rb
   identical  config/initializers/backtrace_silencers.rb
   identical  config/initializers/cookies_serializer.rb
   identical  config/initializers/filter_parameter_logging.rb
   identical  config/initializers/inflections.rb
   identical  config/initializers/mime_types.rb
   identical  config/initializers/session_store.rb
   identical  config/initializers/wrap_parameters.rb
       exist  config/locales
   identical  config/locales/en.yml
   identical  config/boot.rb
   identical  config/database.yml
       exist  db
        skip  db/seeds.rb
       exist  lib
       exist  lib/tasks
   identical  lib/tasks/.keep
       exist  lib/assets
   identical  lib/assets/.keep
       exist  log
   identical  log/.keep
       exist  public
   identical  public/404.html
   identical  public/422.html
   identical  public/500.html
   identical  public/favicon.ico
   identical  public/robots.txt
       exist  test/fixtures
   identical  test/fixtures/.keep
       exist  test/controllers
   identical  test/controllers/.keep
       exist  test/mailers
   identical  test/mailers/.keep
       exist  test/models
   identical  test/models/.keep
       exist  test/helpers
   identical  test/helpers/.keep
       exist  test/integration
   identical  test/integration/.keep
   identical  test/test_helper.rb
       exist  tmp/cache
       exist  tmp/cache/assets
       exist  vendor/assets/javascripts
   identical  vendor/assets/javascripts/.keep
       exist  vendor/assets/stylesheets
   identical  vendor/assets/stylesheets/.keep
       apply  https://raw.github.com/elasticsearch/elasticsearch-rails/master/elasticsearch-rails/lib/rails/templates/02-pretty.rb

      README    Updating Readme...
--------------------------------------------------------------------------------

      append    README.rdoc
         run    git add README.rdoc from "."
         run    git commit -m '[02] Updated the application README' from "."
[master 5d7b262] [02] Updated the application README
 1 file changed, 10 insertions(+)

    Rubygems    Adding Rails logger integration...
--------------------------------------------------------------------------------

      insert    config/application.rb
         run    git add config/application.rb from "."
         run    git commit -m 'Added the Rails logger integration to application.rb' from "."
On branch master
nothing to commit, working directory clean

    Rubygems    Adding Rubygems into Gemfile...
--------------------------------------------------------------------------------

      insert    Gemfile
         run    bundle install from "."
Resolving dependencies...
Using rake 10.3.2
Using i18n 0.6.11
Using json 1.8.1
Using minitest 5.4.0
Using thread_safe 0.3.4
Using tzinfo 1.2.2
Using activesupport 4.1.4
Using builder 3.2.2
Using erubis 2.7.0
Using actionview 4.1.4
Using rack 1.5.2
Using rack-test 0.6.2
Using actionpack 4.1.4
Using mime-types 1.25.1
Using polyglot 0.3.5
Using treetop 1.4.15
Using mail 2.5.4
Using actionmailer 4.1.4
Using activemodel 4.1.4
Using arel 5.0.1.20140414130214
Using activerecord 4.1.4
Using ansi 1.4.3
Using bundler 1.7.2
Using coffee-script-source 1.8.0
Using execjs 2.2.1
Using coffee-script 2.3.0
Using thor 0.19.1
Using railties 4.1.4
Using coffee-rails 4.0.1
Using daemons 1.1.9
Using multi_json 1.10.1
Using elasticsearch-api 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using multipart-post 2.0.0
Using faraday 0.9.0
Using elasticsearch-transport 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using elasticsearch 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using hashie 3.3.1
Using elasticsearch-model 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using elasticsearch-rails 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using eventmachine 1.0.3
Using hike 1.2.3
Using jbuilder 2.1.3
Using jquery-rails 3.1.1
Using kaminari 0.16.1
Using libv8 3.16.14.3
Using metaclass 0.0.4
Using mocha 1.1.0
Using quiet_assets 1.0.3
Using tilt 1.4.1
Using sprockets 2.12.1
Using sprockets-rails 2.1.3
Using rails 4.1.4
Using rdoc 4.1.1
Using ref 1.0.5
Using sdoc 0.4.1
Using spring 1.1.3
Using sqlite3 1.3.9
Using therubyracer 0.12.1
Using thin 1.6.2
Using turbolinks 2.3.0
Using turn 0.9.6
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
         run    git add Gemfile* from "."
         run    git commit -m 'Added the Kaminari gem' from "."
[master 9c1e216] Added the Kaminari gem
 2 files changed, 8 insertions(+)

       Model    Adding a `Article.search` class method...
--------------------------------------------------------------------------------

      insert    app/models/article.rb
        gsub    test/models/article_test.rb
         run    git add app/models/article.rb from "."
         run    git add test/**/article_test.rb from "."
         run    git commit -m 'Added an `Article.search` method' from "."
[master 664282f] Added an `Article.search` method
 2 files changed, 31 insertions(+), 3 deletions(-)

   Bootstrap    Adding Bootstrap asset links into the 'application' layout...
--------------------------------------------------------------------------------

        gsub    app/views/layouts/application.html.erb
      insert    app/views/layouts/application.html.erb
         run    git commit -a -m 'Added loading Bootstrap assets in the application layout' from "."
[master a242601] Added loading Bootstrap assets in the application layout
 1 file changed, 5 insertions(+)

   Bootstrap    Customizing the index page...
--------------------------------------------------------------------------------

        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
         run    git add app/views from "."
         run    git commit -m 'Refactored the articles listing to use Bootstrap components' from "."
[master c5e76b5] Refactored the articles listing to use Bootstrap components
 1 file changed, 21 insertions(+), 10 deletions(-)
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
        gsub    app/views/articles/index.html.erb
         run    git commit -a -m 'Added highlighting for matches' from "."
[master 43d855b] Added highlighting for matches
 1 file changed, 3 insertions(+), 3 deletions(-)
        gsub    app/controllers/articles_controller.rb
        gsub    app/controllers/articles_controller.rb
      insert    app/views/articles/index.html.erb
    generate    kaminari:views
      downloading app/views/kaminari/_first_page.html.erb from kaminari_themes...
      create  app/views/kaminari/_first_page.html.erb
      downloading app/views/kaminari/_gap.html.erb from kaminari_themes...
      create  app/views/kaminari/_gap.html.erb
      downloading app/views/kaminari/_last_page.html.erb from kaminari_themes...
      create  app/views/kaminari/_last_page.html.erb
      downloading app/views/kaminari/_next_page.html.erb from kaminari_themes...
      create  app/views/kaminari/_next_page.html.erb
      downloading app/views/kaminari/_page.html.erb from kaminari_themes...
      create  app/views/kaminari/_page.html.erb
      downloading app/views/kaminari/_paginator.html.erb from kaminari_themes...
      create  app/views/kaminari/_paginator.html.erb
      downloading app/views/kaminari/_prev_page.html.erb from kaminari_themes...
      create  app/views/kaminari/_prev_page.html.erb
        gsub    app/views/kaminari/_paginator.html.erb
         run    git add . from "."
         run    git commit -m 'Added pagination to articles listing' from "."
[master d12215b] Added pagination to articles listing
 9 files changed, 42 insertions(+), 2 deletions(-)
 create mode 100644 app/views/kaminari/_first_page.html.erb
 create mode 100644 app/views/kaminari/_gap.html.erb
 create mode 100644 app/views/kaminari/_last_page.html.erb
 create mode 100644 app/views/kaminari/_next_page.html.erb
 create mode 100644 app/views/kaminari/_page.html.erb
 create mode 100644 app/views/kaminari/_paginator.html.erb
 create mode 100644 app/views/kaminari/_prev_page.html.erb

         CSS    Adding custom styles...
--------------------------------------------------------------------------------

      append    app/assets/stylesheets/application.css
         run    git commit -a -m 'Added custom style definitions into application.css' from "."
[master b6e8add] Added custom style definitions into application.css
 1 file changed, 18 insertions(+)

    Database    Creating 1,000 articles...
--------------------------------------------------------------------------------

         run    rails runner 'Article.__elasticsearch__.create_index! force: true' from "."
        rake    db:seed COUNT=1_000
Deleting all articles...
Generating articles.............

         Git    Details about the application:
--------------------------------------------------------------------------------

         run    git tag pretty from "."
         run    git log --reverse --oneline pretty...basic from "."
5d7b262 [02] Updated the application README
9c1e216 Added the Kaminari gem
664282f Added an `Article.search` method
a242601 Added loading Bootstrap assets in the application layout
c5e76b5 Refactored the articles listing to use Bootstrap components
43d855b Added highlighting for matches
d12215b Added pagination to articles listing
b6e8add Added custom style definitions into application.css

================================================================================
        DONE    Starting the application. Open http://localhost:3000
================================================================================

         run    rails server --port=3000 from "."
=> Booting Thin
=> Rails 4.1.4 application starting in development on http://0.0.0.0:3000
=> Run `rails server -h` for more startup options
=> Notice: server is listening on all interfaces (0.0.0.0). Consider using 127.0.0.1 (--binding option)
=> Ctrl-C to shutdown server
Thin web server (v1.6.2 codename Doc Brown)
Maximum connections set to 1024
Listening on 0.0.0.0:3000, CTRL+C to stop

Started GET "/articles/search?utf8=%E2%9C%93&q=994" for 127.0.0.1 at 2014-08-28 15:27:36 +0200
Processing by ArticlesController#search as HTML
  Parameters: {"utf8"=>"✓", "q"=>"994"}
  Article Load (0.2ms)  SELECT "articles".* FROM "articles"  WHERE "articles"."id" IN (999)
  Rendered articles/index.html.erb within layouts/application (23.3ms)
Completed 200 OK in 28ms (Views: 26.7ms | ActiveRecord: 0.2ms)
^C
RailsProjects/ $ Stopping ...
Exiting

RailsProjects/ $ rails new searchapp --skip --skip-bundle --template https://raw.github.com/elasticsearch/elasticsearch-rails/master/elasticsearch-rails/lib/rails/templates/03-expert.rb
       exist  
        skip  README.rdoc
   identical  Rakefile
   identical  config.ru
        skip  .gitignore
        skip  Gemfile
       exist  app
   identical  app/assets/javascripts/application.js
        skip  app/assets/stylesheets/application.css
   identical  app/controllers/application_controller.rb
   identical  app/helpers/application_helper.rb
        skip  app/views/layouts/application.html.erb
   identical  app/assets/images/.keep
   identical  app/mailers/.keep
   identical  app/models/.keep
   identical  app/controllers/concerns/.keep
   identical  app/models/concerns/.keep
       exist  bin
   identical  bin/bundle
   identical  bin/rails
   identical  bin/rake
       exist  config
        skip  config/routes.rb
   identical  config/application.rb
   identical  config/environment.rb
        skip  config/secrets.yml
       exist  config/environments
        skip  config/environments/development.rb
   identical  config/environments/production.rb
   identical  config/environments/test.rb
       exist  config/initializers
   identical  config/initializers/assets.rb
   identical  config/initializers/backtrace_silencers.rb
   identical  config/initializers/cookies_serializer.rb
   identical  config/initializers/filter_parameter_logging.rb
   identical  config/initializers/inflections.rb
   identical  config/initializers/mime_types.rb
   identical  config/initializers/session_store.rb
   identical  config/initializers/wrap_parameters.rb
       exist  config/locales
   identical  config/locales/en.yml
   identical  config/boot.rb
   identical  config/database.yml
       exist  db
        skip  db/seeds.rb
       exist  lib
       exist  lib/tasks
   identical  lib/tasks/.keep
       exist  lib/assets
   identical  lib/assets/.keep
       exist  log
   identical  log/.keep
       exist  public
   identical  public/404.html
   identical  public/422.html
   identical  public/500.html
   identical  public/favicon.ico
   identical  public/robots.txt
       exist  test/fixtures
   identical  test/fixtures/.keep
       exist  test/controllers
   identical  test/controllers/.keep
       exist  test/mailers
   identical  test/mailers/.keep
       exist  test/models
   identical  test/models/.keep
       exist  test/helpers
   identical  test/helpers/.keep
       exist  test/integration
   identical  test/integration/.keep
   identical  test/test_helper.rb
       exist  tmp/cache
       exist  tmp/cache/assets
       exist  vendor/assets/javascripts
   identical  vendor/assets/javascripts/.keep
       exist  vendor/assets/stylesheets
   identical  vendor/assets/stylesheets/.keep
       apply  https://raw.github.com/elasticsearch/elasticsearch-rails/master/elasticsearch-rails/lib/rails/templates/03-expert.rb
      append    README.rdoc
         run    git add README.rdoc from "."
         run    git commit -m '[03] Updated the application README' from "."
[master 3201430] [03] Updated the application README
 1 file changed, 15 insertions(+)

    Rubygems    Adding Rubygems into Gemfile...
--------------------------------------------------------------------------------

     gemfile    oj
         run    git add Gemfile* from "."
         run    git commit -m 'Added Ruby gems' from "."
[master 3afcf91] Added Ruby gems
 1 file changed, 2 insertions(+), 1 deletion(-)

       Rails    Customizing `rails console`...
--------------------------------------------------------------------------------

     gemfile    pry
         run    git add Gemfile* from "."
         run    git add config/ from "."
         run    git commit -m 'Added Pry as the console for development' from "."
[master 5e74706] Added Pry as the console for development
 2 files changed, 10 insertions(+), 1 deletion(-)

 Application    Disabling asset logging in development...
--------------------------------------------------------------------------------

     gemfile    quiet_assets
         run    git add Gemfile* from "."
         run    git add config/ from "."
         run    git commit -m 'Disabled asset logging in development' from "."
On branch master
nothing to commit, working directory clean
         run    bundle install from "."
Resolving dependencies...
Using rake 10.3.2
Using i18n 0.6.11
Using json 1.8.1
Using minitest 5.4.0
Using thread_safe 0.3.4
Using tzinfo 1.2.2
Using activesupport 4.1.4
Using builder 3.2.2
Using erubis 2.7.0
Using actionview 4.1.4
Using rack 1.5.2
Using rack-test 0.6.2
Using actionpack 4.1.4
Using mime-types 1.25.1
Using polyglot 0.3.5
Using treetop 1.4.15
Using mail 2.5.4
Using actionmailer 4.1.4
Using activemodel 4.1.4
Using arel 5.0.1.20140414130214
Using activerecord 4.1.4
Using ansi 1.4.3
Using bundler 1.7.2
Using coderay 1.1.0
Using coffee-script-source 1.8.0
Using execjs 2.2.1
Using coffee-script 2.3.0
Using thor 0.19.1
Using railties 4.1.4
Using coffee-rails 4.0.1
Using daemons 1.1.9
Using multi_json 1.10.1
Using elasticsearch-api 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using multipart-post 2.0.0
Using faraday 0.9.0
Using elasticsearch-transport 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using elasticsearch 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using hashie 3.3.1
Using elasticsearch-model 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using elasticsearch-rails 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using eventmachine 1.0.3
Using hike 1.2.3
Using jbuilder 2.1.3
Using jquery-rails 3.1.1
Using kaminari 0.16.1
Using libv8 3.16.14.3
Using metaclass 0.0.4
Using method_source 0.8.2
Using mocha 1.1.0
Using oj 2.10.2
Using slop 3.6.0
Using pry 0.10.1
Using quiet_assets 1.0.3
Using tilt 1.4.1
Using sprockets 2.12.1
Using sprockets-rails 2.1.3
Using rails 4.1.4
Using rdoc 4.1.1
Using ref 1.0.5
Using sdoc 0.4.1
Using spring 1.1.3
Using sqlite3 1.3.9
Using therubyracer 0.12.1
Using thin 1.6.2
Using turbolinks 2.3.0
Using turn 0.9.6
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.

      Models    Adding complex schema...
--------------------------------------------------------------------------------

    generate    scaffold
      invoke  active_record
      create    db/migrate/20140828132821_create_categories.rb
      create    app/models/category.rb
      invoke    test_unit
      create      test/models/category_test.rb
      create      test/fixtures/categories.yml
      invoke  resource_route
       route    resources :categories
      invoke  scaffold_controller
      create    app/controllers/categories_controller.rb
      invoke    erb
      create      app/views/categories
      create      app/views/categories/index.html.erb
      create      app/views/categories/edit.html.erb
      create      app/views/categories/show.html.erb
      create      app/views/categories/new.html.erb
      create      app/views/categories/_form.html.erb
      invoke    test_unit
      create      test/controllers/categories_controller_test.rb
      invoke    helper
      create      app/helpers/categories_helper.rb
      invoke      test_unit
      create        test/helpers/categories_helper_test.rb
      invoke    jbuilder
      create      app/views/categories/index.json.jbuilder
      create      app/views/categories/show.json.jbuilder
      invoke  assets
      invoke    js
      create      app/assets/javascripts/categories.js
      invoke    css
      create      app/assets/stylesheets/categories.css
      invoke  css
   identical    app/assets/stylesheets/scaffold.css
    generate    scaffold
      invoke  active_record
      create    db/migrate/20140828132823_create_authors.rb
      create    app/models/author.rb
      invoke    test_unit
      create      test/models/author_test.rb
      create      test/fixtures/authors.yml
      invoke  resource_route
       route    resources :authors
      invoke  scaffold_controller
      create    app/controllers/authors_controller.rb
      invoke    erb
      create      app/views/authors
      create      app/views/authors/index.html.erb
      create      app/views/authors/edit.html.erb
      create      app/views/authors/show.html.erb
      create      app/views/authors/new.html.erb
      create      app/views/authors/_form.html.erb
      invoke    test_unit
      create      test/controllers/authors_controller_test.rb
      invoke    helper
      create      app/helpers/authors_helper.rb
      invoke      test_unit
      create        test/helpers/authors_helper_test.rb
      invoke    jbuilder
      create      app/views/authors/index.json.jbuilder
      create      app/views/authors/show.json.jbuilder
      invoke  assets
      invoke    js
      create      app/assets/javascripts/authors.js
      invoke    css
      create      app/assets/stylesheets/authors.css
      invoke  css
   identical    app/assets/stylesheets/scaffold.css
    generate    scaffold
      invoke  active_record
      create    db/migrate/20140828132825_create_authorships.rb
      create    app/models/authorship.rb
      invoke    test_unit
      create      test/models/authorship_test.rb
      create      test/fixtures/authorships.yml
      invoke  resource_route
       route    resources :authorships
      invoke  scaffold_controller
      create    app/controllers/authorships_controller.rb
      invoke    erb
      create      app/views/authorships
      create      app/views/authorships/index.html.erb
      create      app/views/authorships/edit.html.erb
      create      app/views/authorships/show.html.erb
      create      app/views/authorships/new.html.erb
      create      app/views/authorships/_form.html.erb
      invoke    test_unit
      create      test/controllers/authorships_controller_test.rb
      invoke    helper
      create      app/helpers/authorships_helper.rb
      invoke      test_unit
      create        test/helpers/authorships_helper_test.rb
      invoke    jbuilder
      create      app/views/authorships/index.json.jbuilder
      create      app/views/authorships/show.json.jbuilder
      invoke  assets
      invoke    js
      create      app/assets/javascripts/authorships.js
      invoke    css
      create      app/assets/stylesheets/authorships.css
      invoke  css
   identical    app/assets/stylesheets/scaffold.css
    generate    model
      invoke  active_record
      create    db/migrate/20140828132827_create_comments.rb
      create    app/models/comment.rb
      invoke    test_unit
      create      test/models/comment_test.rb
      create      test/fixtures/comments.yml
    generate    migration
      invoke  active_record
      create    db/migrate/20140828132829_create_articles_categories.rb
        rake    db:drop
        rake    db:migrate
== 20140828132315 CreateArticles: migrating ===================================
-- create_table(:articles)
   -> 0.0009s
== 20140828132315 CreateArticles: migrated (0.0010s) ==========================

== 20140828132821 CreateCategories: migrating =================================
-- create_table(:categories)
   -> 0.0005s
== 20140828132821 CreateCategories: migrated (0.0006s) ========================

== 20140828132823 CreateAuthors: migrating ====================================
-- create_table(:authors)
   -> 0.0005s
== 20140828132823 CreateAuthors: migrated (0.0005s) ===========================

== 20140828132825 CreateAuthorships: migrating ================================
-- create_table(:authorships)
   -> 0.0012s
== 20140828132825 CreateAuthorships: migrated (0.0012s) =======================

== 20140828132827 CreateComments: migrating ===================================
-- create_table(:comments)
   -> 0.0008s
== 20140828132827 CreateComments: migrated (0.0008s) ==========================

== 20140828132829 CreateArticlesCategories: migrating =========================
-- create_table(:articles_categories)
   -> 0.0011s
== 20140828132829 CreateArticlesCategories: migrated (0.0011s) ================

      insert    app/models/category.rb
      insert    app/models/author.rb
        gsub    app/models/authorship.rb
      insert    app/models/article.rb
        gsub    app/models/comment.rb
         run    git add . from "."
         run    git commit -m 'Generated Category, Author and Comment resources' from "."
[master 81ef0b0] Generated Category, Author and Comment resources
 60 files changed, 847 insertions(+), 1 deletion(-)
 create mode 100644 app/assets/javascripts/authors.js
 create mode 100644 app/assets/javascripts/authorships.js
 create mode 100644 app/assets/javascripts/categories.js
 create mode 100644 app/assets/stylesheets/authors.css
 create mode 100644 app/assets/stylesheets/authorships.css
 create mode 100644 app/assets/stylesheets/categories.css
 create mode 100644 app/controllers/authors_controller.rb
 create mode 100644 app/controllers/authorships_controller.rb
 create mode 100644 app/controllers/categories_controller.rb
 create mode 100644 app/helpers/authors_helper.rb
 create mode 100644 app/helpers/authorships_helper.rb
 create mode 100644 app/helpers/categories_helper.rb
 create mode 100644 app/models/author.rb
 create mode 100644 app/models/authorship.rb
 create mode 100644 app/models/category.rb
 create mode 100644 app/models/comment.rb
 create mode 100644 app/views/authors/_form.html.erb
 create mode 100644 app/views/authors/edit.html.erb
 create mode 100644 app/views/authors/index.html.erb
 create mode 100644 app/views/authors/index.json.jbuilder
 create mode 100644 app/views/authors/new.html.erb
 create mode 100644 app/views/authors/show.html.erb
 create mode 100644 app/views/authors/show.json.jbuilder
 create mode 100644 app/views/authorships/_form.html.erb
 create mode 100644 app/views/authorships/edit.html.erb
 create mode 100644 app/views/authorships/index.html.erb
 create mode 100644 app/views/authorships/index.json.jbuilder
 create mode 100644 app/views/authorships/new.html.erb
 create mode 100644 app/views/authorships/show.html.erb
 create mode 100644 app/views/authorships/show.json.jbuilder
 create mode 100644 app/views/categories/_form.html.erb
 create mode 100644 app/views/categories/edit.html.erb
 create mode 100644 app/views/categories/index.html.erb
 create mode 100644 app/views/categories/index.json.jbuilder
 create mode 100644 app/views/categories/new.html.erb
 create mode 100644 app/views/categories/show.html.erb
 create mode 100644 app/views/categories/show.json.jbuilder
 create mode 100644 db/migrate/20140828132821_create_categories.rb
 create mode 100644 db/migrate/20140828132823_create_authors.rb
 create mode 100644 db/migrate/20140828132825_create_authorships.rb
 create mode 100644 db/migrate/20140828132827_create_comments.rb
 create mode 100644 db/migrate/20140828132829_create_articles_categories.rb
 create mode 100644 test/controllers/authors_controller_test.rb
 create mode 100644 test/controllers/authorships_controller_test.rb
 create mode 100644 test/controllers/categories_controller_test.rb
 create mode 100644 test/fixtures/authors.yml
 create mode 100644 test/fixtures/authorships.yml
 create mode 100644 test/fixtures/categories.yml
 create mode 100644 test/fixtures/comments.yml
 create mode 100644 test/helpers/authors_helper_test.rb
 create mode 100644 test/helpers/authorships_helper_test.rb
 create mode 100644 test/helpers/categories_helper_test.rb
 create mode 100644 test/models/author_test.rb
 create mode 100644 test/models/authorship_test.rb
 create mode 100644 test/models/category_test.rb
 create mode 100644 test/models/comment_test.rb

       Model    Adding the `abstract` column to Article...
--------------------------------------------------------------------------------

    generate    migration
      invoke  active_record
      create    db/migrate/20140828132834_add_columns_to_article.rb
        rake    db:migrate
== 20140828132834 AddColumnsToArticle: migrating ==============================
-- add_column(:articles, :abstract, :text)
   -> 0.0028s
-- add_column(:articles, :url, :string)
   -> 0.0003s
-- add_column(:articles, :shares, :integer)
   -> 0.0002s
== 20140828132834 AddColumnsToArticle: migrated (0.0035s) =====================

         run    git add db/ from "."
         run    git commit -m 'Added additional columns to Article' from "."
[master 9d7dc5a] Added additional columns to Article
 2 files changed, 11 insertions(+), 1 deletion(-)
 create mode 100644 db/migrate/20140828132834_add_columns_to_article.rb

       Model    Refactoring the model integration...
--------------------------------------------------------------------------------

      remove    app/models/article.rb
      create    app/models/article.rb
      create    app/models/concerns/searchable.rb
      insert    app/models/article.rb
         run    git add app/models/ from "."
         run    git commit -m 'Refactored the Elasticsearch integration into a concern

See:

* http://37signals.com/svn/posts/3372-put-chubby-models-on-a-diet-with-concerns
* http://joshsymonds.com/blog/2012/10/25/rails-concerns-v-searchable-with-elasticsearch/' from "."
[master 1a9c260] Refactored the Elasticsearch integration into a concern
 2 files changed, 213 insertions(+), 24 deletions(-)
 create mode 100644 app/models/concerns/searchable.rb

 Application    Adding Sidekiq worker for updating the index...
--------------------------------------------------------------------------------

     gemfile    sidekiq
         run    bundle install from "."
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Using rake 10.3.2
Using i18n 0.6.11
Using json 1.8.1
Using minitest 5.4.0
Using thread_safe 0.3.4
Using tzinfo 1.2.2
Using activesupport 4.1.4
Using builder 3.2.2
Using erubis 2.7.0
Using actionview 4.1.4
Using rack 1.5.2
Using rack-test 0.6.2
Using actionpack 4.1.4
Using mime-types 1.25.1
Using polyglot 0.3.5
Using treetop 1.4.15
Using mail 2.5.4
Using actionmailer 4.1.4
Using activemodel 4.1.4
Using arel 5.0.1.20140414130214
Using activerecord 4.1.4
Using ansi 1.4.3
Using bundler 1.7.2
Using timers 1.1.0
Using celluloid 0.15.2
Using coderay 1.1.0
Using coffee-script-source 1.8.0
Using execjs 2.2.1
Using coffee-script 2.3.0
Using thor 0.19.1
Using railties 4.1.4
Using coffee-rails 4.0.1
Installing connection_pool 2.0.0
Using daemons 1.1.9
Using multi_json 1.10.1
Using elasticsearch-api 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using multipart-post 2.0.0
Using faraday 0.9.0
Using elasticsearch-transport 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using elasticsearch 1.0.4 from git://github.com/elasticsearch/elasticsearch-ruby.git (at master)
Using hashie 3.3.1
Using elasticsearch-model 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using elasticsearch-rails 0.1.4 from git://github.com/elasticsearch/elasticsearch-rails.git (at master)
Using eventmachine 1.0.3
Using hike 1.2.3
Using jbuilder 2.1.3
Using jquery-rails 3.1.1
Using kaminari 0.16.1
Using libv8 3.16.14.3
Using metaclass 0.0.4
Using method_source 0.8.2
Using mocha 1.1.0
Using oj 2.10.2
Using slop 3.6.0
Using pry 0.10.1
Using quiet_assets 1.0.3
Using tilt 1.4.1
Using sprockets 2.12.1
Using sprockets-rails 2.1.3
Using rails 4.1.4
Using rdoc 4.1.1
Installing redis 3.1.0
Installing redis-namespace 1.5.1
Using ref 1.0.5
Using sdoc 0.4.1
Installing sidekiq 3.2.2
Using spring 1.1.3
Using sqlite3 1.3.9
Using therubyracer 0.12.1
Using thin 1.6.2
Using turbolinks 2.3.0
Using turn 0.9.6
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
      create    app/workers/indexer.rb
         run    git add Gemfile* app/workers/ from "."
         run    git commit -m 'Added a Sidekiq indexer

Run:

    $ bundle exec sidekiq --queue elasticsearch --verbose

See http://sidekiq.org' from "."
[master d775820] Added a Sidekiq indexer
 3 files changed, 43 insertions(+), 1 deletion(-)
 create mode 100644 app/workers/indexer.rb

 Controllers    Adding SearchController...
--------------------------------------------------------------------------------

      create    app/controllers/search_controller.rb
       route    get '/search', to: 'search#index', as: 'search'
        gsub    config/routes.rb
      create    app/views/search/index.html.erb
      create    app/assets/stylesheets/search.css
         run    git add app/controllers/ config/routes.rb from "."
         run    git add app/views/search/ app/assets/stylesheets/search.css from "."
         run    git commit -m 'Added SearchController#index' from "."
[master 0245d5e] Added SearchController#index
 4 files changed, 250 insertions(+), 1 deletion(-)
 create mode 100644 app/assets/stylesheets/search.css
 create mode 100644 app/controllers/search_controller.rb
 create mode 100644 app/views/search/index.html.erb

 Application    Adding Elasticsearch configuration in an initializer...
--------------------------------------------------------------------------------

      create    config/initializers/elasticsearch.rb
         run    git add config/initializers from "."
         run    git commit -m 'Added Rails initializer with Elasticsearch configuration' from "."
[master c108663] Added Rails initializer with Elasticsearch configuration
 1 file changed, 13 insertions(+)
 create mode 100644 config/initializers/elasticsearch.rb

 Application    Adding Elasticsearch Rake tasks...
--------------------------------------------------------------------------------

      create    lib/tasks/elasticsearch.rake
         run    git add lib/tasks from "."
         run    git commit -m 'Added Rake tasks for Elasticsearch' from "."
[master fe2d4a0] Added Rake tasks for Elasticsearch
 1 file changed, 1 insertion(+)
 create mode 100644 lib/tasks/elasticsearch.rake

    Database    Re-creating the database with data and importing into Elasticsearch...
--------------------------------------------------------------------------------

      create    db/articles.yml.gz
      remove    db/seeds.rb
      create    db/seeds.rb
        rake    db:reset
-- create_table("articles", {:force=>true})
   -> 0.0063s
-- create_table("articles_categories", {:force=>true})
   -> 0.0010s
-- add_index("articles_categories", ["article_id"], {:name=>"index_articles_categories_on_article_id"})
   -> 0.0129s
-- add_index("articles_categories", ["category_id"], {:name=>"index_articles_categories_on_category_id"})
   -> 0.0011s
-- create_table("authors", {:force=>true})
   -> 0.0010s
-- create_table("authorships", {:force=>true})
   -> 0.0008s
-- add_index("authorships", ["article_id"], {:name=>"index_authorships_on_article_id"})
   -> 0.0007s
-- add_index("authorships", ["author_id"], {:name=>"index_authorships_on_author_id"})
   -> 0.0010s
-- create_table("categories", {:force=>true})
   -> 0.0011s
-- create_table("comments", {:force=>true})
   -> 0.0013s
-- add_index("comments", ["article_id"], {:name=>"index_comments_on_article_id"})
   -> 0.0008s
-- initialize_schema_migrations_table()
   -> 0.0051s
Reading articles from gzipped YAML...
 (0.1ms)  begin transaction
SQL (0.3ms)  INSERT INTO "articles" ("abstract", "content", "created_at", "published_on", "shares", "title", "updated_at", "url") VALUES (?, ?, ?, ?, ?, ?, ?, ?)  [["abstract", "What does the way you speak say about where you’re from? Answer the questions to see your personal dialect map."], ["content", ""]..."], ["created_at", "2014-08-28 13:29:02.419902"], ["published_on", "2013-12-20"], ["shares", 1], ["title", "How Y’all, Youse and You Guys Talk"], ["updated_at", "2014-08-28 13:29:02.419902"], ["url", "http://www.nytimes.com/interactive/2013/12/20/sunday-review/dialect-quiz-map.html"]]
 (1.9ms)  commit transaction
 (0.1ms)  rollback transaction
rake aborted!
ActiveRecord::StatementInvalid: SQLite3::SQLException: cannot rollback - no transaction is active: rollback transaction
/Users/walther/Documents/RailsProjects/searchapp/db/seeds.rb:38:in `block in <top (required)>'
/Users/walther/Documents/RailsProjects/searchapp/db/seeds.rb:37:in `each'
/Users/walther/Documents/RailsProjects/searchapp/db/seeds.rb:37:in `<top (required)>'
Tasks: TOP => db:setup => db:seed
(See full trace by running task with --trace)
        rake    environment elasticsearch:import:model CLASS='Article' BATCH=100 FORCE=y
Article:       100% |||||||||||||||||||||||||||||||||||||||||||| Time: 00:00:00
[IMPORT] Done
         run    git add db/seeds.rb db/articles.yml.gz from "."
         run    git commit -m 'Added a seed script and source data' from "."
[master 3e8232f] Added a seed script and source data
 2 files changed, 56 insertions(+), 29 deletions(-)
 create mode 100644 db/articles.yml.gz
 rewrite db/seeds.rb (97%)

         Git    Details about the application:
--------------------------------------------------------------------------------

         run    git tag expert from "."
         run    git log --reverse --oneline HEAD...pretty from "."
3201430 [03] Updated the application README
3afcf91 Added Ruby gems
5e74706 Added Pry as the console for development
81ef0b0 Generated Category, Author and Comment resources
9d7dc5a Added additional columns to Article
1a9c260 Refactored the Elasticsearch integration into a concern
d775820 Added a Sidekiq indexer
0245d5e Added SearchController#index
c108663 Added Rails initializer with Elasticsearch configuration
fe2d4a0 Added Rake tasks for Elasticsearch
3e8232f Added a seed script and source data

================================================================================
        DONE    Starting the application. Open http://localhost:3000
================================================================================

         run    rails server --port=3000 from "."
=> Booting Thin
=> Rails 4.1.4 application starting in development on http://0.0.0.0:3000
=> Run `rails server -h` for more startup options
=> Notice: server is listening on all interfaces (0.0.0.0). Consider using 127.0.0.1 (--binding option)
=> Ctrl-C to shutdown server
Thin web server (v1.6.2 codename Doc Brown)
Maximum connections set to 1024
Listening on 0.0.0.0:3000, CTRL+C to stop

```



# Installed Redis on 28-08-2014
Redis Server is another part of the equation (used by Elasticsearch I believe) - so I had to install that too, using this resource:

```
searchapp/ (master) $ redis
-bash: redis: command not found
searchapp/ (master) $ redis-server
-bash: redis-server: command not found
searchapp/ (master) $ brew install redis
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/redis-2.8.13.mavericks.bottle.tar.gz
######################################################################## 100,0%
==> Pouring redis-2.8.13.mavericks.bottle.tar.gz
==> Caveats
To load redis:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.redis.plist
Or, if you don't want/need launchctl, you can just run:
    redis-server /usr/local/etc/redis.conf
==> Summary
🍺  /usr/local/Cellar/redis/2.8.13: 10 files, 1,3M
searchapp/ (master) $ redis-server /usr/local/etc/redis.conf
^C
searchapp/ (master) $ redis-server
[83007] 28 Aug 16:17:31.266 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
[83007] 28 Aug 16:17:31.267 * Increased maximum number of open files to 10032 (it was originally set to 256).
```

# Installed Elasticsearch on 28-08-2014
Elasticsearch will have a center-court place in leaner so I could as well install it right away.

The "inspiration"  was provided by http://red-badger.com/blog/2013/11/08/getting-started-with-elasticsearch/ and of cause I had to upgrade my Java to 7

```
froeslev/ (master *) $ brew install elasticsearch && brew info elasticsearch
==> Downloading https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.3.2.tar.gz
######################################################################## 100,0%
==> Caveats
Data:    /usr/local/var/elasticsearch/elasticsearch_walther/
Logs:    /usr/local/var/log/elasticsearch/elasticsearch_walther.log
Plugins: /usr/local/var/lib/elasticsearch/plugins/

ElasticSearch requires Java 7; you will need to install an appropriate JDK.

To have launchd start elasticsearch at login:
    ln -sfv /usr/local/opt/elasticsearch/*.plist ~/Library/LaunchAgents
Then to load elasticsearch now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.elasticsearch.plist
Or, if you don't want/need launchctl, you can just run:
    elasticsearch --config=/usr/local/opt/elasticsearch/config/elasticsearch.yml
==> Summary
🍺  /usr/local/Cellar/elasticsearch/1.3.2: 36 files, 30M, built in 8 seconds
elasticsearch: stable 1.3.2, HEAD
http://www.elasticsearch.org
/usr/local/Cellar/elasticsearch/1.3.2 (36 files, 30M) *
  Built from source
From: https://github.com/Homebrew/homebrew/blob/master/Library/Formula/elasticsearch.rb
==> Caveats
Data:    /usr/local/var/elasticsearch/elasticsearch_walther/
Logs:    /usr/local/var/log/elasticsearch/elasticsearch_walther.log
Plugins: /usr/local/var/lib/elasticsearch/plugins/

ElasticSearch requires Java 7; you will need to install an appropriate JDK.

To have launchd start elasticsearch at login:
    ln -sfv /usr/local/opt/elasticsearch/*.plist ~/Library/LaunchAgents
Then to load elasticsearch now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.elasticsearch.plist
Or, if you don't want/need launchctl, you can just run:
    elasticsearch --config=/usr/local/opt/elasticsearch/config/elasticsearch.yml
froeslev/ (master *) $ java --version
Unrecognized option: --version
Could not create the Java virtual machine.
froeslev/ (master *) $ java
Usage: java [-options] class [args...]
           (to execute a class)
   or  java [-options] -jar jarfile [args...]
           (to execute a jar file)

where options include:
    -d32          use a 32-bit data model if available
    -d64          use a 64-bit data model if available (implies -server, only for x86_64)
    -client	  to select the "client" VM
    -server	  to select the "server" VM
    -jvm	  is a synonym for the "client" VM  [deprecated]
    -hotspot	  is a synonym for the "client" VM  [deprecated]
                  The default VM is client.
                  
    -cp <class search path of directories and zip/jar files>
    -classpath <class search path of directories and zip/jar files>
                  A : separated list of directories, JAR archives,
                  and ZIP archives to search for class files.
    -D<name>=<value>
                  set a system property
    -verbose[:class|gc|jni]
                  enable verbose output
    -version      print product version and exit
    -version:<value>
                  require the specified version to run
    -showversion  print product version and continue
    -jre-restrict-search | -jre-no-restrict-search
                  include/exclude user private JREs in the version search
    -? -help      print this help message
    -X            print help on non-standard options
    -ea[:<packagename>...|:<classname>]
    -enableassertions[:<packagename>...|:<classname>]
                  enable assertions
    -da[:<packagename>...|:<classname>]
    -disableassertions[:<packagename>...|:<classname>]
                  disable assertions
    -esa | -enablesystemassertions
                  enable system assertions
    -dsa | -disablesystemassertions
                  disable system assertions
    -agentlib:<libname>[=<options>]
                  load native agent library <libname>, e.g. -agentlib:hprof
                    see also, -agentlib:jdwp=help and -agentlib:hprof=help
    -agentpath:<pathname>[=<options>]
                  load native agent library by full pathname
    -javaagent:<jarpath>[=<options>]
                  load Java programming language agent, see java.lang.instrument
    -splash:<imagepath>
                  show splash screen with specified image
froeslev/ (master *) $ java -v
Unrecognized option: -v
Could not create the Java virtual machine.
froeslev/ (master *) $ java -?
Usage: java [-options] class [args...]
           (to execute a class)
   or  java [-options] -jar jarfile [args...]
           (to execute a jar file)

where options include:
    -d32          use a 32-bit data model if available
    -d64          use a 64-bit data model if available (implies -server, only for x86_64)
    -client	  to select the "client" VM
    -server	  to select the "server" VM
    -jvm	  is a synonym for the "client" VM  [deprecated]
    -hotspot	  is a synonym for the "client" VM  [deprecated]
                  The default VM is client.
                  
    -cp <class search path of directories and zip/jar files>
    -classpath <class search path of directories and zip/jar files>
                  A : separated list of directories, JAR archives,
                  and ZIP archives to search for class files.
    -D<name>=<value>
                  set a system property
    -verbose[:class|gc|jni]
                  enable verbose output
    -version      print product version and exit
    -version:<value>
                  require the specified version to run
    -showversion  print product version and continue
    -jre-restrict-search | -jre-no-restrict-search
                  include/exclude user private JREs in the version search
    -? -help      print this help message
    -X            print help on non-standard options
    -ea[:<packagename>...|:<classname>]
    -enableassertions[:<packagename>...|:<classname>]
                  enable assertions
    -da[:<packagename>...|:<classname>]
    -disableassertions[:<packagename>...|:<classname>]
                  disable assertions
    -esa | -enablesystemassertions
                  enable system assertions
    -dsa | -disablesystemassertions
                  disable system assertions
    -agentlib:<libname>[=<options>]
                  load native agent library <libname>, e.g. -agentlib:hprof
                    see also, -agentlib:jdwp=help and -agentlib:hprof=help
    -agentpath:<pathname>[=<options>]
                  load native agent library by full pathname
    -javaagent:<jarpath>[=<options>]
                  load Java programming language agent, see java.lang.instrument
    -splash:<imagepath>
                  show splash screen with specified image
froeslev/ (master *) $ java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-462-11M4609)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-462, mixed mode)
froeslev/ (master *) $ java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-462-11M4609)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-462, mixed mode)
froeslev/ (master *) $ export JAVA_HOME="/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home"
froeslev/ (master *) $ java -version
java version "1.7.0_67"
Java(TM) SE Runtime Environment (build 1.7.0_67-b01)
Java HotSpot(TM) 64-Bit Server VM (build 24.65-b04, mixed mode)
froeslev/ (master *) $ vi ~/.bash_profile
froeslev/ (master *) $ ln -sfv /usr/local/opt/elasticsearch/*.plist ~/Library/LaunchAgents
/Users/walther/Library/LaunchAgents/homebrew.mxcl.elasticsearch.plist -> /usr/local/opt/elasticsearch/homebrew.mxcl.elasticsearch.plist
froeslev/ (master *) $ launchctl load ~/Library/LaunchAgents/homebrew.mxcl.elasticsearch.plist
froeslev/ (master *) $ ps ax | grep elas

```

# Copied the Devise Views on 27-08-2014
One of the issues to handle manually - as instructed by Devise installation text - was an optional copy of views, which I did with

```
leaner/ (master *) $ rails g devise:views
      invoke  Devise::Generators::SharedViewsGenerator
      create    app/views/devise/shared
      create    app/views/devise/shared/_links.erb
      invoke  simple_form_for
      create    app/views/devise/confirmations
      create    app/views/devise/confirmations/new.html.erb
       exist    app/views/devise/passwords
    conflict    app/views/devise/passwords/edit.html.erb
  Overwrite /Users/walther/Documents/RailsProjects/leaner/app/views/devise/passwords/edit.html.erb? (enter "h" for help) [Ynaqdh] n
        skip    app/views/devise/passwords/edit.html.erb
    conflict    app/views/devise/passwords/new.html.erb
  Overwrite /Users/walther/Documents/RailsProjects/leaner/app/views/devise/passwords/new.html.erb? (enter "h" for help) [Ynaqdh] n
        skip    app/views/devise/passwords/new.html.erb
       exist    app/views/devise/registrations
    conflict    app/views/devise/registrations/edit.html.erb
  Overwrite /Users/walther/Documents/RailsProjects/leaner/app/views/devise/registrations/edit.html.erb? (enter "h" for help) [Ynaqdh] n
        skip    app/views/devise/registrations/edit.html.erb
    conflict    app/views/devise/registrations/new.html.erb
  Overwrite /Users/walther/Documents/RailsProjects/leaner/app/views/devise/registrations/new.html.erb? (enter "h" for help) [Ynaqdh] n
        skip    app/views/devise/registrations/new.html.erb
       exist    app/views/devise/sessions
    conflict    app/views/devise/sessions/new.html.erb
  Overwrite /Users/walther/Documents/RailsProjects/leaner/app/views/devise/sessions/new.html.erb? (enter "h" for help) [Ynaqdh] n
        skip    app/views/devise/sessions/new.html.erb
      create    app/views/devise/unlocks
      create    app/views/devise/unlocks/new.html.erb
      invoke  erb
      create    app/views/devise/mailer
      create    app/views/devise/mailer/confirmation_instructions.html.erb
      create    app/views/devise/mailer/reset_password_instructions.html.erb
      create    app/views/devise/mailer/unlock_instructions.html.erb
leaner/ (master *) $
```


# Created the Leaner Project on 27-08-2014
Using the following commands I created the project 'from scratch' :)

First though I added a Heruku account and an account with Segment.io


## Added a Heruku app on 27-08-2014
git@heroku.com:leaner.git 
http://leaner.herokuapp.com/
git clone git@heroku.com:leaner.git -o heroku

## Added a Segment.IO account on 27-08-2014
https://segment.io/wdiechmann/lean/setup

Then I started the RailsComposer

```
RailsProjects/ $ mkdir leaner
RailsProjects/ $ cd leaner
leaner/ $ rbenv local 2.1.2
leaner/ $ cd .
leaner/ $ clear

leaner/ $ rails new . -m https://raw.github.com/RailsApps/rails-composer/master/composer.rb
       exist
      create  README.rdoc
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/assets/javascripts/application.js
      create  app/assets/stylesheets/application.css
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/views/layouts/application.html.erb
      create  app/assets/images/.keep
      create  app/mailers/.keep
      create  app/models/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/bundle
      create  bin/rails
      create  bin/rake
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/secrets.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/session_store.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/favicon.ico
      create  public/robots.txt
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/test_helper.rb
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor/assets/javascripts
      create  vendor/assets/javascripts/.keep
      create  vendor/assets/stylesheets
      create  vendor/assets/stylesheets/.keep
       apply  https://raw.github.com/RailsApps/rails-composer/master/composer.rb
    composer
    composer   _____       _ _
    composer  |  __ \     (_) |       /\
    composer  | |__) |__ _ _| |___   /  \   _ __  _ __  ___
    composer  |  _  // _` | | / __| / /\ \ | '_ | '_ \/ __|
    composer  | | \ \ (_| | | \__ \/ ____ \| |_) | |_) \__ \
    composer  |_|  \_\__,_|_|_|___/_/    \_\ .__/| .__/|___/
    composer                               | |   | |
    composer                               | |   | |
    composer
    composer  Rails Composer, open source, supported by subscribers.
    composer  Please join RailsApps to support development of Rails Composer.
    composer  Need help? Ask on Stack Overflow with the tag 'railsapps.'
    composer  Your new application will contain diagnostics in its README file.
      insert    config/application.rb
      recipe  Running core recipe...
        core  selected all core recipes
      recipe  Running git recipe...
         git  initialize git
      remove    .gitignore
      create    .gitignore
         run    git init from "."
Initialized empty Git repository in /Users/walther/Documents/RailsProjects/leaner/.git/
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: initial commit" from "."
      recipe  Running railsapps recipe...
      option  Build a starter application?
          1)  Build a RailsApps example application
          2)  Contributed applications (none available)
          3)  Custom application (experimental)
      choose  Enter your selection: 3
              Get on the mailing list for Rails Composer news?
      option  Enter your email address: walther@diechmann.net
      recipe  Running learn_rails recipe...
      recipe  Running rails_bootstrap recipe...
      recipe  Running rails_foundation recipe...
      recipe  Running rails_omniauth recipe...
      recipe  Running rails_devise recipe...
      recipe  Running rails_devise_pundit recipe...
      recipe  Running rails_signup_download recipe...
      recipe  Running rails_mailinglist_signup recipe...
      recipe  Running setup recipe...
       setup  Your operating system is darwin13.3.0.
       setup  You are using Ruby version 2.1.2.
       setup  You are using Rails version 4.1.5.
      option  Web server for development?
          1)  WEBrick (default)
          2)  Thin
          3)  Unicorn
          4)  Puma
          5)  Phusion Passenger (Apache/Nginx)
          6)  Phusion Passenger (Standalone)
      choose  Enter your selection: 2
      option  Web server for production?
          1)  Same as development
          2)  Thin
          3)  Unicorn
          4)  Puma
          5)  Phusion Passenger (Apache/Nginx)
          6)  Phusion Passenger (Standalone)
      choose  Enter your selection: 2
      option  Database used in development?
          1)  SQLite
          2)  PostgreSQL
          3)  MySQL
      choose  Enter your selection: 2
      option  Template engine?
          1)  ERB
          2)  Haml
          3)  Slim
      choose  Enter your selection: 2
      option  Test framework?
          1)  None
          2)  RSpec with Capybara
      choose  Enter your selection: 2
       setup  Adding DatabaseCleaner, FactoryGirl, Faker, Launchy, Selenium
      option  Continuous testing?
          1)  None
          2)  Guard
      choose  Enter your selection: 1
      option  Front-end framework?
          1)  None
          2)  Bootstrap 3.0
          3)  Bootstrap 2.3
          4)  Zurb Foundation 5.0
          5)  Zurb Foundation 4.0
          6)  Simple CSS
      choose  Enter your selection: 2
      option  Add support for sending email?
          1)  None
          2)  Gmail
          3)  SMTP
          4)  SendGrid
          5)  Mandrill
      choose  Enter your selection: 5
      option  Authentication?
          1)  None
          2)  Devise
          3)  OmniAuth
      choose  Enter your selection: 2
      option  Devise modules?
          1)  Devise with default modules
          2)  Devise with Confirmable module
          3)  Devise with Confirmable and Invitable modules
      choose  Enter your selection: 3
      option  Authorization?
          1)  None
          2)  Pundit
      choose  Enter your selection: 2
      option  Use a form builder gem?
          1)  None
          2)  SimpleForm
      choose  Enter your selection: 2
      option  Add pages?
          1)  None
          2)  Home
          3)  Home and About
          4)  Home and Users
          5)  Home, About, and Users
      choose  Enter your selection: 5
      create    README
      append    README
      recipe  Running locale recipe...
      option  Set a locale? Enter nothing for English, or es, de, etc:
      recipe  Running readme recipe...
      recipe  Running gems recipe...
      insert    Gemfile
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: Gemfile" from "."
      recipe  Running tests recipe...
      recipe  Running email recipe...
      recipe  Running devise recipe...
      recipe  Running omniauth recipe...
      recipe  Running roles recipe...
      recipe  Running frontend recipe...
      recipe  Running pages recipe...
      recipe  Running init recipe...
      recipe  Running analytics recipe...
      option  Install page-view analytics?
          1)  None
          2)  Google Analytics
          3)  Segment.io
      choose  Enter your selection: 3
      option  Segment.io API key? l62r9st9qe
      recipe  Running deployment recipe...
      option  Add a deployment mechanism?
          1)  None
          2)  Capistrano3
      choose  Enter your selection: 2
  deployment  recipe adding capistrano gems
      recipe  Running extras recipe...
      option  Set a robots.txt file to ban spiders? (y/n) y
      option  Create a GitHub repository? (y/n) y
      option  Add gem and file for environment variables?
          1)  None
          2)  Add .env with Foreman
          3)  Add application.yml with Figaro
      choose  Enter your selection: 2
      option  Reduce assets logger noise during development? (y/n) y
      option  Improve error reporting with 'better_errors' during development? (y/n) y
      option  Use 'pry' as console replacement during development and test? (y/n) y
      option  Use or create a project-specific rvm gemset? (y/n) n
      extras  recipe setting quiet_assets for reduced asset pipeline logging
      extras  recipe creating .env file for development environment variables with foreman
      extras  recipe adding better_errors gem
      extras  recipe adding pry-rails gem
      extras  recipe banning spiders by modifying 'public/robots.txt'
    composer  Installing gems. This will take a while.
         run    bundle install --without production from "."
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Using rake 10.3.2
Using i18n 0.6.11
Using json 1.8.1
Using minitest 5.4.0
Using thread_safe 0.3.4
Using tzinfo 1.2.2
Using activesupport 4.1.5
Using builder 3.2.2
Using erubis 2.7.0
Using actionview 4.1.5
Using rack 1.5.2
Using rack-test 0.6.2
Using actionpack 4.1.5
Using mime-types 1.25.1
Using polyglot 0.3.5
Using treetop 1.4.15
Using mail 2.5.4
Using actionmailer 4.1.5
Using activemodel 4.1.5
Using arel 5.0.1.20140414130214
Using activerecord 4.1.5
Using addressable 2.3.6
Using bcrypt 3.1.7
Using coderay 1.1.0
Using better_errors 2.0.0
Using debug_inspector 0.0.2
Using binding_of_caller 0.7.2
Using sass 3.2.19
Using bootstrap-sass 3.2.0.1
Using bundler 1.7.0
Using colorize 0.7.3
Using net-ssh 2.9.1
Using net-scp 1.2.1
Using sshkit 1.5.1
Using capistrano 3.0.1
Using capistrano-bundler 1.1.2
Using capistrano-rails 1.1.0
Using capistrano-rails-console 0.2.0
Using capistrano-rvm 0.1.1
Using mini_portile 0.6.0
Using nokogiri 1.6.3.1
Using xpath 2.0.0
Using capybara 2.4.1
Using ffi 1.9.3
Using childprocess 0.5.3
Using coffee-script-source 1.7.1
Using execjs 2.2.1
Using coffee-script 2.3.0
Using thor 0.19.1
Using railties 4.1.5
Using coffee-rails 4.0.1
Using daemons 1.1.9
Using database_cleaner 1.3.0
Using orm_adapter 0.5.0
Using warden 1.2.3
Using devise 3.3.0
Using devise_invitable 1.3.6
Using diff-lcs 1.2.5
Using dotenv-deployment 0.0.2
Using dotenv 0.11.1
Using eventmachine 1.0.3
Using factory_girl 4.4.0
Using factory_girl_rails 4.4.1
Using faker 1.4.3
Using foreman 0.74.0
Using tilt 1.4.1
Using haml 4.1.0.beta.1
Using haml-rails 0.5.3
Using high_voltage 2.2.1
Using hike 1.2.3
Using hpricot 0.8.6
Using sexp_processor 4.4.4
Using ruby_parser 3.1.3
Using html2haml 1.0.1
Using hub 1.12.2
Using interception 0.5
Using multi_json 1.10.1
Using jbuilder 2.1.3
Using jquery-rails 3.1.1
Using launchy 2.4.2
Using method_source 0.8.2
Using pg 0.17.1
Using slop 3.6.0
Using pry 0.10.1
Using pry-rails 0.3.2
Using pry-rescue 1.4.1
Using pundit 0.3.0
Using quiet_assets 1.0.3
Using sprockets 2.11.0
Using sprockets-rails 2.1.3
Using rails 4.1.5
Using rails_apps_pages 0.5.12
Using rails_apps_testing 0.3.10
Using rails_layout 1.0.21
Using rdoc 4.1.1
Using rspec-support 3.0.4
Using rspec-core 3.0.4
Using rspec-expectations 3.0.4
Using rspec-mocks 3.0.4
Using rspec-rails 3.0.2
Using rubyzip 1.1.6
Using sass-rails 4.0.3
Using sdoc 0.4.1
Using websocket 1.0.7
Using selenium-webdriver 2.42.0
Using simple_form 3.0.2
Using spring 1.1.3
Using thin 1.6.2
Using turbolinks 2.3.0
Using uglifier 2.5.3
Your bundle is complete!
Gems in the group production were not installed.
Use `bundle show [gemname]` to see where a bundled gem is installed.
    composer  Updating gem paths.
WARN: Unresolved specs during Gem::Specification.reset:
      rake (>= 0.8.7)
WARN: Clearing out unresolved specs.
Please report a bug if this causes problems.
    composer  Stage Two (running recipe 'stage_two' callbacks).
    composer  importing html2haml conversion tool
locale
gems
        gems  recipe stage two
        gems  configuring database
      remove    config/database.yml
      create    config/database.yml
      option  Username for PostgreSQL?(leave blank to use the app name) leaner
      option  Host for PostgreSQL in database.yml? (leave blank to use default socket connection) localhost
        gsub    config/database.yml
      option  Password for PostgreSQL user leaner? meaner!
        gsub    config/database.yml
        gems  set config/database.yml for username/password leaner/meaner!
        gsub    config/database.yml
        gsub    config/database.yml
        gsub    config/database.yml
        gsub    config/database.yml
        gsub    config/database.yml
      option  Okay to drop all existing databases named leaner? 'No' will abort immediately! (y/n) y
         run    bundle exec rake db:drop from "."
         run    bundle exec rake db:create:all from "."
leaner_production already exists
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: create database" from "."
gems
        gems  recipe stage two
        gems  running generators
        gems  recipe installing simple_form for use with Bootstrap
    generate    simple_form:install --bootstrap
      create  config/initializers/simple_form.rb
      create  config/initializers/simple_form_bootstrap.rb
       exist  config/locales
      create  config/locales/simple_form.en.yml
      create  lib/templates/haml/scaffold/_form.html.haml
===============================================================================

  Be sure to have a copy of the Bootstrap stylesheet available on your
  application, you can get it on http://twitter.github.com/bootstrap.

  Inside your views, use the 'simple_form_for' with one of the Bootstrap form
  classes, '.form-horizontal', '.form-inline', '.form-search' or
  '.form-vertical', as the following:

    = simple_form_for(@user, html: {class: 'form-horizontal' }) do |form|

===============================================================================
      create    .env
      create    Procfile
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: generators" from "."
tests
       tests  recipe stage two
       tests  recipe installing RSpec
    generate    testing:configure rspec -f
         run  rm -rf test/ from "."
    generate  rspec:install
      create  .rspec
      create  spec
      create  spec/spec_helper.rb
      create  spec/rails_helper.rb
      insert  .rspec
      insert  .rspec
        gsub  .rspec
      insert  config/application.rb
      create  spec/support/capybara.rb
        gsub  spec/rails_helper.rb
      create  spec/support/database_cleaner.rb
      create  spec/support/factory_girl.rb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: testing framework" from "."
email
       email  recipe stage two
      insert    config/environments/development.rb
      insert    config/environments/production.rb
        gsub    config/environments/production.rb
      insert    config/environments/development.rb
      insert    config/environments/production.rb
        gsub    config/environments/development.rb
        gsub    config/environments/production.rb
        gsub    config/environments/development.rb
        gsub    config/environments/production.rb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: set email accounts" from "."
devise
      devise  recipe stage two
        gsub    config/initializers/filter_parameter_logging.rb
    generate    devise:install
      create  config/initializers/devise.rb
      create  config/locales/devise.en.yml
===============================================================================

Some setup you must do manually if you haven't yet:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:

       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

     In production, :host should be set to the actual host of your application.

  2. Ensure you have defined root_url to *something* in your config/routes.rb.
     For example:

       root to: "home#index"

  3. Ensure you have flash messages in app/views/layouts/application.html.erb.
     For example:

       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>

  4. If you are deploying on Heroku with Rails 3.2 only, you may want to set:

       config.assets.initialize_on_precompile = false

     On config/application.rb forcing your application to not access the DB
     or load models when precompiling your assets.

  5. You can copy Devise views (for customization) to your app by running:

       rails g devise:views

===============================================================================
    generate    devise_invitable:install
      insert  config/initializers/devise.rb
      create  config/locales/devise_invitable.en.yml
    generate    devise user
      invoke  active_record
      create    db/migrate/20140827142456_devise_create_users.rb
      create    app/models/user.rb
      invoke    rspec
      create      spec/models/user_spec.rb
      invoke      factory_girl
      create        spec/factories/users.rb
      insert    app/models/user.rb
       route  devise_for :users
    generate    migration AddNameToUsers name:string
      invoke  active_record
      create    db/migrate/20140827142459_add_name_to_users.rb
        gsub    app/models/user.rb
    generate    migration AddConfirmableToUsers confirmation_token:string confirmed_at:datetime confirmation_sent_at:datetime unconfirmed_email:string
      invoke  active_record
      create    db/migrate/20140827142501_add_confirmable_to_users.rb
         run    bundle exec rake db:migrate from "."
== 20140827142456 DeviseCreateUsers: migrating ================================
-- create_table(:users)
   -> 0.0063s
-- add_index(:users, :email, {:unique=>true})
   -> 0.0016s
-- add_index(:users, :reset_password_token, {:unique=>true})
   -> 0.0012s
== 20140827142456 DeviseCreateUsers: migrated (0.0092s) =======================

== 20140827142459 AddNameToUsers: migrating ===================================
-- add_column(:users, :name, :string)
   -> 0.0005s
== 20140827142459 AddNameToUsers: migrated (0.0006s) ==========================

== 20140827142501 AddConfirmableToUsers: migrating ============================
-- add_column(:users, :confirmation_token, :string)
   -> 0.0004s
-- add_column(:users, :confirmed_at, :datetime)
   -> 0.0003s
-- add_column(:users, :confirmation_sent_at, :datetime)
   -> 0.0003s
-- add_column(:users, :unconfirmed_email, :string)
   -> 0.0003s
== 20140827142501 AddConfirmableToUsers: migrated (0.0014s) ===================

         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: devise" from "."
omniauth
    omniauth  recipe stage two
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: omniauth" from "."
On branch master
nothing to commit, working directory clean
roles
       roles  recipe stage two
    generate    migration AddRoleToUsers role:integer
      invoke  active_record
      create    db/migrate/20140827142505_add_role_to_users.rb
      insert    app/models/user.rb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: add roles to a User model" from "."
frontend
    frontend  recipe stage two
    generate    layout:install bootstrap3 -f
      remove  app/assets/stylesheets/application.css
      create  app/assets/stylesheets/application.css.scss
      create  app/assets/stylesheets/framework_and_overrides.css.scss
       force  app/assets/javascripts/application.js
      remove  app/assets/stylesheets/simple.css
      remove  app/assets/stylesheets/foundation_and_overrides.css.scss
      append  app/assets/stylesheets/framework_and_overrides.css.scss
      remove  app/views/layouts/application.html.erb
      create  app/views/layouts/application.html.haml
      create  app/views/layouts/_messages.html.haml
      create  app/views/layouts/_navigation.html.haml
      create  app/views/layouts/_navigation_links.html.erb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: front-end framework" from "."
pages
       pages  recipe stage two
    generate    pages:about -f
    generate  pages:home -f
      create  app/views/visitors/index.html.erb
      create  app/controllers/visitors_controller.rb
      insert  config/routes.rb
      create  spec/features/visitors/home_page_spec.rb
      create  app/views/pages/about.html.erb
      create  spec/features/visitors/about_page_spec.rb
    generate    pages:users -f
      create  app/views/users/_user.html.erb
      create  app/views/users/index.html.erb
      create  app/views/users/show.html.erb
    generate  pages:home -f
   identical  spec/features/visitors/home_page_spec.rb
       force  app/views/visitors/index.html.erb
      create  app/controllers/users_controller.rb
      insert  config/routes.rb
      create  config/initializers/devise_permitted_parameters.rb
     prepend  app/views/users/_user.html.erb
      insert  app/views/users/show.html.erb
    generate    pages:authorized -f
      create  config/initializers/pundit.rb
       force  app/views/users/_user.html.erb
       force  app/controllers/users_controller.rb
      create  app/policies/user_policy.rb
    generate    layout:navigation -f
   identical  app/views/layouts/_navigation_links.html.erb
      append  app/views/layouts/_navigation_links.html.erb
      append  app/views/layouts/_navigation_links.html.erb
      create  spec/features/visitors/navigation_spec.rb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: add pages" from "."
analytics
   analytics  recipe stage two
    generate    analytics:segmentio -f
      create  app/assets/javascripts/segmentio.js
        gsub    app/assets/javascripts/segmentio.js
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: add analytics" from "."
deployment
  deployment  recipe stage two
  deployment  recipe capistrano file
         run    bundle exec cap install from "."
mkdir -p config/deploy
[deprecated] I18n.enforce_available_locales will default to true in the future. If you really want to skip validation of your locale you can set I18n.enforce_available_locales = false to avoid this message.
create config/deploy.rb
create config/deploy/staging.rb
create config/deploy/production.rb
mkdir -p lib/capistrano/tasks
Capified
extras
      extras  recipe stage two
        gsub    public/robots.txt
        gsub    public/robots.txt
    composer  Stage Three (running recipe 'stage_three' callbacks).
readme
      readme  recipe stage three
      remove    README
      remove    README.rdoc
      remove    doc/README_FOR_APP
      create    README
      append    README
      append    README
      create    public/humans.txt
      create    README.md
      append    README.md
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: add README files" from "."
tests
       tests  recipe stage three
    generate    testing:configure devise -f
      create  spec/support/devise.rb
      create  spec/support/helpers/session_helpers.rb
      create  spec/support/helpers.rb
       force  spec/factories/users.rb
       force  spec/models/user_spec.rb
      create  spec/features/users/sign_in_spec.rb
      create  spec/features/users/sign_out_spec.rb
      create  spec/features/users/user_delete_spec.rb
      create  spec/features/users/user_edit_spec.rb
      create  spec/features/users/user_index_spec.rb
      create  spec/features/users/user_show_spec.rb
      create  spec/features/visitors/sign_up_spec.rb
      insert    spec/factories/users.rb
      insert    config/environments/test.rb
        gsub    spec/features/users/user_edit_spec.rb
        gsub    spec/features/visitors/sign_up_spec.rb
    generate    testing:configure pundit -f
       force  spec/factories/users.rb
       force  spec/features/users/user_index_spec.rb
      create  spec/policies/user_policy_spec.rb
      create  spec/support/pundit.rb
      insert    spec/factories/users.rb
init
        init  recipe stage three
      insert    config/secrets.yml
      insert    config/secrets.yml
      insert    config/secrets.yml
      insert    config/secrets.yml
      append    .env
      insert    config/secrets.yml
      insert    config/secrets.yml
      insert    config/secrets.yml
      append    .env
        gsub    config/initializers/devise.rb
      create    .env.example
      remove    db/seeds.rb
      create    db/seeds.rb
      remove    app/services/create_admin_service.rb
      create    app/services/create_admin_service.rb
      append    db/seeds.rb
      insert    app/services/create_admin_service.rb
         run    foreman run bundle exec rake db:migrate from "."
== 20140827142505 AddRoleToUsers: migrating ===================================
-- add_column(:users, :role, :integer)
   -> 0.0006s
== 20140827142505 AddRoleToUsers: migrated (0.0006s) ==========================

    generate    devise_invitable user
      insert  app/models/user.rb
      invoke  active_record
      create    db/migrate/20140827142534_devise_invitable_add_to_users.rb
        init  applying migrations and seeding the database
         run    foreman run bundle exec rake db:migrate from "."
== 20140827142534 DeviseInvitableAddToUsers: migrating ========================
-- change_table(:users)
   -> 0.0215s
-- change_column_null(:users, :encrypted_password, true)
   -> 0.0004s
== 20140827142534 DeviseInvitableAddToUsers: migrated (0.0220s) ===============

         run    foreman run bundle exec rake db:seed from "."
CREATED ADMIN USER: user@example.com
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: set up database" from "."
    generate    layout:devise bootstrap3 -f
      create  app/views/devise/sessions/new.html.erb
      create  app/views/devise/passwords/new.html.erb
      create  app/views/devise/passwords/edit.html.erb
      create  app/views/devise/registrations/new.html.erb
      create  app/views/devise/registrations/edit.html.erb
        gsub  app/views/devise/registrations/new.html.erb
        gsub  app/views/devise/registrations/edit.html.erb
      insert  app/views/devise/registrations/new.html.erb
      insert  app/views/devise/registrations/edit.html.erb
    generate    layout:navigation -f
       force  app/views/layouts/_navigation_links.html.erb
      append  app/views/layouts/_navigation_links.html.erb
      append  app/views/layouts/_navigation_links.html.erb
   identical  spec/features/visitors/navigation_spec.rb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: navigation links" from "."
extras
      extras  recipe stage three
      extras  recipe removing unnecessary files and whitespace
      remove    public/index.html
      remove    app/assets/images/rails.png
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile
        gsub    Gemfile
        gsub    config/routes.rb
        gsub    config/routes.rb
         run    git add -A from "."
         run    git commit -qm "rails_apps_composer: extras" from "."
extras
      extras  recipe stage three
      extras  recipe creating GitHub repository
         run    hub create leaner from "."
Updating origin
created repository: wdiechmann/leaner
         run    hub push -u origin master from "."
Counting objects: 258, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (226/226), done.
Writing objects: 100% (258/258), 57.70 KiB | 0 bytes/s, done.
Total 258 (delta 78), reused 0 (delta 0)
To git@github.com:wdiechmann/leaner.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
    composer  Your new application will contain diagnostics in its README file.
    composer  When reporting an issue on GitHub, include the README diagnostics.
    composer  Finished running the rails_apps_composer app template.
    composer  Your new Rails app is ready. Time to run 'bundle install'.
         run  bundle install
Resolving dependencies...
Using rake 10.3.2
Using i18n 0.6.11
Using json 1.8.1
Using minitest 5.4.0
Using thread_safe 0.3.4
Using tzinfo 1.2.2
Using activesupport 4.1.5
Using builder 3.2.2
Using erubis 2.7.0
Using actionview 4.1.5
Using rack 1.5.2
Using rack-test 0.6.2
Using actionpack 4.1.5
Using mime-types 1.25.1
Using polyglot 0.3.5
Using treetop 1.4.15
Using mail 2.5.4
Using actionmailer 4.1.5
Using activemodel 4.1.5
Using arel 5.0.1.20140414130214
Using activerecord 4.1.5
Using addressable 2.3.6
Using bcrypt 3.1.7
Using coderay 1.1.0
Using better_errors 2.0.0
Using debug_inspector 0.0.2
Using binding_of_caller 0.7.2
Using sass 3.2.19
Using bootstrap-sass 3.2.0.1
Using bundler 1.7.0
Using colorize 0.7.3
Using net-ssh 2.9.1
Using net-scp 1.2.1
Using sshkit 1.5.1
Using capistrano 3.0.1
Using capistrano-bundler 1.1.2
Using capistrano-rails 1.1.0
Using capistrano-rails-console 0.2.0
Using capistrano-rvm 0.1.1
Using mini_portile 0.6.0
Using nokogiri 1.6.3.1
Using xpath 2.0.0
Using capybara 2.4.1
Using ffi 1.9.3
Using childprocess 0.5.3
Using coffee-script-source 1.7.1
Using execjs 2.2.1
Using coffee-script 2.3.0
Using thor 0.19.1
Using railties 4.1.5
Using coffee-rails 4.0.1
Using daemons 1.1.9
Using database_cleaner 1.3.0
Using orm_adapter 0.5.0
Using warden 1.2.3
Using devise 3.3.0
Using devise_invitable 1.3.6
Using diff-lcs 1.2.5
Using dotenv-deployment 0.0.2
Using dotenv 0.11.1
Using eventmachine 1.0.3
Using factory_girl 4.4.0
Using factory_girl_rails 4.4.1
Using faker 1.4.3
Using foreman 0.74.0
Using tilt 1.4.1
Using haml 4.1.0.beta.1
Using haml-rails 0.5.3
Using high_voltage 2.2.1
Using hike 1.2.3
Using hpricot 0.8.6
Using sexp_processor 4.4.4
Using ruby_parser 3.1.3
Using html2haml 1.0.1
Using hub 1.12.2
Using interception 0.5
Using multi_json 1.10.1
Using jbuilder 2.1.3
Using jquery-rails 3.1.1
Using launchy 2.4.2
Using method_source 0.8.2
Using pg 0.17.1
Using slop 3.6.0
Using pry 0.10.1
Using pry-rails 0.3.2
Using pry-rescue 1.4.1
Using pundit 0.3.0
Using quiet_assets 1.0.3
Using sprockets 2.11.0
Using sprockets-rails 2.1.3
Using rails 4.1.5
Using rails_layout 1.0.21
Using rdoc 4.1.1
Using rspec-support 3.0.4
Using rspec-core 3.0.4
Using rspec-expectations 3.0.4
Using rspec-mocks 3.0.4
Using rspec-rails 3.0.2
Using rubyzip 1.1.6
Using sass-rails 4.0.3
Using sdoc 0.4.1
Using websocket 1.0.7
Using selenium-webdriver 2.42.0
Using simple_form 3.0.2
Using spring 1.1.3
Using thin 1.6.2
Using turbolinks 2.3.0
Using uglifier 2.5.3
Your bundle is complete!
Gems in the group production were not installed.
Use `bundle show [gemname]` to see where a bundled gem is installed.
         run  bundle exec spring binstub --all
* bin/rake: spring inserted
* bin/rails: spring inserted
```
