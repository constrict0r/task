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

This role expand files or URLs by default so you must write your items like:

.. substitution-code-block:: bash

 |DEFAULT_VAR_NAME|:
   - item_path: |DEFAULT_VAR_VALUE|
     item_expand: false


You can change this default behaviour by:

- Setting the **expand** variable to *false*.

Or

- Add to an item the attribute **item_expand** setted to *true*.