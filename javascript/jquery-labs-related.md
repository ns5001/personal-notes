
### Tests related

#### Jasmine Tests

* [gulp-jasmine-livereload-task](https://github.com/mucsi96/gulp-jasmine-livereload-task)
* [gulpfile.js](https://gist.github.com/ozPop/d5385f8c1d3533b0bbade13064f2dc19)


#### Selinium Tests

Do

`gem uninstall chromedriver-helper and brew install chromedriver`

Also add the below to spec_helper.rb

```ruby
Capybara.register_driver :chrome do |app|
  Capybara::Selenium::Driver.new(app, :browser => :chrome)
end

Capybara.javascript_driver = :chrome
```
