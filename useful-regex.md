

Matches site name "twitter.com" and splits

    * `match(/\b\w*\b\.com/).to_s.split(%r{\.\w*}).first`

Validate email
[source](http://stackoverflow.com/a/22994329/6664582)

    * `valid_email_regex = /\A[\w+\-.]+@[a-z\d\-]+(\.[a-z\d\-]+)*\.[a-z]+\z/i`


