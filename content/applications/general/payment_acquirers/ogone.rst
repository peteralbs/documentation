
=====
Ogone
=====

`Ogone <https://www.ingenico.com/>`_, also known as **Ingenico Payment Services** is a France-based
company that provides the technology involved in secure electronic transactions.

Configuration
=============

An Ogone Production account is needed to get paid with Ogone. Create a production account or
upgrade your test account to a production account.
To proceed your payments with Ogone, you need to have an Ogone production account.

.. note::
   Please refer to :ref:`Add a new Payment Acquirer <payment_acquirers/add_new>` to read how to
   enable this payment acquirer on Odoo.

Credentials tab
---------------

Odoo needs your **API Credentials** to connect with your Ogone account, which comprise:

- PSPID: The ID solely used to identify the account with Ogone. You chose it when you opened your
  account.
- :ref:`API User ID<ogone/api_user>`: The ID solely used to identify the user with Ogone.
- :ref:`API User Password<ogone/api_user>`: Value used to identify the user with Ogone.
- :ref:`SHA Key IN <ogone/sha_key_in>`: Key used in the signature Odoo send to Ogone.
- :ref:`SHA Key OUT <ogone/sha_key_out>`: Key used in the signature Ogone send to Odoo.

You can copy your credentials from your Ogone account, and paste them in the related fields under
the **Credentials** tab.

.. _ogone/api_user:

API User ID and Password
~~~~~~~~~~~~~~~~~~~~~~~~

If you already created a User and have both its ID and passwword, just copy them. You can also
generate a new password from :menuselection:`Configuration --> Users --> Your chosen user --> change
password`.

If you don't have a user, in can create one by going to :menuselection:`Configuration --> Users -->
New User`. You can set your **User ID** and will get your **password** when you save your new user.

.. image:: media/ogone_new_user.png
   :align: center
   :alt: Get your password when you save the new user.

.. _ogone/sha_key_in:

SHA Key IN
~~~~~~~~~~

In order to retrieve the SHA Key IN, log into your ogone account, go to
:menuselection:`Configuration --> Technical Information --> Data and origin verification -->
Checks for e-Commerce & Alias Gateway`, and get **SHA Key IN**.

.. _ogone/sha_key_out:

SHA Key OUT
~~~~~~~~~~~

In order to retrieve the API Key and the Client Key, log into your ogone account, go to
:menuselection:`Configuration --> Technical Information --> Transaction feedback --> All transaction
submission modes`, and get or generate your **API Key** and **Client Key**. Be carefull to copy your
API key as you'll not be allowed to get it later without generating a new one.

.. important::
   If you are trying Ogone as a test, with the Test Account, change the **State** to *Test Mode*. We
   recommend doing this on a test Odoo database, rather than on your main database.

.. seealso::
   - :doc:`../payment_acquirers`
