Changelog
=========

1.4.9
-----

Changes:
 - New: drop_test_database, drops the test database
 - New: command_signals, git commit -a -m 'bumped version number' (see docs)
 - Bugfix: runserver_plus, removed empty lines when logging on Python 3


1.4.8
-----

Changes:
 - Bugfix: validators, fix NoWhitespaceValidator __eq__ check


1.4.7
-----

Changes:
 - New: validators.py, NoControlCharactersValidator and NoWhitespaceValidator
 - New: EmailNotificationCommand class, email exceptions from Django Commands
 - Improvement: runserver_plus, enable threading by default and added --nothreading
 - Improvement: runscript, better detection when import error occured in script 
 - Improvement: runscript, use EmailNotificationCommand class
 - Deprecation: deprecated UUIDField since Django 1.8 will have a native version.
 - Removed: completely remove support for automatically finding project root.


1.4.6
-----

Changes:
 - Improvement: sqldiff, fix for dbcolumn not used in few places when generating the sqldiff
 - Fix: sqldiff, backwards compatiblity fix for Django 1.4
 - Fix: ForeignKey Field, handling of __str__ instead of __unicode__ in python3


1.4.5
-----

Changes:
 - New: clear_cache, Clear django cache, useful when testing or deploying
 - Improvement: AutoSlugField, add the possibility to define a custom slugify function
 - Improvement: shell_plus --notebook, add a big warning when the notebook extension is not going to be loaded
 - Improvement: setup.py, add pypy classifier
 - Improvement: readme, add pypy badges
 - Fix: admin_generator, Fixed Python 3 __unicode__/__str__ compatibility


1.4.4
-----

Changes:
 - Fix: admin_generator, fix ImproperlyConfigured exception on Django 1.7
 - Improvement: Remove "requires_model_validation" and "requires_system_checks" in commands which set the default value


1.4.1
-----

Changes:
 - New: shell_plus, Added python-prompt-toolkit integration for shell_plus
 - New: shell_plus, Added --ptipython (PYPython + IPython)
 - Improvement: reset_db, output traceback to easy debugging in case of error
 - Improvement: dumpscript, add --autofield to dumpscript to include autofields in export
 - Improvement: show_urls, Include namespace in URL name
 - Improvement: show_urls, Allow multiple decorators on the show_urls command
 - Improvement: runscript, show script errors with verbosity > 1
 - Fix: jobs, daily_cleanup job use clearsessions for Django 1.5 and later
 - Fix: shell_plus, refactored importing and selecting shells to avoid polluted exception
 - Fix: shell_plus, Fix model loading for sentry


1.4.0
-----

Changes:
 - New admin_generator, can generate a admin.py file from models
 - Improvement: sqldiff, use the same exit codes as diff uses
 - Improvement: sqldiff, add support for unsigned numeric fields
 - Improvement: sqldiff, add NOT NULL support for MySQL
 - Improvement: sqldiff, add proper AUTO_INCREMENT support for MySQL
 - Improvement: sqldiff, detect tables for which no model exists
 - Improvement: travis.yml, add pypy to tests
 - Fix: sqldiff, fix for mysql misreported field lengths
 - Fix: sqldiff, in PG custom int primary keys would be mistaking for serial
 - Fix: sqldiff, use Django 1.7 db_parameters() for detect check constraints
 - Fix: update_permissions, Django 1.7 support
 - Fix: encrypted fields, fix for Django 1.7 migrations


1.3.11
------

Changes:
 - Improvement: sqldiff, show differences for not managed tables
 - Improvement: show_urls -f aligned, 3 spaces between columns
 - Improvement: reset_db, support mysql options files in reset_db
 - Fix: sqldiff, Fixed bug with --output_text option and notnull-differ text
 - Fix: reset_db, Fix for PostgreSQL databases with dashes, dots, etc in the name
 - Fix: dumpscript, AttributeError for datefields that are None
 - Docs: Adding RUNSERVERPLUS_SERVER_ADDRESS_PORT to docs


1.3.10
------

Changes:
 - Fix: show_urls, fix bug in new formatter when column is empty


1.3.9
-----

Changes:
 - Feature: shell_plus, add --kernel option to start as standalone IPython kernel
 - Feature: reset_db, Programatically determine PostGIS template 
 - Feature: sqldiff, add support for PointField and MultiPolygonField
 - Test: renamed test app
 - Fix: runserver_plus, --print-sql for Django 1.7
 - Fix: shell_plus, --print-sql for Django 1.7
 - Fix: show_urls, add support for functions that use functools.partial
 - Fix: show_urls, add formatter for aligned output (will most likely become future default)
 - Fix: shell_plus / notebook, support for Django 1.7
 - Docs: various fixes and improvements
 - Cleanup: Remove work arounds for Django 0.96 and earlier


