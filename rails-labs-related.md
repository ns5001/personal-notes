## Some setup steps for rails related labs

* add gitignore
  * [rails.gitignore](https://github.com/github/gitignore/blob/master/Rails.gitignore)
* update gemfile with desired gems
  ```ruby
  # server
  gem 'puma'
  # error output
  gem 'better_errors'
  gem 'binding_of_caller'
  # pry gems
  gem 'pry-rails'
  gem 'pry-byebug'
  
  # Rails Panel: insight to db/rendering/total times, parameter list, rendered views and more
  # for more info https://github.com/dejan/rails_panel
  gem 'meta_request'  
  
  ```
  
  ```bash
  git commit -am "add gitignore, update gemfile"
  ```

* fixup git tracking
  ```bash
  git rm -r --cached .
  git add .
  git commit -m "update git tracking"
  ```
  
* update `spring gem` to rid off error
  ```ruby
    bundle update spring && bundle exec spring binstub --remove --all && bundle exec spring binstub --all
  ```

* runing puma with better_errors
 * use `bundle exec puma -w 1`
 * [reason](https://github.com/charliesome/better_errors#unicorn-puma-and-other-multi-worker-servers)
 * [puma docs](https://github.com/puma/puma#clustered-mode)


* some labs dont include .rspec file so rspec produces no colors, use the below command to generate .rspec
 * `echo -e "--color\n--format documentation\n--require spec_helper" > .rspec`

relevant links:

* http://stackoverflow.com/questions/11451535/gitignore-not-working
* https://github.com/rubygems/rubygems/issues/1551
