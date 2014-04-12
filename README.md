Middleman-OGP
=============

`middleman-opg` is an extension for the [Middleman] static site generator that adds OpenGraph Protocol support.


Configuration
-------------

### In your `config.rb`

```ruby
activate :ogp do |ogp|
  #
  # register namespace with default options
  #
  ogp.namespaces = {
    fb: data.ogp.fb,
    # from data/ogp/fb.yml
    og: data.ogp.og
    # from data/ogp/og.yml
  }
end
```

### In your layout

source/layout.slim

```
html
  head
    meta charset="utf-8"
    title= data.page.title
    - ogp_tags do|name, value|
      meta property=name content=value

  body
    .container
      = yield
```

### In your page source

Page data overrides default options. (deep merge).


```markdown
---
ogp:
  og:
    description: 'This is my fixture Middleman site.'
    image:
      '': http://mydomain.tld/path/to/fbimage.png
      secure_url: https://secure.mydomain.tld/path/to/fbimage.png
      type: image/png
      width: 400
      height: 300
    locale:
      '': en_us
      alternate:
        - ja_jp
        - zh_tw
  fb:
    description: 'This is my fixture Middleman site.'
    image:
      '': http://mydomain.tld/path/to/fbimage.png
      secure_url: https://secure.mydomain.tld/path/to/fbimage.png
      type: image/png
      width: 400
      height: 300
---

Hello
=====

This is the __content__
```


Build & Dependency Status
-------------------------

[![Gem Version](https://badge.fury.io/rb/middleman-ogp.png)][gem]
[![Build Status](https://travis-ci.org/ngs/middleman-ogp.png)][travis]
[![Dependency Status](https://gemnasium.com/ngs/middleman-ogp.png?travis)][gemnasium]
[![Code Quality](https://codeclimate.com/github/ngs/middleman-ogp.png)][codeclimate]

License
-------

Copyright (c) 2014 [Atsushi Nagase]. MIT Licensed, see [LICENSE] for details.

[middleman]: http://middlemanapp.com
[gem]: https://rubygems.org/gems/middleman-ogp
[travis]: http://travis-ci.org/ngs/middleman-ogp
[gemnasium]: https://gemnasium.com/ngs/middleman-ogp
[codeclimate]: https://codeclimate.com/github/ngs/middleman-ogp
[LICENSE]: https://github.com/ngs/middleman-ogp/blob/master/LICENSE.md
[Atsushi Nagase]: http://ngs.io/