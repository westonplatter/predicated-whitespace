# Predicated Whitespace

Predicated Whitespace is a minimal, responsive, and visualization focused driven theme for [Octopress](http://octopress.org).

## Demos

<!--Default theme: [Themespace Preview](http://themespace.github.io/whitespace/)-->

<!--*If you are using whitespace and would like to showcase your website, we would be very happy to add you to the list! Just tell us your URL via the issue tracking system!*-->

## Install

``` sh
$ cd octopress
$ git clone git://github.com/westonplatter/predicated-whitespace.git .themes/predicated-whitespace
$ rake install['predicated-whitespace'] # for zsh, use: rake install\['predicated-whitespace'\]
$ rake generate
```

## Update

``` sh
$ git -C .themes/predicated-whitespace pull origin master
$ rake install['whitespace']
$ rake generate
```

## Update and Keep Customizations

*For this to work, you have to track your website theme customizations on a remote (we call it ```mywebsiterepo```).*

``` sh
$ git -C .themes/predicated-whitespace pull origin master
$ rake install['predicated-whitespace']
$ cd ../..
$ git fetch --all
$ git reset --hard mywebsiterepo/master
$ rake generate
```

## Comment System

We support the open-source [Juvia](https://github.com/phusion/juvia) comment system. To enable it, add the `juvia_site_key` and `juvia_host` parameters in `_config.yml`.

## Navigation Bar

You can add several icons to the navigation bar. Just set the corresponding user IDs in `_config.yml`:

- `googleplus_user` with `googleplus_hidden: false` for Google+ profile.
- `pinboard_user` for Pinboard bookmarks.
- `delicious_user` for Delicious bookmarks.
- `github_user` with `github_show_profile_link: true` for GitHub profile.
- `twitter_user` for Twitter profile.
- `bitbucket_user` for Bitbucket profile.
- `stackoverflow_user_id` for Stackoverflow profile. (If you look at your profile link its structure is: `http://stackoverflow.com/users/your-user-id/your-login`)
- `linkedin_user` for LinkedIn profile. (To use this icon you'll need to create a custom public profile URL. [Here is a help topic specifying how to do this.](https://help.linkedin.com/app/answers/detail/a_id/87/~/customizing-your-public-profile-url))

## External URL

You can also use our theme to set up a [Linklog](http://en.wikipedia.org/wiki/Linklog)! To publish a link post, just add the `external-url` variable to the YAML section (the header) of your post - and specify a valid URL.

``` yaml
---
layout: post
...
external-url: http://example.com/some/external/url
---
```

The title will be rendered with an arrow (&rarr;) character at the end; and the title link will point to the external url.

## Google+ "authored by" link

If the `googleplus_user` variable is set under `_config.yml`, by default, posts will contain a link with `rel="author"` pointing to the respective Google+ profile.

You can override the pofile for the authored by link for a specific post by adding `googleplus_user` for the post:

``` yaml
---
layout: post
...
gooleplus_user: [put overriding profile id here]
---
```

You can also choose to ignore the link by assigning `ignore` to the `googleplus_user` post variable (in your post header). The "authored by" text will then be displayed without a link.

``` yaml
---
layout: post
...
googleplus_user: ignore
---
```

## AdSense for Search

You can enable Google AdSense™ for search via your whitespace search bar.
For this to work you have to set `simple_search` and `adsense_cse_partner_ID` in your `_config.yml` file (you will have to add a line for the second variable, as it is not used with any other themes).
The value for this variable can be extracted from the custom code for your search bar from a line such as the following:

```
<input type="hidden" name="cx" value="<adsense_cse_partner_ID>" />
```

Example for `_config.yml`:

```
simple_search: https://www.google.com/search
adsense_cse_partner_ID: partner-pub-9999999999999999:9999999999
```

## Edit and History Links

If you choose to track your content via an an open repository (on  GitHub, Bitbucket, etc.) you can also link to your article's history (in the footer) or allow users to contribute via the version controlling backend (link in the header, next to "COMMENTS").
Whitespace automatically enables this if you set the following variables in your `_config.yml` - e.g.:

```
history: https://github.com/youruser/yourblog/commits/master/source/
edit: https://github.com/youruser/yourblog/edit/master/source/
```

## License

See LICENSE file.
