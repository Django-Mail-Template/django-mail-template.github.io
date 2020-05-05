========
Advanced
========

Configuration
=============

Create a *Configuration* to map a *process name* with a MailTemplate. This let
developer to create an algorithm that use a *process name* for sending
emails while users maps *MailTemplates* with *Configurations* at run time
through *Django admin interface*.

In short word an administrative user can create/update application's mails
at run time.



Using process map in data models
--------------------------------

Is also possible to use MailTemplate with other data model to get more dynamic
capabilities. For example, with a book model, you can add it a Char field were
to keep a *process's name*. Then, users can change the process
mapped with an instance (by changing *process's name*), and by doing this they
will be changing the MailTemplate used to send mails.

::

    class Book(models.Model):
        ...
        audience = models.CharField(max_length=200, null=True, blank=True)
        ...

The upper example will let a user to use admin GUI (if Book model is
properly registered) to change the audience mapped with each book. The
next example show a possible code:

::

    from django_mail_template.models import Configuration

    ...
    foreach book in Book.objects.all():
        mail_template = Configuration.get_mail_template(book.audience)
        if mail_template:
            # Do something and send mail
            ...

In upper example each instance (book) can use a different MailTemplate.
The mail to send to each audience can be specific. If the audience are kids,
one type of mail will be used, but if the audience are seniors other type of
mail will be used. And both type of mail, and their content, can be changed by
administrative users:

* Changing the value of *audience* field of a book.

* Changing or editing the mapped MailTemplate.
