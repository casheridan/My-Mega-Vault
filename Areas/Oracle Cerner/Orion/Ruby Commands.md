```
bundle [install (first time)/update (already )]
npm install
rspec
bundle exec rake assets:precompile
npm run build:development
bundle exec rails s
```

terra-rails-view_models: eventually update this

## Install Fixes
---

<u>Install libv8 / fix therubyracer</u>
`CXX=clang++ GYPFLAGS=-Dmac_deployment_target=10.16 gem install libv8 --version '3.16.14.19' -- --with-system-v8`

<u>Install / fix thrift</u>
`gem install thrift -v 0.17.0 -- --with-cppflags="-Wno-compound-token-split-by-macro"`