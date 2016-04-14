---
layout: page
title:  "Documentation"
permalink: /docs/
excerpt: "The Monoid documentation."
---

## Basic configuration

{% highlight yaml %}
# _config.yml
title: Your awesome title
tagline: Your awesome tagline
description: > # This means to ignore newlines until "baseurl:"
  Write an awesome description for your new site here. You can edit this
  line in _config.yml. It will appear in your document head meta (for
  Google search results) and in your feed.xml site description.
baseurl: "" # The subpath of your site, e.g. /blog
url: "http://yourdomain.com" # The base hostname & protocol for your site
image: /images/site-image.jpg # The site cover image on the home page
feed: # Set it if your feed path is not /feed.xml, e.g. /atom.xml
paginate: 10 # http://jekyllrb.com/docs/pagination/

disqus_shortname:
google_analytics_tracking_id:
{% endhighlight %}

If `baseurl` is set, you will need to prepend the baseurl to these settings: `feed`, `nav` urls, `og_image`, post cover images, and post thumbnails, e.g. `feed: /blog/feed/`.

## Site navigation

{% highlight yaml %}
# _config.yml
nav:
  - title: "Home"
    url:   "/"
  - title: "Documentation"
    url:   "/docs/"
{% endhighlight %}

## Social icons

{% highlight yaml %}
# _config.yml
social_links:
  - title: "Twitter"
    url:   "https://twitter.com/"
  - title: "Facebook"
    url:   "https://www.facebook.com/"
  - title: "Google+"
    url:   "https://plus.google.com/"
{% endhighlight %}

The social links in the footer. The following sites are supported:

- Twitter
- Facebook
- Google+
- Behance
- Bitbucket
- CodePen
- Dribbble
- Flickr
- Foursquare
- Github
- Instagram
- JSFiddle
- LinkedIn
- Email (mailto:)
- Medium
- Pinterest
- SoundCloud
- reddit
- RSS (just set a "RSS" title, the url is generated in the HTML template (site.baseurl + "/feed.xml" or site.feed)
- Spotify
- Stack Exchange
- Stack Overflow
- Steam
- StumbleUpon
- Trello
- Tumblr
- Twitch
- Vimeo
- WordPress
- YouTube

The icons are displayed base on the urls via CSS.

## Authors

To have author bylines and bio at bottom of posts, add configuration like the following in `_config.yml`:

{% highlight yaml %}
authors:
  johndoe:
    name: John Doe
    website: "http://themeforest.net/"
    bio: An awesome bio # Author info at bottom of post only shows if bio exists
    avatar: /images/avatar.jpg
  joebloggs:
    name: Joe Bloggs
{% endhighlight %}

and specify the author in the Front Matter of posts:

    ---
    author: johndoe
    ---

## Post cover images and thumbnails

In post Front Matter:

    ---
    image: /images/post-image.jpg
    thumbnail: /images/post-thumbnail.jpg
    ---

## Social meta tags

Monoid generates Open Graph and Twitter Cards meta tags automatically for better social media sharing. There are two extra settings:

{% highlight yaml %}
# _config.yml
og_image: /images/og-image.jpg # Fallback og:image when no page.image or site.image. at least 200 x 200px.
twitter_site: # twitter:site. Your Twitter username without "@"
{% endhighlight %}

### Meta description

`page.excerpt` is used for meta description of posts and pages. It is the first paragraph by default for posts. For pages you have to set it in the Front Matter:

    ---
    excerpt: An excerpt
    ---

If it's empty, Facebook will show the first text and Twitter will just leave description empty.

## Tag and category archives

Monoid supports tag and category archive pages by the [Jekyll Archives](https://github.com/jekyll/jekyll-archives) plugin. Run `gem install jekyll-archives` to install if you don't use Gemfile. And add configuration to `_config.yml` like this:

{% highlight yaml %}
gems:
  - jekyll-archives

jekyll-archives:
  enabled:
    - categories
    - tags
{% endhighlight %}
