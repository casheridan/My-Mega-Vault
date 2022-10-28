# Point Gem to Local Directory
What does this do? - This method will allow you to make code changes on an engine and see them almost immediately without running a bundle install on a server. It also allows work on two gems with one as a dependency of the other without performing a bundle install or pushing to a GitHub repo each time.

Setup:
1. In a terminal change the current working directory to the directory of the dependency/engine (d/e) gem
2. Run this command in the terminal
- `bundle config local.GEM_NAME /path/to/local/git/repository`
	- This sets your bundler configuration to point a variable to the directory of the d/e gem
3. Navigate in an IDE to the consuming/server (c/s) gem
4. Open the Gemfile
5. Find the d/e gem definition
6. Replace the definition line with
- `gem 'GEM_NAME', :git 'GEM_NAME/GEM_NAME', branch: 'master'`
7. Run a `bundle install`

The gem should now be using the local version of the gem and now any changes made to the d/e will automatically be used. If you are running the c/s gem and make a change you will need to restart it and the changes should show/come into effect once restarted.

Reminder: Be sure to revert the changes or use the new d/e gem in the server's Gemfile before pushing any changes to the server's remote repo.