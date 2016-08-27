## Some setup steps for rails related labs

* add gitignore
  * [rails.gitignore](https://github.com/github/gitignore/blob/master/Rails.gitignore)
* update gemfile
  ```ruby
  gem 'puma'
  gem 'better_errors'
  gem 'binding_of_caller'
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

