source "https://rubygems.org"

gem "jekyll", "~> 4.3"

# Pin jekyll-sass-converter to the 2.x line (libsass) rather than the
# 3.x line (Dart Sass). Our theme uses the indented .sass syntax with
# calc() expressions like `calc(40% - 17em)` that Dart Sass parses more
# strictly and rejects — libsass is happy with them, and this repo
# doesn't need any Dart-specific SASS features. GitHub Pages' legacy
# Jekyll build also uses jekyll-sass-converter 2.x, so this keeps local
# builds and the deployed site consistent.
gem "jekyll-sass-converter", "~> 2.0"

# Gems that used to be part of Ruby's stdlib but were removed from the
# default gems in Ruby 3.4+. Jekyll still requires some of them, so we
# pin them explicitly here to keep the site buildable on modern Ruby.
gem "csv"
gem "base64"
gem "bigdecimal"
# webrick is what `jekyll serve` uses under the hood; not shipped by
# default since Ruby 3.0.
gem "webrick"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
end
