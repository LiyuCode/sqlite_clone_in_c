# Prerequests:
 - Using the commands below to install `rspec`:
   ```
   sudo apt install ruby ruby-bundler -y
   sudo gem install rspec
   rspec --version
   ```
 - Optionally, installing `rebornix.ruby` extension on `VSCode` to highlight '*.rb' files when editing.

Now we are good to go write the test script, `db_spec.rb`.

# Testing:
Run `rspec db_spec.rb` or `rspec db_spec.rb --color --format doc`to test.

Ref `https://relishapp.com/rspec/docs/gettingstarted` for more info.
