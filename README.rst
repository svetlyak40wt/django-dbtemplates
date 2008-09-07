===================================
Database template loader for Django
===================================

This is a basic database template loader for Django which uses a m2m
relationship to provide a site centric template loading.

How to use it in your own Django application
============================================

0. Get the source from the subversion repository
1. Follow the instructions in the INSTALL file
2. Edit the settings.py of your Django project:

   Add ``dbtemplates`` to the ``INSTALLED_APPS`` of your django project
 
   Check if ``django.contrib.sites`` and ``django.contrib.admin`` are in
   ``INSTALLED_APPS`` and add if necessary.
 
   It should look something like this::
 
       INSTALLED_APPS = (
           'django.contrib.auth',
           'django.contrib.contenttypes',
           'django.contrib.sessions',
           'django.contrib.sites',
           'django.contrib.admin',
           'django.contrib.flatpages',
           'dbtemplates',
           'myapp.blog',
       )
 
   Add ``dbtemplates.loader.load_template_source`` to the
   ``TEMPLATE_LOADERS`` list in the settings.py of your Django project
 
   It should look something like this::
 
       TEMPLATE_LOADERS = (
           'django.template.loaders.filesystem.load_template_source',
           'django.template.loaders.app_directories.load_template_source',
           'dbtemplates.loader.load_template_source',
       )

3. Sync your database via shell (hint: "./manage.py syncdb" within project dir)
4. Restart your Django server
5. Go to the admin interface and add templates by filling the ``name`` field
   with filename like identifiers, for example "blog/entry_list.html"
6. Use it with ``Flatpages``, ``Generic views`` and your own custom views

Support
=======

Please leave your questions and messages on the designated Google Code site:

http://code.google.com/p/django-databasetemplateloader/
