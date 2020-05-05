====================
Django Mail Template
====================

===========
Quick start
===========

Description
===========

Django Mail Template has two main objectives:

* Provide *basic template* features for mails subjects and bodies.

* Provide needed infrastructure to let administrative users create/edit mails
  used by applications.


Requirements
------------

1) Django's email docs specify all requirements for sending mail with
django.core.mail (`Django email`_).

2) ``django_mail_template`` uses *Django admin interface*, check official
documentation for it's requirements: `Django admin site`_.

.. _`Django email`: https://docs.djangoproject.com/en/dev/topics/email/

.. _`Django admin site`: https://docs.djangoproject.com/en/dev/ref/contrib/admin/


Quick start
===========


Installation and configuration
------------------------------

1. Install ``django_mail_template`` from pypi:

::

   pip install django-mail-template

2. Add *'django_mail_template'* to your INSTALLED_APPS:

::

   INSTALLED_APPS = [
       ...
       'django_mail_template.apps.DjangoMailTemplateConfig',
   ]


3. Run migrations:
::

    python manage.py migrate


Use Django Mail Template
========================




Two
===

Three
-----

Four
~~~~

Five
^^^^


Any MailTemplate must have a unique code.
Can not send email if the MailTemplate instance is not saved to DB.
Is not necessary to have a configuration to use MailTemplate.


