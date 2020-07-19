.. _testing_mail_template:

Testing Mail Template
=====================

It is possible to test one o more *MailTemplate*. This action will help you to
determine if everything is right with *MailTemplates*, for example if in
body o subject there are errors that can cause the process to fail, typically
errors when writing variables:

``Dear {first_name} {last_name{``


Requirements
------------

To test a MailTemplate, first you need to edit it and be sure there is a
value in ``To`` field, if not the sending process will fail.

When testing, send method will be called: be sure you will not be sending
emails to wrong people.


Test mails templates action
---------------------------

In *MailTemplate* list (always in *Django admin site*) there is an action
named "Test mails templates". Select *MailTemplates* to be tested and then
execute this action. After testing messages will appear at the top of the
page and inform the result of the action (identifying each Mail Template with
its title).
