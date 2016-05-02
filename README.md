# [Bedrock](https://code.thegeeks.rocks/bedrock/)

[![Build Status](https://travis-ci.org/roots/bedrock.svg)](https://travis-ci.org/roots/bedrock)

This is a fork from [Bedrock](https://roots.io/bedrock/) with some little improvements from me.

Bedrock is a modern WordPress stack that helps you get started with the best development tools and project structure.

Much of the philosophy behind Bedrock is inspired by the [Twelve-Factor App](http://12factor.net/) methodology including the [WordPress specific version](https://roots.io/twelve-factor-wordpress/).

## Features

* Better folder structure
* Dependency management with [Composer](http://getcomposer.org)
* Easy WordPress configuration with environment specific files
* Environment variables with [Dotenv](https://github.com/vlucas/phpdotenv)
* Autoloader for mu-plugins (use regular plugins as mu-plugins)
* Enhanced security (separated web root and secure passwords with [wp-password-bcrypt](https://github.com/roots/wp-password-bcrypt))

See a complete working example in the [jscarton's geekspress repo](https://github.com/jscarton/geekspress).

## Requirements

* PHP >= 5.5
* Composer - [Install](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)

## Installation

1. Clone the git repo - `git clone https://github.com/roots/bedrock.git`
2. Run `composer install`
3. Copy `.env.example` to `.env` and update environment variables:
  * `DB_NAME` - Database name
  * `DB_USER` - Database user
  * `DB_PASSWORD` - Database password
  * `DB_HOST` - Database host
  * `WP_ENV` - Set to environment (`development`, `staging`, `production`)
  * `WP_HOME` - Full URL to WordPress home (http://example.com)
  * `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
  * `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT` - Generate with [wp-cli-dotenv-command](https://github.com/aaemnnosttv/wp-cli-dotenv-command) or from the [WordPress Salt Generator](https://api.wordpress.org/secret-key/1.1/salt/)
4. Add theme(s) in `web/app/themes` as you would for a normal WordPress site.
5. Set your site vhost document root to `/path/to/site/web/` (`/path/to/site/current/web/` if using deploys)
6. Access WP admin at `http://example.com/wp/wp-admin`

## Deploys

I use a modified version of [bedrock-capistrano](https://github.com/roots/bedrock-capistrano) which is embeded in this repo so you only have to configure your capistrano environments at config/deploy.rb and config/deploy/* files

Any other deployment method can be used as well with one requirement:

`composer install` must be run as part of the deploy process.

## Documentation

Bedrock original documentation is available at [https://roots.io/bedrock/docs/](https://roots.io/bedrock/docs/).

## Contributing

Contributions are welcome from everyone. Let's do some code together
