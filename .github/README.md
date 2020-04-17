# Liquid Feed Atom
[heading__title]:
  #liquid-feed-atom
  "&#x2B06; Top of ReadMe File"


Liquid layout that builds Atom feeds from Jekyll collections via FrontMatter configurations


## [![Byte size of feed-atom.html][badge__master__feed_atom__source_code]][feed_atom__master__source_code] [![Open Issues][badge__issues__feed_atom]][issues__feed_atom] [![Open Pull Requests][badge__pull_requests__feed_atom]][pull_requests__feed_atom] [![Latest commits][badge__commits__feed_atom__master]][commits__feed_atom__master] [![Feed Atom Demos][badge__demo__feed_atom]][demo__feed_atom]



------


#### Table of Contents


- [:arrow_up: Top of ReadMe File][heading__title]

- [:zap: Quick Start][heading__quick_start]

  - [:memo: Edit Your ReadMe File][heading__your_readme_file]
  - [&#x1F578; Utilize Feed Atom][heading__utilize]
  - [:floppy_disk: Commit and Push][heading__commit_and_push]

- [:card_index: Attribution][heading__attribution]

- [&#x2696; License][heading__license]


------



## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


**Bash Variables**


```Bash
_module_name='feed-atom'
_module_https_url="https://github.com/liquid-utilities/${_module_name}.git"
_module_relative_path="_layouts/modules/${_module_name}"
```


**Bash Submodule Commands**


```Bash
cd "<your-git-project-path>"

git checkout gh-pages
mkdir -vp "_layouts/modules"

git submodule add\
 -b master --name "${_module_name}"\
 "${_module_https_url}" "${_module_relative_path}"
```


### Your ReadMe File
[heading__your_readme_file]:
  #your-readme-file
  "&#x1F578; Suggested additions for your ReadMe.md file so everyone has a good time with submodules"


Suggested additions for your _`ReadMe.md`_ file so everyone has a good time with submodules


```MarkDown
Clone with the following to avoid incomplete downloads


    git clone --recurse-submodules <url-for-your-project>


Update/upgrade submodules via


    git submodule update --init --merge --recursive --remote
```


### Utilize Feed Atom
[heading__utilize]:
  #utilize-feed-atom
  "&#x1F578; How to make use of this submodule within another project"


Each collection directory should contain a `atom.xml` file similar to...


**`_administration/administration.atom`**


```YAML
---
layout: modules/feed-atom/feed-atom
title: Administration
collection_name: administration
collection_home: /administration/
date: 2019-07-21 11:12:13 -0700
content_type: xhtml
permalink: /:collection/:name:output_ext
---
```


> Note, an [Atom feed example][feed_atom__gh_pages__rss_feed] file is available within the [`gh-pages`][feed_atom__gh_pages] branch of this repository.


Each collection _`page`_ should have the following FrontMatter definitions...


```YAML
---
## Layout may be `default`, `post`, or `page` depending upon theme
layout: post

title: Title of Page
date: 2019-07-21 11:42:11 -0300
#date_updated:  ## Optional and formatted like `date` above

description: A description of page content
#excerpt: Or a snippet about this page

## Optional, allows for embedding CSV data within `content` tags
#content_type: 'text/delimited'  ## Defaults to `html`

# Number of seconds till update by client reader is recommended
time_to_live: 1800
---
```


> Note, `excerpt` requires `site.show_excerpts` to be non-`false` and **not** setting a `description` for those pages using `excerpt`s
>
> An example page [raw source][feed_atom__gh_pages__raw_source__something_about_something] is available within the [`gh-pages`][feed_atom__gh_pages] branch of this repository.


Assign `site.url`, either via Jekyll `build`/`serve` command line option or with the following `_config.yml` examples...


**`_config.yml`**


```YAML
url: "http://example.com"
show_excerpts: false
plugins:
  - jekyll-github-metadata
```


> Note, a full example [`_config.yml`][feed_atom__gh_pages__config_yml] file is available within the [`gh-pages`][feed_atom__gh_pages] branch of this repository.


To enable all features please configure the GitHub MetaData plugin...


**`Gemfile`**


```Gemfile
# gem "jekyll", "~> 3.8.5"
gem "github-pages", group: :jekyll_plugins

gem "jekyll-github-metadata"
```


Add links to feed within other layout files where desired...


**`_layouts/collections/home.html`**


```HTML
<!-- ... Other layout stuff above -->
<span>
  <svg class="svg-icon orange">
  <use xlink:href="{{- '/assets/minima-social-icons.svg#rss' | relative_url -}}"></use>
  </svg>
  <a href="{{- '/administration/administration.atom' | relative_url -}}">Atom Feed</a>
</span>
<!-- ... More layout stuff bellow -->
```


### Commit and Push
[heading__commit_and_push]:
  #commit-and-push
  "&#x1F4BE; It may be just this easy..."


```Bash
git add .gitmodules
git add _layouts/feed-atom


## Add any changed files too


git commit -F- <<'EOF'
:heavy_plus_sign: Adds `liquid-utilities/feed-atom#1` submodule



**Additions**


- `.gitmodules`, tracks submodules AKA Git within Git _fanciness_

- `README.md`, updates installation and updating guidance

- `_layouts/feed-atom`, builds Atom feeds via FrontMatter configurations
EOF


git push origin gh-pages
```


**:tada: Excellent :tada:** your site is now ready to begin unitizing code from this repository!


___


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


Resources that where helpful in building this project so far


- [Atom Web Standard - `wikipedia.org`](https://en.wikipedia.org/wiki/Atom_(Web_standard))

- [Atom Validator - `w3.org`](https://validator.w3.org/feed/docs/atom.html)

- [Jekyll RSS feed template - `natelandau.com`](https://natelandau.com/jekyll-rss-feed-template/)

- [RFC4287 - `w3.org`](https://validator.w3.org/feed/docs/rfc4287.html)
- [Draft Nottingham HTTP Cache Channels - `tools.ietf.org`](https://tools.ietf.org/html/draft-nottingham-http-cache-channels-00)


___


## License
[heading__license]:
  #license
  "&#x2696; Legal bits of Open Source software"


Legal bits of Open Source software


```
Feed Atom ReadMe documenting how things like this could be utilized
Copyright (C) 2019  S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation; version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```



[badge__commits__feed_atom__master]:
  https://img.shields.io/github/last-commit/liquid-utilities/feed-atom/master.svg

[commits__feed_atom__master]:
  https://github.com/liquid-utilities/feed-atom/commits/master
  "&#x1F4DD; History of changes on this branch"


[feed_atom__community]:
  https://github.com/liquid-utilities/feed-atom/community
  "&#x1F331; Dedicated to functioning code"


[feed_atom__gh_pages]:
  https://github.com/liquid-utilities/feed-atom/tree/gh-pages
  "Source code examples hosted thanks to GitHub Pages!"


[feed_atom__gh_pages__config_yml]:
  https://github.com/liquid-utilities/feed-atom/blob/gh-pages/_config.yml
  "Example configuration file"

[feed_atom__gh_pages__raw_source__something_about_something]:
  https://raw.githubusercontent.com/liquid-utilities/feed-atom/gh-pages/documentation/_example-collection/something-about-something.markdown
  "Raw source code of example post"

[feed_atom__gh_pages__atom_feed]:
  https://github.com/liquid-utilities/feed-atom/blob/gh-pages/documentation/_example-collection/example-collection.atom
  "Example RSS feed configuration FrontMatter"



[badge__demo__feed_atom]:
  https://img.shields.io/website/https/liquid-utilities.github.io/feed-atom/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[demo__feed_atom]:
  https://liquid-utilities.github.io/feed-atom/index.html
  "&#x1F52C; Check the example collection tests"


[badge__issues__feed_atom]:
  https://img.shields.io/github/issues/liquid-utilities/feed-atom.svg

[issues__feed_atom]:
  https://github.com/liquid-utilities/feed-atom/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."


[badge__pull_requests__feed_atom]:
  https://img.shields.io/github/issues-pr/liquid-utilities/feed-atom.svg

[pull_requests__feed_atom]:
  https://github.com/liquid-utilities/feed-atom/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"


[badge__master__feed_atom__source_code]:
  https://img.shields.io/github/size/liquid-utilities/feed-atom/feed-atom.html.svg?label=feed-atom.html

[feed_atom__master__source_code]:
  https://github.com/liquid-utilities/feed-atom/blob/master/feed-atom.html
  "&#x2328; Project source, one Liquid file of actionable code!"
