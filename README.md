# Guard::Notifier::GitAutoCommit

This gem is for who forgots to commit after tests pass.

When notified from Guard, this gem commits your changes into git with build status.

Example of `git log --oneline` after some works:

    a0f503f success  Jasmine results  56 tests, 0 failures, 0.222 secs.
    792da9c failed  Jasmine results  5 tests, 1 failures, 0.07 secs.
    e762d32 failed  Jasmine results  5 tests, 1 failures, 0.088 secs.
    c503842 failed  Jasmine results  5 tests, 1 failures, 0.073 secs.
    e7ef02f success  Spork  RSpec successfully started

## Installation

Add this line to your application's Gemfile:

    gem 'guard-notifier-git_auto_commit', group: 'development'

And then execute:

    $ bundle

Open your Guardfile, add the following at last.

    require 'guard-notifier-git_auto_commit'
    notification :git_auto_commit

If you want to use this with other notifiers, list them.

    require 'guard-notifier-git_auto_commit'
    notification :git_auto_commit
    notification :notifysend

This generates untidy history.  `git-rebase` is your friend.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
