Description
--------------------------------------------------------------

Ansible role to run arbitrary tasks.

It allows to specify a task file or URL and this role will run it without
having to write a playbook or another role.

This role performs the following actions:

- Ensure the requirements are installed.

- Update the apt cache.

- Ensure dependencies are installed.

- If the **user_tasks** variable is defined run each specified task.

- If the **configuration** variable is defined and the **user_tasks** variable
  is defined, run each specified task.

Inside each specified task is possible to use the **unified** variable that
will have the list of specified users.

This role do not expand files or URLs by default because the most common case
is to specify URLs that points directly to a tasks file, so the
default behaviour for this role is to treat file paths and URLs as plain text.

You can change the default behaviour by:

- Setting the **expand_b** variable to *true*.

Or

- Add to an item the attribute **item_expand** setted to *true*.