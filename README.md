# iso8601 [![Build Status][travis-badge]][travis] [![Tag][tag-badge]][tag] [![Erlang Version][erl-badge]][erl]

*An ISO 8601 date formating and parsing library for Erlang*

[![iso8601 project logo][logo]][logo-large]


#### Contents

* [About](#about-)
* [Usage](#usage-)
* [Known Deficiencies](#known-deficiencies-)
* [License](#license-)


## About [&#x219F;](#contents)

The ``erlang_iso8601`` library was originally created by Sean Sawyer in 2011. In 2016, Sean handed off maintenance of the library to the [erlsci](https://github.com/erlsci) Github org at which point the project (and repo) was renamed to simply ``iso8601``, matching its Erlang app name:

* ``git clone https://github.com/erlsci/iso8601.git``

Thanks to Github's forwarding for project renames and moves, the following still work:

* ``git clone https://github.com/seansawyer/erlang_iso8601.git``
* ``git clone https://github.com/erlsci/erlang_iso8601.git``


## Usage [&#x219F;](#contents)

Add it to your `rebar.config` deps:

```erlang
{iso8601, ".*", {git, "https://github.com/erlsci/iso8601.git", {tag, "1.2.0"}}}
```

Or for `rebar3`:

```erlang
{iso8601, {git, "https://github.com/erlsci/iso8601.git", {tag, "1.2.0"}}}
```

Format a timestamp or calendar datetime tuple:

```erlang
1> iso8601:format(now()).
<<"2012-02-16T01:06:19Z">>
2> iso8601:format(calendar:universal_time()).
<<"2012-02-16T01:06:48Z">>
```

Parse a date string or binary:

```erlang
3> iso8601:parse(<<"2012-02-16T01:06:48Z">>).
{{2012,2,16},{1,6,48}}
4> iso8601:parse("2012-02-16T01:06:48Z").
{{2012,2,16},{1,6,48}}
```

Add 1 hour, 2 minutes and 3 seconds to a datetime tuple:

```erlang
5> Datetime = iso8601:parse(<<"2012-02-16T01:06:48Z">>).
{{2012,2,16},{1,6,48}}
6> iso8601:add_time(Datetime, 1, 2, 3).
{{2012,2,16},{2,8,51}}
```


## Known Deficiencies [&#x219F;](#contents)

* Does not support expanded year representation.
* Does not support fractional times.
* Does not support ordinal dates.
* Does not support intervals.

See the [open issues](https://github.com/erlsci/iso8601/issues)
for more info.


## License [&#x219F;](#contents)

```
The MIT License (MIT)

Copyright © 2011-2014, Sean Sawyer
Copyright © 2012, Tristan Sloughter
Copyright © 2016, Duncan McGreggor
```


<!-- Named page links below: /-->

[travis]: https://travis-ci.org/erlsci/iso8601
[travis-badge]: https://travis-ci.org/erlsci/iso8601.png?branch=master
[tag]: https://github.com/erlsci/iso8601/releases/latest
[tag-badge]: https://img.shields.io/github/tag/erlsci/iso8601.svg
[erl]: http://www.erlang.org/downloads
[erl-badge]: https://img.shields.io/badge/erlang-%E2%89%A5R15B03-blue.svg
[logo]: priv/images/logo.png
[logo-large]: priv/images/logo-large.png
[logo-source]: https://www.flickr.com/photos/theilr/2164085293
