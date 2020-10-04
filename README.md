# rda.ch

This is the source code of my personal blog on [rda.ch](https://rda.ch), cloned from [Fredrik Averpil's blog](https://fredrikaverpil.github.io), orginally based on [poole/hyde](https://github.com/poole/hyde).

## Run website locally

Full instructions [here](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/#step-1-create-a-local-repository-for-your-jekyll-site).

### Dependencies

```bash
apt install ruby2.5 bundler ruby-full build-essential zlib1g-dev
```

### Set up ruby and install

```bash
cd <repo>
echo "source 'https://rubygems.org'" > Gemfile
echo "gem 'github-pages', group: :jekyll_plugins" >> Gemfile
source rubyenv.sh
bundle install
```

### Serve website

```bash
bundle exec jekyll serve
```

### Visit website

- Visit website at http://localhost:4000
- Cancel serving with ctrl+c

### Build static website

```bash
bundle exec jekyll build
```
