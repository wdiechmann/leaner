
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
