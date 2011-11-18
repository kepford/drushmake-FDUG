!SLIDE

# Drush Make & Other Awesomeness #

!SLIDE bullets incremental transition=fade

# What You'll Learn #

* How to Use Drush Make
* Quick Power Tips
* My Workflow

!SLIDE bullets incremental transition=fade

# Drush Make Magic #

* Put modules where you want!
* Apply Patches!
* Download Third party libraries!
* Download using Version Control!



!SLIDE bullets incremental transition=fade

# Installation #

* Is Drush Installed?
* Download [Drush Make](http://drupal.org/project/drush_make)
* Read the [INSTALL.txt](http://drupalcode.org/project/drush_make.git/blob_plain/refs/heads/6.x-2.x:/INSTALL.txt)
* Test: $ drush make -h

!SLIDE bullets incremental transition=fade

# Make A Make File #

    drush generate-makefile example.make

Generate a makefile with ALL projects versioned

!SLIDE bullets incremental transition=fade

# Make A Drupal Site #

    drush make example.make

!SLIDE bullets incremental transition=fade

# Get Repos with Make #

    drush make --working-copy
Where possible, retrieve a working copy of projects from their repos

!SLIDE bullets incremental transition=fade

# Put modules where you want! #
    projects[flag][subdir] = contrib
    projects[flag][version] = 2.0-beta5
    ; DEVELOPMENT
    projects[devel][subdir] = "dev"

!SLIDE bullets incremental transition=fade

# Apply Patches! #

    ; http://drupal.org/node/968826#comment-3863422
    projects[features][patch][] = "http://drupal.org/files/issues/968826-features-menu-uuid.patch"


!SLIDE bullets incremental transition=fade

# Third party libraries! #

    ; jQuery UI
    libraries[jquery_ui][download][type] = "get"
    libraries[jquery_ui][destination] = "modules/contrib/jquery_ui"
    libraries[jquery_ui][download][url] = "http://jquery-ui.googlecode.com/files/jquery-ui-1.7.3.zip"
    libraries[jquery_ui][directory_name] = "jquery.ui"

!SLIDE bullets incremental transition=fade

# Get Version Controlled Repos #

    projects[ccpc2011][type] = "theme"
    projects[ccpc2011][download][type] = "git"
    projects[ccpc2011][download][url] = "http://mydomain/mytheme.git"
    projects[ccpc2011][download][branch] = "dev"

!SLIDE bullets incremental transition=fade

# Quick Tips #

!SLIDE

# Drush --help #
    drush command --help

!SLIDE

# DB Dump #
    $ drush sql-dump > database-backup-$(date +%Y-%m-%d-%H.%M.%S).sql

!SLIDE

# Import a database #
    drush sqlc < database_file.sql

!SLIDE

# Drush Password Reset URL #
    drush php-eval 'echo user_pass_reset_url(user_load(1));'

!SLIDE

# Take Site Offline #

    drush vset --always-set site_offline 1

!SLIDE bullets incremental transition=fade

# My Workflow #

* Grab an old make file
* Update it with modules/themes/libs
* Add make file to my Git repo
* drush make myfile.build

!SLIDE bullets incremental transition=fade

# Site Build #

* Config site
* Add new modules to make file
* Commit make file changes and push
* Production:$ drush make myfile.build

!SLIDE

# Resources #

* Get the code [drush_make](http://drupal.org/project/drush_make)
* Drush FAQ's and Documentation [drush.ws](http://drush.ws/)
* Generate a make file [drushmake.me](http://drushmake.me/)