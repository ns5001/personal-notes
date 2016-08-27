## Some setup steps for rails related labs

* add gitignore
  * [rails.gitignore](https://github.com/github/gitignore/blob/master/Rails.gitignore)
* update gemfile
  ```ruby
  gem 'puma'
  gem 'better_errors'
  gem 'binding_of_caller'
  gem 'pry-rails'
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


relevant links:

* http://stackoverflow.com/questions/11451535/gitignore-not-working
* https://github.com/rubygems/rubygems/issues/1551
