# DP Changelog

## Version 1.4.1 -- May 10th, 2017

* Fix bug with `dp version` when using git style deploy mode.

## Version 1.4.0 -- April 30th, 2017

* Add new deployment style, `git`, that copies across the whole git repository.
* Add support for `DEPLOY_MODE` to select between new `git` style and old `dir`
  style.

## Version 1.3.1 -- February 22nd, 2017

* Fix bug in `old` and `old:clean` commands detecting current deploy.
* Allow user to deploy a git tag.

## Version 1.3.0 -- February 11th, 2017

* Add support for `old`, `old:set`, `old:clean` commands.

## Version 1.2.2 -- February 6th, 2017

* Fix bug in process management, we track the run script life-time rather than
  the process it launched.

## Version 1.2.1 -- February 6th, 2017

* Add `ssh` command.
* Better error messages when starting an app.

## Version 1.2.0 -- February 5th, 2017

* Fix bug with handling of stdin/stderr.
* Add the `envs` command.

## Version 1.1.0 -- May 19th, 2016

* Add support for log rotation.
* Add 'auto:on', 'auto:off' commands.
* Improve documentation.

## Version 1.0.1 -- April 5th, 2016

* Avoid use of bash 4.0 syntax `;&` for switch fall-through.

## Version 1.0.0 -- Jan 27th, 2016

* Updated documentation.
* Added support for git sub-modules.
* Add version command.
* Add --help command.

## Version 0.1.0 -- Feb 27th, 2014

* Initial release.

