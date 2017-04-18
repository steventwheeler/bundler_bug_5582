This repository can be used to reproduce [bundler/bundler#5582](https://github.com/bundler/bundler/issues/5582)

# Behavior of v1.14.4 and below:
```
$ bundle --version && bundle update && bundle exec ruby lib/test.rb
Bundler version 1.14.4
Warning: the running version of Bundler (1.14.4) is older than the version that created the lockfile (1.14.6). We suggest you upgrade to the latest version of Bundler by running `gem install bundler`.
Fetching gem metadata from https://rubygems.org/..
Fetching version metadata from https://rubygems.org/.
Resolving dependencies...
Using timeout-extensions 0.1.1
Using bundler 1.14.4
Using timeout 0.0.1
Bundle updated!
lib/test.rb:3:in `<main>': This is a test (Timeout::Error)
```

# Behavior of v1.14.5:
```
$ bundle --version && bundle update && bundle exec ruby lib/test.rb
Bundler version 1.14.5
Warning: the running version of Bundler (1.14.5) is older than the version that created the lockfile (1.14.6). We suggest you upgrade to the latest version of Bundler by running `gem install bundler`.
Fetching gem metadata from https://rubygems.org/..
Fetching version metadata from https://rubygems.org/.
Resolving dependencies...
Using timeout-extensions 0.1.1
Using bundler 1.14.5
Using timeout 0.0.1
Bundle updated!
lib/test.rb:3:in `<main>': uninitialized constant Timeout::Error (NameError)
Did you mean?  KeyError
               IOError
               Errno
```

# Behavior of v1.14.6:
```
$ bundle --version && bundle update && bundle exec ruby lib/test.rb
Bundler version 1.14.6
Fetching gem metadata from https://rubygems.org/..
Fetching version metadata from https://rubygems.org/.
Resolving dependencies...
Using timeout-extensions 0.1.1
Using bundler 1.14.6
Using timeout 0.0.1
Bundle updated!
lib/test.rb:3:in `<main>': uninitialized constant Timeout::Error (NameError)
Did you mean?  KeyError
               IOError
               Errno
```
