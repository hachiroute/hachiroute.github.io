<<<<<<< HEAD
# Type on Strap 

[![Build Status](https://travis-ci.org/Sylhare/Type-on-Strap.svg?branch=master)](https://travis-ci.org/Sylhare/Type-on-Strap) 
[![Gem Version](https://badge.fury.io/rb/type-on-strap.svg)](https://badge.fury.io/rb/type-on-strap)

A free and open-source [Jekyll](https://jekyllrb.com) theme. Based on Rohan Chandra [type-theme](https://github.com/rohanchandra/type-theme) with a few new features:

* Responsive design
* Portfolio page for your projects
* Tags compatibility
* Bootstrap : [Get Bootstrap](http://getbootstrap.com/)
* Search feature : [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search)
* Math Rendering : [KateX](https://github.com/Khan/KaTeX)
* Seo Tags : [Jekyll-seo-tag](https://help.github.com/articles/search-engine-optimization-for-github-pages/)
* Syntax Highlighting: Easily customisable [Base16](https://github.com/chriskempson/base16)
* Free of rights images from [pexels](https://www.pexels.com/)

> [Demo](https://sylhare.github.io/Type-on-Strap/)
 
[![Default Type on Strap blog](https://github.com/Sylhare/Type-on-Strap/blob/master/screenshot.png?raw=true)](https://sylhare.github.io/Type-on-Strap/)

## Table of Contents

1. [Usage](https://github.com/Sylhare/Type-on-Strap#Usage)
2. [Structure](https://github.com/Sylhare/Type-on-Strap#structure)
3. [Configure Type on Strap](https://github.com/Sylhare/Type-on-Strap#configure-type-on-strap)
4. [Layout](https://github.com/Sylhare/Type-on-Strap#layout)
5. [Feature pages](https://github.com/Sylhare/Type-on-Strap#feature-pages)
6. [Template as a Gem](https://github.com/Sylhare/Type-on-Strap#Template-as-a-Gem)
7. [License](https://github.com/Sylhare/Type-on-Strap#license)

## Usage

1. Fork and clone the [Type on Strap repo](https://github.com/sylhare/Type-On-Strap): `git clone https://github.com/Sylhare/Type-on-Strap.git`
2. Install [Jekyll](https://jekyllrb.com/docs/installation/): `gem install jekyll`, check [#1](https://github.com/Sylhare/Type-on-Strap/issues/1) if you have a problem.
3. Install the theme's dependencies: `bundle install`
4. Customize the theme
	- Github Page: [update `_config.yml`](https://github.com/Sylhare/Type-on-Strap#site-configuration)
5. Run the Jekyll server: `jekyll serve`

## Structure

Here are the main files of the template

```bash
jekyll-theme-basically-basic
├── _draft	               # To store your drafts, they won't be published on your site
├── _includes	               # theme includes
├── _layouts                   # theme layouts (see below for details)
├── _portfolio	               # collection of article to be populated in the portfolio page
├── _posts                     # Blog posts
├── _sass                      # Sass partials 
├── assets
|  ├── js	               # theme javascript, Katex, jquery, bootstrap, jekyll search, 
|  ├── css                     # isolated Bootstrap, font-awesome, katex and main css
|  ├── fonts		       # Font-Awesome, Glyphicon, and other fonts
|  └── img		       # Images used for the template
├── pages
|   ├── 404.md		       # To be displayed when url is wrong
|   ├── about.md               # About example page
|   ├── gallery.md              # Gallery page for your photos
|   ├── portfolio.md	         # Portfolio page for your projects
|   ├── search.html	       # Search page
|   └── search.json            # Specify the search target (page, post, collection)
├── _config.yml                # sample configuration
└── index.html                 # sample home page (blog page paginated)
```
	
## Configure Type on Strap

Open `_config.yml` in a text editor to change most of the blog's settings.

If a variable in this document is marked as "optional", disable the feature by removing all text from the variable. 


### Site configuration
Configure Jekyll as your own blog or with a subpath in in `_config.yml`:

Jekyll website *without* a subpath (such as a GitHub Pages website for a given username):

```yml
  baseurl: ""
  url: "https://username.github.io"
```

Jekyll website *with* subpath (like the Type on Strap [demo](https://sylhare.github.io/Type-on-Strap/) page):

```yml
  baseurl: "/sub-directory"
  url: "https://username.github.io/"
```

Please configure this  before using the theme.

### Meta and Branding

Meta variables hold basic information about your Jekyll site which will be used throughout the site and as meta properties for search engines, browsers, and the site's RSS feed.

Change these variables in `_config.yml`:

```yml
  theme_settings:
    title: My Jekyll Blog                 # Name of website
    avatar: assets/img/triangular.svg     # Path of avatar image, to be displayed in the theme's header
    gravatar: f98....6bfc                 # MD5 hash of your email address
    description: My blog posts            # Short description, primarily used by search engines
```

### Customizing text

#### Footer and Header's text

Customize your site header/footer with these variables in `_config.yml`:

```yml
  theme_settings:
    header_text: Welcome to my Jekyll blog
    header_text_feature_image: assets/img/sample3.png
    footer_text: Copyright 2017
```

#### Localisation string

Change localization string variables in `_config.yml`.

English text used in the theme has been grouped  so you can quickly translate the theme or change labels to suit your needs.

```yml
  theme_settings:
     str_follow_on: "Follow on"
     str_rss_follow: "Follow RSS feed"
     str_email: "Email"
     str_next_post: "Next post"
     str_previous_post: "Previous post"
     str_next_page: "Next"
     str_previous_page: "Prev"
     str_continue_reading: "Continue reading"
     str_javascript_required_disqus: "Please enable JavaScript to view comments."
```


### Other features

Jekyll works with [liquid](https://shopify.github.io/liquid/) tags usually represented by:

```
{{ liquid.tag | filter }}
```

These are useful to render your jekyll files. You can learn more about them on [shopify's doc](https://help.shopify.com/themes/liquid/basics)

### Footer's icons

Display the site's icon from [Font Awesome](https://fortawesome.github.io/Font-Awesome/) in the footer. All icon variables should be your username enclosed in quotes (e.g. "username") in `_config.yml`, except for the following variables:

```yml
  theme_settings:
     rss: true                                                   # Make sure you created a feed.xml with feed.xml layout
     email_address: type@example.com
     linkedin: https://www.linkedin.com/in/FirstLast
     stack_exchange: https://stackoverflow.com/users/0000/first-last
```

### Comments (via Disqus)

Optionally, if you have a [Disqus](https://disqus.com/) account, you can show a 
comments section below each post.

To enable Disqus comments, add your [Disqus shortname](https://help.disqus.com/customer/portal/articles/466208) to your project's `_config.yml` file:

```yml
  theme_settings:
     disqus_shortname: my_disqus_shortname
```

### Google Analytics

To enable Google Analytics, add your [tracking ID](https://support.google.com/analytics/answer/1032385) 
to `_config.yml` like so:

```yml
  theme_settings:
     google_analytics: UA-NNNNNNNN-N
```

### Math typesetting

When KateX is set in `_config.yml`:

```yml
  theme_settings:
     katex: true # to Enable it
```

You can then wrap math expressions with `$$` signs in your posts and make sure you have set the `katex` variable in `_config.yml` to `true` for math typesetting.

For inline math typesetting, type your math expression on the *same line* as your content. For example:

```latex
Type math within a sentence $$2x^2 + x + c$$ to display inline
```

For display math typesetting, type your math expression on a *new line*. For example:

```latex
$$
  \bar{y} = {1 \over n} \sum_{i = 1}^{n}y_i
$$
```

### Post excerpt

The [excerpt](https://jekyllrb.com/docs/posts/#post-excerpts) are the first lines of an article that is display on the blog page. The length of the excerpt has a default of around `250` characters and can be manually set in the post using:
```yml
---
layout: post
title: Sample Page
excerpt_separator: <!--more-->
---

some text in the excerpt
<!--more-->
... rest of the text not shown in the excerpt ...
```

The html is stripped out of the excerpt so it only display text.

## Layout
Please refer to the [Jekyll docs for writing posts](https://jekyllrb.com/docs/posts/). Non-standard features are documented below.

### Layout: Post

This are the basic features you can use with the  `post` layout.

```yml
---
layout: post
title: Hello World                                # Title of the page
feature-img: "assets/img/sample.png"              # Add a feature-image to the post
thumbnail: "assets/img/thumbnail/sample-th.png"   # Add a thumbnail image on blog view
bootstrap: true                                   # Add bootstrap to the page
tags: [sample, markdown, html]
---
```

With `thumbnail`, you can add a smaller image than the `feature-img`. If you don't want/have a thumbnail you can still use the same image as the feature one.

So the **bootstrap** is not mandatory and is only usefull if you want to add bootstrapped content in your page. It will respect the page and theme layout, mind the padding on the sides.

### Layout: Page

The page layout have a bit more features explained here.

```yml
---
layout: page
title: "About" 
subtitle: "This is a subtitle"   
feature-img: "assets/img/sample.png" 
permalink: /about.html               # Set a permalink your your page
hide: true                           # Prevent the page title to appear in the navbar
tags: [sample, markdown, html]
---
```

The hide only hides your page from the navigation bar, it is however still generated and can be access through its link. Use the `_draft` folder to keep files from being generated on your site.

### Layout: Default

This layout includes the head, navigation bar and footer around your content.

## Feature pages

All feature pages besides the "home" one are stored in the `page` folder, they will appear in the navigation bar unless you set `Hide: true` in the front matter. 

Here are the documentation for the other feature pages that can be added through `_config.yml`.

### Home

This page is the used as the home page of the template (in the `index.html`). It displays the list of article in `_posts`.
You can use this layout in another page (adding a title to it will make it appear in the navigation bar).

### Portfolio

Portfolio is a feature page that will take all the markdown/html files in the `_portfolio` folder to create a 3-columns image portfolio matrix.

To use the portfolio, simply create a `portfolio.md` with this information inside:
```yml
--- 
layout: page
title : Portfolio 
---

{% include portfolio.html %}
```

### Gallery

You can create a gallery using [Masonry JS](https://masonry.desandro.com/) which will placing the pictures in optimal position based on available vertical space. You need to specify the `gallery_path` which will be used to find the pictures to render. It will take all of the picture under that directory. Then use the `include` to add it in your page. 

```
---
layout: page
title: Gallery
gallery: "assets/img/pexels"
---

{% include gallery.html gallery_path=page.gallery %}
```


### Search

The search feature is based on [Simple-Jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search) there is a `search.json` file that will create a list of all of the site posts, pages and portfolios. 

Then there's a `search.js` displaying the formatted results entered in the `search.html` page.


The search page can be enable/disable in the navigation bar through the `_config.yml` via:
```yml
special_page:
    search: 
      icon: "search"
      enabled: true
```

### Tags

Tags should be placed between `[]` in your post metadata. Separate each tag with a comma. Tags are recommended for posts and portfolio items.

For example:

```yml
---
layout: post
title: Markdown and HTML
tags: [sample, markdown, html]
---
```

> Tags are case sensitive `Tag_nAme` ≠ `tag_name`

All the tags will be listed in `tags.html` with a link toward the pages or posts.
The tags page can be enable/disable in the navigation bar through the `_config.yml` via:

```yml
special_page:
    tags: 
      icon: "tags"
      enabled: true
```

## Template as a Gem

You can use Type-on-strap as a [gem](https://rubygems.org/gems/type-on-strap). Checkout an example in the [gem-demo branch](https://github.com/Sylhare/Type-on-Strap/tree/gem-demo).
To make the feature pages available in from the gem I created them as layouts that can be invoked in the pages folder.

So if you're using the template as a theme, Make sure you have:
  - A `index.html` file
  - The right `_config.yml` with the theme setting such as `theme: type-on-strap` uncommented
  - The feature page included. (ex: as it is already in `pages`)
  - Some content ready in `_posts` and `_portfolio` to be displayed

Now you can use any theme gem with github pages : [29/11/2017 Github Pages Broadcast](https://github.com/blog/2464-use-any-theme-with-github-pages)

## License

[The MIT License (MIT)](https://raw.githubusercontent.com/Sylhare/Type-on-Strap/master/LICENSE)
=======
# Universal Theme for Hugo

[![Build Status](https://travis-ci.org/devcows/hugo-universal-theme.svg?branch=master)](https://travis-ci.org/devcows/hugo-universal-theme)
[![Code Climate](https://codeclimate.com/github/devcows/hugo-universal-theme/badges/gpa.svg)](https://codeclimate.com/github/devcows/hugo-universal-theme)

Universal is a clean and stylish website template built with Bootstrap. It stands out with its clean design and elegant typography.

This Hugo theme was ported from [Bootstrapious](http://bootstrapious.com/p/universal-business-e-commerce-template) for training and fun. It has a very nice and customizable landing page, a comments system by Disqus, site search by Google, contact forms by Formspree, Google Analytics, and optional widgets for the sidebar.

![screenshot](https://raw.githubusercontent.com/devcows/hugo-universal-theme/master/images/screenshot.png)


## Table of Contents

* [Features](#features)
* [Installation](#installation)
* [Configuration](#configuration)
  * [Style](#style)
  * [Comments](#comments)
  * [Google Analytics](#google-analytics)
  * [Contact form](#contact-form)
  * [Menu](#menu)
  * [Sidebar widgets](#sidebar-widgets)
  * [Blog post thumbnails](#blog-post-thumbnails)
  * [Top bar](#top-bar)
  * [Landing page](#landing-page)
    * [Carousel](#carousel)
    * [Features](#features)
    * [Testimonials](#testimonials)
    * [See more](#see-more)
    * [Clients](#clients)
    * [Recent posts](#recent-posts)
    * [Meta tags](#meta-tags)
* [Usage](#usage)
* [Contributing](#contributing)
* [License](#license)
* [Thanks](#thanks)

## Features

* Responsive design
* Customizable landing page
  * Carousel
  * Testimonials
  * Features
  * Customers
  * Recent posts
* Contact form by Formspree
* Google search
* Disqus comments
* Google Analytics


## Installation

Go to the directory where you have your Hugo site and run:

```
$ mkdir themes
$ cd themes
$ git clone https://github.com/devcows/hugo-universal-theme
```

For more information read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo.


## Configuration

After installing the Universal theme successfully, we recommend you to take a look at the [exampleSite](//github.com/devcows/hugo-universal-theme/tree/master/exampleSite) directory. You will find a working Hugo site configured with the Universal theme that you can use as a starting point for your site.

First, let's take a look at the [config.toml](//github.com/devcows/hugo-universal-theme/tree/master/exampleSite/config.toml). It will be useful to learn how to customize your site. Feel free to play around with the settings.


### Language

Available translations are in the `/i18n` directory. You can configure the language modifying the following key.

```toml
defaultContentLanguage = "en"
```

### Style

You can change the color of the theme by modifying the following key.

```toml
style = "default"
```

Available options are: `default` (light-blue), `blue`, `green`, `marsala`, `pink`, `red`, `turquoise`, `violet`.


### Comments

The optional comments system is powered by [Disqus](https://disqus.com). If you want to enable comments, create an account in Disqus and write down your shortname.

```toml
disqusShortname = "devcows"
```

You can disable the comments system by leaving the `disqusShortname` empty.


### Google Analytics

You can optionally enable Google Analytics. Type your tracking code in the ``.

```toml
googleAnalytics = "UA-XXXXX-X"
```

Leave the `googleAnalytics` key empty to disable it.


### Contact form

You can optionally create a contact page and include a contact form.

A contact page is just like a regular Hugo page. But it must include the field `id` with the value `contact`.

```toml
+++
title = "Contact"
id = "contact"
+++
```

You can optionally add the google maps widget defining latitude and longitude in the section `params` at `config.toml`. On pin click  opens Google Maps directions with the coordinates. Additionally you can define direction if you want to have a different target set for directions or the google maps entry of your company.:

```yaml
[params]
    ...
    latitude = "-12.043333"
    longitude = "-77.028333"
    direction = "Desamparados Station, Distrito de Lima 15001, Peru"
```

Since this Hugo sites are static, the contact form uses [Formspree](https://formspree.io/) as a proxy. The form makes a POST request to their servers to send the actual email. Visitors can send up to a 1000 emails each month for free.

To enable the form in the contact page, just type your Formspree email in the `config.toml` file.

```yaml
[params]
email = "your@email.com"
```

### Menu

You can also define the menu items that will appear in the top bar. Edit the `[[params.menu]]` entries to create your menu.

```toml
[[params.menu]]
    name = "Contact"
    url  = "/contact"
    weight = 4
```

The `weight` parameter will determine the order of the menu entries.


### Sidebar widgets

You can enable/disable the sidebar widgets that will be shown in the blog section. The following widgets are currently available:

* Search bar (powered by Google)
* Categories list
* Tags list

You can enable/disable them under `params.widgets`.

```toml
[params.widgets]
    search = true
    categories = true
    tags = true
```

### Top bar

The top bar is typically used to provide contact information and social links. It is disabled by default, and it can be enabled inside the `params.topbar` settings.

```toml
[params.topbar]
    enable = true
    text = "<p>Contact us on +420 777 555 333 or hello@universal.com.</p>"
```

The `text` shows up on the left side and accepts HTML.

The social links on the right side are configured as a top-level menu.

```toml
[[menu.topbar]]
    weight = 1
    name = "GitHub"
    url = "https://github.com/devcows/hugo-universal-theme"
    pre = "<i class='fa fa-2x fa-github'></i>"

[[menu.topbar]]
    weight = 2
    name = "Facebook"
    url = "http://facebook.com"
    pre = "<i class='fa fa-2x fa-facebook'></i>"
```

### Blog post thumbnails

After creating a new post you can define a banner by entering the relative path to the image.

```toml
banner = "img/banners/banner-4.jpg"
```

It must contain a relative path to the banner inside the `static` directory.


### Landing page

The landing page consists in many sections that can be activated and configured individually. Let's go through all sections from top to bottom.

#### Carousel

The carousel content is configured in the data directory.

```
data
└── carousel
    ├── customizable.yaml
    ├── design.yaml
    ├── features.yaml
    └── multipurpose.yaml
```

Each carousel entry is represented as a YAML file inside `data/carousel`. Let's see the `customizable.yaml` as an example of a carousel entry.

```yaml
weight: 4
title: "Easy to customize"
description: >
  <ul class="list-style-none">
    <li>7 preprepared colour variations.</li>
    <li>Easily to change fonts</li>
  </ul>
image: "img/carousel/template-easy-code.png"
```

The `weight` field determines the position of the entry. `title` is a text-only field. The `description` field accepts HTML code. And the `image` must contain the relative path to the image inside the `static` directory.

Once the carousel is configured, it must be explicitly enabled in the `config.toml` file.

```toml
[params.carousel]
    enable = true
```

#### Features

Features are also defined in the `data` directory just like the carousel.

```
data
└── features
    ├── consulting.yaml
    ├── email.yaml
    ├── print.yaml
    ├── seo.yaml
    ├── uiux.yaml
    └── webdesign.yaml
```

A feature file looks like this.

```yaml
weight: 4
name: "Consulting"
icon: "fa fa-lightbulb-o"
description: "Fifth abundantly made Give sixth hath. Cattle creature i be don't them behold green moved fowl Moved life us beast good yielding. Have bring."
```

The `icon` field is the CSS class of an icon. In this example we have used icons powered by [FontAwesome](http://fontawesome.io/icons/).

Once you have completed your features, enable them in the `config.toml` file.

```toml
[params.features]
    enable = true
```

#### Testimonials

Testimonials are defined in the `data` directory.

```
data
└── testimonials
    ├── 1.yaml
    ├── 2.yaml
    ├── 3.yaml
    ├── 4.yaml
    └── 5.yaml
```

You can add as many testimonials files as you want. Be sure you fill in all fields as in the following example.

```yaml
text: "One morning, when Gregor Samsa woke from troubled dreams, he found himself transformed in his bed into a horrible vermin. He lay on his armour-like back, and if he lifted his head a little he could see his brown belly, slightly domed and divided by arches into stiff sections."
name: "John McIntyre"
position: "CEO, TransTech"
avatar: "img/testimonials/person-1.jpg"
```

Then, enable it in the configuration file and add a title and subtitle.

```toml
[params.testimonials]
    enable = true
    title = "Testimonials"
    subtitle = "We have worked with many clients and we always like to hear they come out from the cooperation happy and satisfied. Have a look what our clients said about us."
```


#### See more

This section is used to provide a link to another place. It can be an external site, or a page or post within your Hugo site.

You can enable it in the configuration file.

```toml
[params.see_more]
    enable = true
    icon = "fa fa-file-code-o"
    title = "Do you want to see more?"
    subtitle = "We have prepared for you more than 40 different HTML pages, including 5 variations of homepage."
    link_url = "http://your-site.com/more"
    link_text = "Check other homepages"
```


#### Clients

The clients section is used to show a list of logos of companies you have collaborated with. The clients are defined in the `data` directory as YAML files.

```
data
└── clients
    ├── 1.yaml
    ├── 2.yaml
    ├── 3.yaml
    ├── 4.yaml
    ├── 5.yaml
    └── 6.yaml
```

Each client file contains the following information.

```yaml
name: "customer-1"
image: "img/clients/customer-1.png"
url: "http://www.customer-1.com"
```

The `name` of the client. `image` is a relative path to the logo inside the `static` directory. And `url` is an optional field in case you want to link the logo to the client's website.

Then, you can enable the section in the configuration file.

```toml
[params.clients]
    enable = true
    title = "Our Partners"
    subtitle = "We have proudly collaborated with the following companies."
```

#### Recent posts

The recent posts sections shows the four latest published blog posts, with their featured image and a summary.

You can enable it in the configuration file.

```toml
[params.recent_posts]
    enable = true
    title = "From our blog"
    subtitle = "Pellen
```


#### Meta tags

`Description` and `Keywords` meta tags are available and can be customized.
You can set default values for all pages in the `config.toml` file as below.

```toml
[params]
    defaultKeywords = ["devcows", "hugo", "go"]
    defaultDescription = "Site template made by Devcows using Hugo"
```

The result in HTML will be the following.

```html
<meta name="keywords" content="devcows, hugo, go">
<meta name="description" content="Site template made by Devcows using Hugo">
```

You can also override the default values from the `config.toml` by setting the `description` and `keywords` in the individual pages meta data.
See the `faq.md` file in the `exampleSite` directory for an example.

```yaml
+++
title = "FAQ"
description = "Frequently asked questions"
keywords = ["FAQ","How do I","questions","what if"]
+++
```


## Usage

In order to see your site in action, run Hugo's built-in local server.

```
$ hugo server -w
```

Now enter [`localhost:1313`](http://localhost:1313) in the address bar of your browser.

For more information check out the official [Hugo documentation](http://gohugo.io/overview/usage/).


## Contributing

Did you found a bug or got an idea for a new feature? Feel free to use the [issue tracker](https://github.com/devcows/hugo-universal-theme/issues) to let us know. Or make directly a [pull request](https://github.com/devcows/hugo-universal-theme/pulls).


## License

This port is released under the MIT License. Check the [original theme license](http://bootstrapious.com/p/universal-business-e-commerce-template) for additional licensing information.


## Thanks

Thanks to [Steve Francia](https://github.com/spf13) for creating Hugo and the awesome community around the project. And also thanks to [Bootstrapious](http://bootstrapious.com/) for creating this awesome theme.
>>>>>>> ffccfecfe17a81060fb39ae7a2d432891dc77258
