## Useful bits for rails related labs

#### Add gitignore
Some labs do not have a gitignore file

* [rails.gitignore](https://github.com/github/gitignore/blob/master/Rails.gitignore)


#### Useful gems for rails labs
Update gemfile with desired gems

 ```ruby
 
 # Server
 gem 'puma'
 
 group :development do
   # Error output
   gem 'better_errors'
   gem 'binding_of_caller'
   
   # Pry gems
   gem 'pry-rails'
   gem 'pry-byebug'
   
   # Rails Panel: insight to db/rendering/total times, parameter list, rendered views and more
   # for more info https://github.com/dejan/rails_panel
   gem 'meta_request'
   
   # Automation
   # [For more info check](https://gist.github.com/ozPop/17ca00f63728f4656416592c83fef290)
   gem 'guard'
   gem 'guard-sass'
   gem 'guard-livereload', '~> 2.5', require: false
 end
 ```
 
If added gitignore and update gemfile, useful git command:

 ```bash
 git commit -am "add gitignore, update gemfile"
 ```

#### Some labs are tracking too many files
Fixup git tracking

 ```bash
 git rm -r --cached .
 git add .
 git commit -m "update git tracking"
 ```

#### Some labs spring gem is producing deprecation errors
Update `spring gem` to rid off errors

 ```ruby
   bundle update spring && bundle exec spring binstub --remove --all && bundle exec spring binstub --all
 ```

#### NOTE on running puma with better_errors gem
Use `bundle exec puma -w 1` command to change number of 'workers'

* [reason](https://github.com/charliesome/better_errors#unicorn-puma-and-other-multi-worker-servers)
* [puma docs](https://github.com/puma/puma#clustered-mode)


#### Some labs dont include .rspec file
Use the below command to generate .rspec

* `echo -e "--color\n--format documentation\n--require spec_helper" > .rspec`

### Other useful misc items:

Deleting items using link_to

* [Steps on how to setup](http://stackoverflow.com/a/35271656/6664582)

#### Rails Forms

Docs for the collection_check_boxes form helper

* [Example](http://edgeapi.rubyonrails.org/classes/ActionView/Helpers/FormBuilder.html#method-i-collection_check_boxes)

How to permit an array with strong parameters

* [Useful SO answer](http://stackoverflow.com/a/16555975/6664582)

[Related lab for above links](https://learn.co/tracks/full-stack-web-development/rails/validations-and-forms/rails-blog-associations-and-validations)

Relevant links:

* http://stackoverflow.com/questions/11451535/gitignore-not-working
* https://github.com/rubygems/rubygems/issues/1551
