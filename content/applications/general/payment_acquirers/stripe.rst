
======
Stripe
======

`Stripe <https://stripe.com/>`_ is a United States-based online payment solution
provider, allowing businesses to accept **credit cards** and other payment methods.


Configuration
=============

To proceed your payments with Stripe, you need to activate your Stripe account to get live data.

.. note::
   Please refer to :ref:`Add a new Payment Acquirer <payment_acquirers/add_new>` to read how to
   enable this payment acquirer on Odoo.

Credentials tab
---------------

Odoo needs your **API Credentials** to connect with your Stripe account, which comprise:

- Publishable Key: The key solely used to identify the account with Stripe.
- Secret Key: The key to sign the merchant account with Stripe.
- Webhook Signing Secret: If a webhook is enabled on your Stripe account
  (:menuselection:`Developers --> webhooks`), this signing secret must be set to authenticate the
  messages sent from Stripe to Odoo.

To retrive the publishable and secret keys, log into your Stripe dashboard and go to
:menuselection:`Developers --> API Keys --> Standard Keys`

.. important::
   If you are trying Sripe as a test, in the **test mode**, change the **State** to *Test
   Mode*. We recommend doing this on a test Odoo database, rather than on your main database.

.. seealso::
   - :doc:`../payment_acquirers`
