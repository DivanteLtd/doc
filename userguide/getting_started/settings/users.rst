.. index::
   single: users

Admins
======

When your store is first set up, you receive a set of login credentials for the Administrator role that has full permissions. If there are others on your team or service providers who need access, you can create a separate user account for each from this section.

To limit the sections or elements that admin users can access when they log in, you must first create a role with limited permissions and access only to the necessary resources.
See :doc:`ACL </userguide/getting_started/settings/acl>` section to learn more about the roles.
Then, you can assign the role to a specific user account.

.. note::

    **Admin users, who are assigned to a restricted role, can see and/or change data only for resources that are associated with the role**


Admins list include both active and inactive Admin user’s – inactive are grayed-out.
You can also see their status in Active column.
Additionally, Admins list grid provides basic information about admins – name, surname, email address and authenticate method.

.. image:: /userguide/_images/users.png
   :alt:   All Admins


New admin user creation
-----------------------

To add new admin:
^^^^^^^^^^^^^^^^^

1. Tap the **Settings** icon |settings_add| in the upper-right corner and choose **Admins** on the menu.

.. |settings_add| image:: /userguide/_images/icon.png

2. To add new admin, tap ``Add``

.. image:: /userguide/_images/add_user2.png
   :alt:   New Admin Account Information

3. In the **Create admin** section, complete the following information:

  - Name
  - Surname
  - Phone
  - E-mail

  This email address must be different from the one that is associated with your original Admin account

4. Assign one of the existing **Roles** to the user account

5. Then you have to decide which of the following user authentication method to choose:

  - To authenticate user via an **API key**, do the following:

    - Mark checkbox **External**
    - Enter an **API key**, received from Open Loyalty provider

  - To authenticate user via **Password**, do the following:

    - Leave **External** checkbox blank
    - Assign a **Password** to the account

6. Set **Active** field to "Active"

7. To receive push notifications, select the **Notifications enabled** checkbox

8. When it is done, tap ``SAVE``

.. note::

    In case of API key authentication, you will authenticate the user and store that authentication in the session, so User will be automatically logged in for every subsequent request
	

Admin user edition
------------------

.. image:: /userguide/_images/admin_edition.png
   :alt:   Admin User Editing

To edit an admin account:
^^^^^^^^^^^^^^^^^^^^^^^^^

1. Tap the **Settings** icon |settings_add| in the upper-right corner and choose **Admins** on the menu.

.. |settings_edit| image:: /userguide/_images/icon.png

2. In the Admins list, find the record to be edited and click **Edit** icon |edit_form|  in the Action column to open the record in edit mode.

.. |edit_form| image:: /userguide/_images/edit.png

3. Make any necessary changes to user account information. **If you change password/API key or role, make sure to inform user about changes**

4. When it is done, tap ``SAVE``


Locked admins
-------------

Any user account, that is currently inactive, appears in the Admins list as grayed-out. An account can be unlocked (set to active) by other Admin users.

To lock/unlock an admin account:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Tap the **Settings** icon |settings_add| in the upper-right corner and choose **Admins** on the menu.

.. |settings_lock| image:: /userguide/_images/icon.png

2.	In the Admins list, find the record to be edited and click **Edit** icon |lock_form|  in the Action column to open the record in edit mode.

.. |lock_form| image:: /userguide/_images/edit.png

3. Set **Active** field to one of the following

  - **Active**
      to unlock admin account. User can log in and have access to the Open Loyalty platform
  - **Inactive**
      to lock an admin account. User will not be able to log in and have access to the Open Loyalty platform

.. tip::

    **Admin users can not be deleted from Open Loyalty platform**.

    To prevent any user from access to the platform, **set the Active field as Inactive**
