# Eleven Theme for Pelican

## Pelican Configuration File
here is a sample Pelican configuration file for a blog site using the theme.
```
AUTHOR = 'Your Name'
SITENAME = 'Your Blog'
SITEURL = ""

THEME = "themes/eleven-pelican-theme"
SUMMARY_MAX_LENGTH = 0
ELEVEN_LOGO="images/logo.png"

PATH = "content"
PAGE_PATHS = ['pages']
ARTICLE_PATHS = ['articles']

TIMEZONE = 'Europe/Rome'

DEFAULT_LANG = 'en'

PLUGINS = [
    'neighbors',
    'minchin.pelican.plugins.summary',
]

# Feed generation is usually not desired when developing
FEED_ALL_ATOM = None
CATEGORY_FEED_ATOM = None
TRANSLATION_FEED_ATOM = None
AUTHOR_FEED_ATOM = None
AUTHOR_FEED_RSS = None

# Blogroll
LINKS = (
    ("Pelican", "https://getpelican.com/"),
    ("Python.org", "https://www.python.org/"),
    ("Jinja2", "https://palletsprojects.com/p/jinja/"),
    ("Page", SITEURL+"/pages/secret.html"),
)

DEFAULT_PAGINATION = False
```

## Pages and Articles
You can create pages and articles in the `content/pages` and `content/articles` directories respectively. 
Pages are typically used for static content that appears on the index directly, while articles are used for posts.

### Example Page (content/pages/first-page.md)
Pages require a title, layout and order. 
The only supported layout is `block`.
The `Order` field is used to order the pages on the index page.
If the `Order` field is `hidden`, the page will not be shown on the index page.
```
Title: This is the second block
Layout: block
Order: 1

This is the content of my first block.
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus lacinia odio vitae vestibulum.
Cras venenatis euismod malesuada.
<!-- PELICAN_END_SUMMARY -->
Here is some more text to make this block longer and see how it looks in the layout.
```
Using PELICAN_END_SUMMARY you can define how much of the page content is shown on the index page.

### Example Article (content/articles/first-article.md)
Articles require a title, datum and category.
If the category is `posts`, the articles will be listed with the blog posts.
Other categories will be grouped in a separate section under the Category name. 
To order pages inside a category you can use the `Order` metadata field.
```
Title: First Page
Date: 2024-06-01
Category: posts

This is the content of the first page.
```

## Folder Structure
Here is a suggested folder structure for your Pelican blog site:

```
my_blog/
├── content/
│   ├── articles/
│   │   ├── first-article.md
│   │   └── second-article.md
│   ├── pages/
│   │   ├── first-page.md
│   │   └── second-page.md
│   └── images/
│       └── logo.png
├── themes/
│   └── eleven/
├── pelicanconf.py
└── publishconf.py
```