1.3.8
-----

Changes:
 - Feature: show_urls, add option to specify dense or verbose output format
 - Improvement: better support for django 1.7 migrations
 - Improvement: better support for django's admin docs
 - BugFix: runjob, job_name and app_name was swapped in error message
 - Docs: Update link to chinese docs
 - Python3: unreferenced_files, fix python3 compatibility
 - Python3: pipchecker, fix python3 compatibility

1.3.7
-----

Changes:
 - Reinstated: clean_pyc and compile_pyc commands, these now depends on BASE_DIR
               in settings.py as per Django 1.6. We urge everybody to include a
               BASE_DIR settings in their project file! auto-detecting the
               project-root is now deprecated and will be removed in 1.4.0.
 - I18N: Added russian locale
 - Docs: runscript, Add section about passing arguments to scripts
 - Python3: show_url, Fixed to AttributeError 'func_globals'
 - Deprecated: clean_pyc, compile_pyc, Auto-detecting project root


1.3.6
-----

Changes:
 - Additional version bump because we mistakenly already uploaded
   version 1.3.5 of the wheel package with the code of 1.3.4


1.3.5
-----

Changes:
 - Feature: Django-Extensions is now also distributed as a Wheel package
 - Improvement: dumpscript, improved the readability of comments in generated script
 - Improvement: sqldiff, backported get_constraints() for PostgreSQL
 - Improvement: shell_plus, consistent colorization
 - BugFix: encrypted fields, there is no decoding to unicode in Python 3
 - BugFix: shell_plus, importing modules failed in some edge cases
 - Django 1.7: included Django 1.7 in test suite
 - Python 3.4: included Python 3.4 in test suite


1.3.4
-----

Changes:
 - Feature: Start maintaining a CHANGELOG file in the repository
 - Feature: ActivatorModelManager now has an ActivatorQuerySet
 - Feature: Add a deconstruct() method for future Django 1.7 migration compatibility
 - Feature: show_urls, now support --language for i18n_patterns
 - Feature: show_urls, now shows the decoraters set on a view function
 - Feature: graph_models, now support --include-models to restrict the graph to specified models
 - Feature: print_settings, allow to specify the settings you want to see
 - Improvement: graph_models, use '//' instead of '#' as comment character in dot files
 - Improvement: graph_models, added error message for abstract models without explicit relations
 - Improvement: JSONField, use python's buildin json support by default with fallback on django.utils.simplejson
 - Improvement: PostgreSQLUUIDField, parse value into UUID type before sending it to the database
 - Improvement: Use django.JQuery in autocomplete.js if available
 - Improvement: use "a not in b" instead of "not a in b" in the entire codebase
 - Removed: clean_pyc command since it does not work correctly in many cases
 - Removed: sync_media_s3 command in favor of sync_s3
 - BugFix: syncdata, use pk instead of id for identifying primary key of objects
 - BugFix: sync_s3, use safer content type per default
 - BugFix: export_emails, filtering on groups
 - BugFix: print_user_for_session, use USERNAME_FIELD if defined
 - BugFix: update_permission, fixed TypeError issue
 - BugFix: JSONField, do not coerse a json string into a python list
 - BugFix: import json issue by using absolute imports
 - BugFix: add minimal version number to six (>=1.2)
 - Docs: graph_models, Added some documentation about using dot templates
 - Docs: reset_db, short description on SQL DDL used
 - Docs: Added specific list of supported Python and Django versions
 - Docs: Add link to GoDjango screencast
 - Docs: Add ShortUUIDField to docs
 - Python3: fixes to graph_models and export_emails for Python3 compatibility


1.3.3
-----

Changes:
 - Docs: Made it clearer that Django Extensions requires Django 1.4 or higher
 - Translations: FR Updated
 - Python3: Fix for shell_plus


1.3.0
-----

Changes:
 - Feature: SQLDiff much better notnull detection
 - Feature: reset_db add option to explicit set the PostGreSQL owner of the newly created DB
 - Feature: shell_plus added support for MongoEngine
 - Feature: sync_s3 enable syncing to other cloud providers compatible with s3
 - Improvement: ForeignKeyAutocompleteAdmin add option to limit queryset
 - BugFix: graph_models fix issue with models without primary key
 - BugFix: graph_models fix UnicodeDecodeError using --verbose-names
 - BugFix: dumpscript fix problems with date/datetimes by saving them now as ISO8601
 - Docs: many improvements
 - Docs: Chinese translation !!!
 - Python3: various improvements
 - Tests: add Django 1.6
