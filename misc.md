
### Misc

Run a webrick server at specified port from current location

`ruby -r webrick -e "s = WEBrick::HTTPServer.new(:Port => 8000, :DocumentRoot => Dir.pwd); trap('INT') { s.shutdown }; s.start"`