
====
SIPS
====

`SIPS <COINCOIN>`_ is an online payments platform COINCOIN.

Configuration
=============

To proceed your payments with COINCOIN

.. note::
   Please refer to :ref:`Add a new Payment Acquirer <payment_acquirers/add_new>` to read how to
   enable this payment acquirer on Odoo.

Credentials tab
---------------

Odoo needs your **API Credentials** to connect with your SIPS account, which comprise:

- Merchant ID: The ID solely used to identify the merchant account with SIPS.
- Secret Key: COINCOIN ?
- Secret Key Version: COINCOIN prérempli
- Interface Version: COINCOIN prérempli

You can copy your credentials from your SIPS account, and paste them in the related fields under
the **Credentials** tab.

.. image:: media/sips_credentials.png
   :align: center
   :alt: SIPS required credentials.
   :width: 500

To retrieve them, COINCOIN

.. important::
   If you are trying SIPS as a test, in the *sandbox*, change the **State** to *Test Mode*. We
   recommend doing this on a test Odoo database, rather than on your main database. COINCOIN?

.. seealso::
   - `SIPS: COINCOIN <COINCOIN>`_
   - :doc:`../payment_acquirers`
