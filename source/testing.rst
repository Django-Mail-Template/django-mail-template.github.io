Testing Mail Template
=====================

It is possible to test one o more *MailTemplate*. This action will help you to
determine if everything is right with MailTemplates, for example if in
body o subject there are errors that can cause the process to fail, for
example when there is an error of writing variables:

``Dear {first_name} {last_name{``


Requirements
------------

To test a MailTemplate, first you need to edit it and be sure there is a
value in ``To`` field, if not the sending process will fail.

When testing, send method will be called: be sure you will not be sending
emails to wrong people.

4.1 Test your Mail Template
+++++++++++++++++++++++++++

For each created *MailTemplate* is possible to test it. In *MailTemplate*
list (always in *Django admin site*) there is an action named "Test mails
templates" to test selected *MailTemplates*. Before a *MailTemplate* can be
tested ``To`` field of those *MailTemplate* must have a valid email address.
