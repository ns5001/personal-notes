## Ruby related notes


#### Dates

* [Determine Whether Two Date Ranges Overlap](http://stackoverflow.com/questions/325933/determine-whether-two-date-ranges-overlap)

#### Misc

* [Understanding Private Methods](http://stackoverflow.com/questions/4293215/understanding-private-methods-in-ruby/4293330#4293330)

Start a webrick server

* `ruby -r webrick -e "s = WEBrick::HTTPServer.new(:Port => 8000, :DocumentRoot => Dir.pwd); trap('INT') { s.shutdown }; s.start"`