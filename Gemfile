source "https://rubygems.org"

gem "jekyll", "~> 4.2.0"
gem 'wdm', '>= 0.1.0' if Gem.win_platform?
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
end
gem "webrick", "~> 1.7"
# Needed because Ruby ≥ 3.4 drops these from stdlib
gem "csv",    "~> 3.2"
gem "logger", "~> 1.6"   # not strictly required yet, silences the warning
gem "base64",  "~> 0.2"   # NEW → fixes the SafeYAML crash
gem "bigdecimal","~> 3.1"   # ← NEW