---
title: '[ruby on rails] rubocop 導入'
date: 2024-03-03 14:13:03
tags:
---

### Gemfile

```ruby
group :development do
  gem 'rubocop', require: false
  gem 'rubocop-performance', require: false
  gem 'rubocop-rails', require: false
  gem 'rubocop-rspec', require: false
end
```


### 設定ファイル雛形を作成

```sh
bundle exec rubocop --auto-gen-config
```

