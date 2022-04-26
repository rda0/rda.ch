---
layout: post
title: 'Create a jekyll site'
tags: [linux,jekyll,bash]
---

![{{ site.name }} logo]({{ site.baseurl }}/blog/assets/{{ site.logo }})

This guide shows how to create this site.

<!--more-->

## Installation

Install the required dependencies to run `ruby` and build `jekyll` (Debian/Ubuntu):

```bash
apt install git ruby bundler ruby-full build-essential zlib1g-dev
```

Set up ruby environment and install jekyll:

```bash
git clone https://github.com/rda0/rda.ch.git
cd rda.ch
echo "source 'https://rubygems.org'" > Gemfile
echo "gem 'github-pages', group: :jekyll_plugins" >> Gemfile
export GEM_HOME="${HOME}/gems"
export PATH="${HOME}/gems/bin:${PATH}"
gem install bundler
bundle install
```

## Configuration

Edit `_config.yml` and start a local development server:

```bash
bundle exec jekyll clean
bundle exec jekyll serve
```

- Visit website at [http://localhost:4000](http://localhost:4000)
- Cancel serving with ctrl+c

## Build the site

```bash
bundle exec jekyll clean
bundle exec jekyll build
```

This will build the static site content at `_site/`.
