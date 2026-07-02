source "https://rubygems.org"

# Standalone Jekyll 4 (no longer the github-pages managed gem). The site is
# built and deployed by GitHub Actions (.github/workflows/deploy.yaml), so we
# are free to use a current Jekyll and custom plugins.
gem "jekyll", "~> 4.3"

# Keep the classic (LibSass) Sass converter. The theme's vendored Susy 2 and
# breakpoint stylesheets rely on `@import` semantics that Dart Sass (the
# converter 3.x default) rejects. Pinning ~> 2.0 lets the existing SCSS compile
# unchanged. Do not bump to 3.x without migrating Susy/breakpoint to `@use`.
gem "jekyll-sass-converter", "~> 2.0"

# Ruby 3+ no longer ships webrick; needed for `jekyll serve` (local preview).
gem "webrick"

# Silence deprecation warnings: bigdecimal leaves default gems in Ruby 3.4,
# and octokit (via jekyll-gist) wants faraday-retry under Faraday 2.
gem "bigdecimal"
gem "faraday-retry"

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-sitemap"
  gem "jekyll-gist"
  gem "jekyll-paginate"
  gem "jekyll-redirect-from"
end

gem "wdm", "~> 0.1.1", platforms: [:mingw, :x64_mingw, :mswin]
