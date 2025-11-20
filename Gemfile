# frozen_string_literal: true

source "https://rubygems.org"

# Core Jekyll (version is controlled via Appraisal matrix)
gem "jekyll"

# Jekyll plugins
group :jekyll_plugins do
  gem "jekyll-remote-theme"
  gem "jekyll-paginate"
  gem "jekyll-sitemap"
end

# Needed for `jekyll serve` with Ruby 3+
gem "webrick", "~> 1.7"

# Windows and JRuby do not include zoneinfo files
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# For CI Jekyll version matrix
group :development do
  gem "appraisal"
end
