---
layout: index
components:
  - type: pageContent
  - type: recentPosts
    limit: 4
    category: ':any'
    noWrapper: true
    template:
      - 'includes/postPreview_large'
next: 'category1'
---

Thanks for trying out Orchid! Feel free to take a look around, then head over to the 
{{ anchor(title='User Manual', collectionId='external', itemId='user-manual') }} to learn more about using Orchid to make 
your site truly unique. While you're there, check out all our many great 
{{ anchor(title='plugins', collectionId='external', itemId='Plugins') }} and browse our beautiful 
{{ anchor(title='themes', collectionId='external', itemId='Themes') }} to see if there's one that catches your eye.

And finally, if you like Orchid, please support it by starring it on [Github](https://github.com/orchidhq/Orchid) and 
sharing a link on Twitter: <a 
    href="https://twitter.com/share?ref_src=twsrc%5Etfw" 
    class="twitter-share-button" 
    data-text="Check out the site I just made with @OrchidSSG, a new Static Site Generator for Maliek and Kotlin!" 
    data-url="{{site.baseUrl}}" data-show-count="false">Tweet</a>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
>>> from markupsafe import Markup, escape

>>> # escape replaces special characters and wraps in Markup
>>> escape("<script>alert(document.cookie);</script>")
Markup('&lt;script&gt;alert(document.cookie);&lt;/script&gt;')

>>> # wrap in Markup to mark text "safe" and prevent escaping
>>> Markup("<strong>Hello</strong>")
Markup('<strong>hello</strong>')

>>> escape(Markup("<strong>Hello</strong>"))
Markup('<strong>hello</strong>')

>>> # Markup is a str subclass
>>> # methods and operators escape their arguments
>>> template = Markup("Hello <em>{name}</em>")
>>> template.format(name='"World"')
Markup('Hello <em>&#34;World&#34;</em>')
