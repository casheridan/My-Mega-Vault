bundle install
npm install
rspec
bundle exec rails s - hosts on port 9292

terra-rails-view_models: eventually update this

<u>Install libv8 / fix therubyracer</u>
CXX=clang++ GYPFLAGS=-Dmac_deployment_target=10.15 gem install libv8 --version 3.16.14.19

<u>Install / fix thrift</u>
gem install thrift -v 0.17.0 -- --with-cppflags="-Wno-compound-token-split-by-macro"