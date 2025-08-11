# frozen_string_literal: true
source "https://rubygems.org"

# Jekyll & Chirpy 테마 (theme: jekyll-theme-chirpy 사용)
gem "jekyll", "~> 4.3"
gem "jekyll-theme-chirpy"

# 플러그인 (config.yml의 paginate 사용 중이므로 포함)
gem "jekyll-sitemap"
gem "jekyll-feed"
gem "jekyll-paginate"

# 로컬 서버에 필요할 수 있음
gem "webrick"

# 테스트(선택)
group :test do
  gem "html-proofer", "~> 5.0"
end

# Windows 전용 보조 젬
platforms :windows do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
  gem "wdm", "~> 0.2.0"
end