
==========
PayU Money
==========

`PayU Money <https://payu.in/>`_ is the Indian part of
`PayU <https://corporate.payu.com/about-payu/>`, an online payments platform.

Configuration
=============

To proceed your payments with Payu Money, COINCOIN

.. note::
   Please refer to :ref:`Add a new Payment Acquirer <payment_acquirers/add_new>` to read how to
   enable this payment acquirer on Odoo.

Credentials tab
---------------

Odoo needs your **API Credentials** to connect with your PayU Money account, which comprise:

- Merchant Key: The Key solely used to identify the account with PayU Money.
- Merchant Salt: COINCOIN ?

You can copy your credentials from your PayU Money account, and paste them in the related fields under the **Credentials** tab.

.. image:: media/payumoney_credentials.png
   :align: center
   :alt: PayU Money required credentials.
   :width: 500

To retrieve them, COINCOIN

.. important::
   If you are trying PayU Money as a test, in the *sandbox*, change the **State** to *Test Mode*. We
   recommend doing this on a test Odoo database, rather than on your main database. COINCOIN?

.. seealso::
   - `PayU Money: Create an account <https://onboarding.payu.in/app/account>`_
   - :doc:`../payment_acquirers`
