# Site Audit Development Project

This project provides a development environment for Site Audit and related modules.

Join the development community in Drupal Slack: #site-audit-module

## Usage

First you need to [install Composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

> Note: The instructions below refer to the [global Composer installation](https://getcomposer.org/doc/00-intro.md#globally).
You might need to replace `composer` with `php composer.phar` (or similar)
for your setup.

Next clone this project:

```
git clone git@github.com:SiteAudit/site-audit-development
```

Then composer install the project.

```
composer install
```

Then launch the site using your favorite development tool, or just use `drush run-server` and sqlite3.

If using drush you have to run site install BEFORE running run server.

```
bin/drush site:install --db-url=sqlite://tmp/database.sqlite
bin/drush run:server siteaudit.local.computer:80
```

Or you can use the meta commands `composer site:install` and `composer site:run`

## What does this project do?

* Drupal will be installed in the `web`-directory.
* Modules (packages of type `drupal-module`) will be placed in `web/modules/contrib/`
* Theme (packages of type `drupal-theme`) will be placed in `web/themes/contrib/`
* Profiles (packages of type `drupal-profile`) will be placed in `web/profiles/contrib/`
* Latest version of drush is installed locally for use at `bin/drush`.
* Latest version of DrupalConsole is installed locally for use at `bin/drupal`.
* Creates environment variables based on your .env file. See [.env.example](.env.example).

* Site Audit module is installed to web/modules/contrib/site_audit
* Site Audit Server is installed to web/modules/contrib/site_audit_server


# Development Process

When you clone this project and composer install, the Site Audit and Site Audit Server modules
will be cloned into `/web/modules/contrib` at the main branch, `4.0.x`.

To develop the modules, create an issue fork.

To put the forked module into this composer project, it is easier just to change the git remote than to use composer to alter the repo.

        $ cd /path/to/clone
        $ cd web/modules/contrib/site_audit
        $ git remote set-url origin git@git.drupal.org:YOUR-ISSUE-FORK-URL.git
        $ git fetch
        $ git checkout YOUR-ISSUE-FORK-BRANCH.

And start developing.

