========
Advanced
========

Configuration
=============

Create a *Configuration* to map a *process name* with a *MailTemplate*. This
let developer to create an algorithm that use a *process name* for sending
emails while users maps *MailTemplates* with *Configurations* at run time
through *Django admin site*.

In short word an administrative user can create/update application's mails
at run time.


Map process with data models
----------------------------

Is also possible to use *MailTemplate* with other data model to get more
dynamic capabilities. For example, book model with a audience field (*process
name*) will let to send different mails to the different audiences. And the
mails sent to each audience can be changed without the need to modify the code.

::

    class Book(models.Model):
        ...
        audience = models.CharField(max_length=200, null=True, blank=True)
        ...

The upper example will let a user to use admin GUI to change the audience
mapped with each book. The next example show a possible code:

::

    from django_mail_template.models import Configuration

    ...
    foreach book in Book.objects.all():
        mail_template = Configuration.get_mail_template(book.audience)
        if mail_template:
            # Do something and send mail
            ...

In upper example each instance (book) can use a different *MailTemplate*.
The mail to be sent to each audience can be specific. If the audience are kids,
one type of mail will be used, but if the audience are seniors other type of
mail will be used. And both type of mail, and their content, can be changed in
*Django admin site* without modifying the code of the application:

* Changing the value of *audience* field of a book.

* Changing or editing the mapped *MailTemplate*.


List Fields
===========

Fields like To, Cc, Bcc, and Reply-to requires ``a list or tuple of addresses
separated with comma`` but with ``django_mail_template`` is possible to give
values to this fields when creating a *MailTemplate* in *Django admin
interface* or by creating objects with code. Because of this, this fields
(To, Cc, Bcc, and Reply-To) accept address separated with comma (as CharField
do not accept list), then *MailTemplate* during the sending process will
convert this fields in lists with coma separated addresses.


CKEditor
=========

::

    pip install django-ckeditor

Add 'ckeditor' to your INSTALLED_APPS setting.


Run the collectstatic management command: $ ./manage.py collectstatic. This will copy

Finally run $./manage.py makemigrations and $./manage.py migrate.








