:show-content:

================================================
Payment Acquirers (Credit Cards, Online Payment)
================================================

.. toctree::
   :titlesonly:

   payment_acquirers/wire_transfer
   payment_acquirers/adyen
   payment_acquirers/alipay
   payment_acquirers/authorize
   payment_acquirers/buckaroo
   payment_acquirers/mollie
   payment_acquirers/ogone
   payment_acquirers/paypal
   payment_acquirers/sips
   payment_acquirers/stripe

Odoo embeds several **payment acquirers** that allow your customers to pay on their *Customer
Portals* or your *eCommerce website*. They can pay Sales Orders, invoices, or subscriptions with
recurring payments with their favorite payment methods such as **Credit Cards**.

Offering several payment methods increases the chances of getting paid in time, or even immediately,
as you make it more convenient for your customers to pay with the payment method they prefer and
trust.

.. image:: payment_acquirers/online-payment.png
   :align: center
   :alt: Pay online in the customer portal and select which payment acquirer to use.

.. note::
   Odoo apps delegate the handling of sensitive information to the certified payment acquirer so
   that you don't ever have to worry about PCI compliance.

   This means that no sensitive information (such as credit card numbers or credentials) is stored
   on Odoo servers or Odoo databases hosted elsewhere. Instead, Odoo apps use a unique reference
   number to the data stored safely in the payment acquirers' systems.

.. _payment_acquirers/acquirers:

Payment Acquirers
=================

From an accounting perspective, we can distinguish two types of payment acquirers: the payments that
go directly on the bank account and follow the usual reconciliation workflow, and the payment
acquirers that are third-party services and require you to follow another accounting workflow.

.. _payment_acquirers/bank_payments:

Bank Payments
-------------

- | :doc:`Wire Transfer <payment_acquirers/wire_transfer>`
  | When selected, Odoo displays your payment information with a payment reference. You have to
    approve the payment manually once you have received it on your bank account.
- | SEPA Direct Debit
  | Your customers can sign a SEPA Direct Debit mandate online and get their bank account charged
    directly. :doc:`Click here <../finance/accounting/receivables/customer_payments/batch_sdd>` for more
    information about this payment method.

.. _payment_acquirers/online_providers:

Online Payment Providers
------------------------

+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
|                                     | Redirection to       | Payment   | Save Cards | Capture Amount  | Refund    |
|                                     | the acquirer website | from Odoo |            | Manually        | from Odoo |
+=====================================+======================+===========+============+=================+===========+
| :doc:`Adyen                         | ✔                    | ✔         | ✔          |                 | ✔         |
| <payment_acquirers/adyen>`          |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`Alipay                        | ✔                    |           |            |                 |           |
| <payment_acquirers/alipay>`         |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`Authorize.Net                 | ✔                    | ✔         | ✔          | ✔               |           |
| <payment_acquirers/authorize>`      |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`Buckaroo                      | ✔                    |           |            |                 |           |
| <payment_acquirers/buckaroo>`       |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`Mollie                        | ✔                    |           |            |                 |           |
| <payment_acquirers/mollie>`         |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`Ogone                         | ✔                    |           |            |                 |           |
| <payment_acquirers/ogone>`          |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`PayPal                        | ✔                    |           |            |                 |           |
| <payment_acquirers/paypal>`         |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| PayU Latam                          | ✔                    |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| PayUMoney                           | ✔                    |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`SIPS                          | ✔                    |           |            |                 |           |
| <payment_acquirers/sips>`           |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+
| :doc:`Stripe                        | ✔                    | ✔         | ✔          |                 |           |
| <payment_acquirers/stripe>`         |                      |           |            |                 |           |
+-------------------------------------+----------------------+-----------+------------+-----------------+-----------+

.. note::
   Some of these Online Payment Providers can also be added as :doc:`Bank Accounts
   <../finance/accounting/bank/setup/bank_accounts>`, but this is **not** the same process as adding them
   as Payment Acquirers. Payment Acquirers allow customers to pay online, and Bank Accounts are
   added and configured on your Accounting app to do a bank reconciliation, which is an accounting
   control process.

.. _payment_acquirers/configuration:

Configuration
=============

Some of the features described in this section are available only with some Payment Acquirers. Refer
to :ref:`the table above <payment_acquirers/online_providers>` for more details.

.. _payment_acquirers/add_new:

Add a new Payment Acquirer
--------------------------

To add a new Payment acquirer and make it available to your customers, go to
:menuselection:`Accounting --> Configuration --> Payment Acquirers`, look for your payment acquirer,
install the related module, and activate it. To do so, open the payment acquirer and change its
state from *Disabled* to *Enabled*.

.. image:: payment_acquirers/activation.png
   :align: center
   :alt: Click on install, then on activate to make the payment acquirer available on Odoo.

.. warning::
   We recommend using the *Test Mode* on a duplicated database or a test database. The Test Mode is
   meant to be used with your test/sandbox credentials, but Odoo generates Sales Orders and Invoices
   as usual. It isn't always possible to cancel an invoice, and this could create some issues with
   your invoices numbering if you were to test your payment acquirers on your main database.

.. _payment_acquirers/credentials_tab:

Credentials tab
~~~~~~~~~~~~~~~

If not done yet, go to the **Online Payment Provider**'s website, create an account, and make sure
to have the credentials required for third-party use. Odoo requires these credentials to communicate
with the Payment Acquirer and get the confirmation of the *payment authentication*.

The form in this section is specific to the Payment Acquirer you are configuring. Please refer to
the related documentation for more information.

.. _payment_acquirers/configuration_tab:

Configuration tab
~~~~~~~~~~~~~~~~~

You can change the Payment Acquirer front-end appearance by modifying its name under the **Displayed
as** field and which credit card icons to display under the **Supported Payment Icons** field.

.. _payment_acquirers/payment_methods:

Enable Local Payment Methods
****************************

Local payment methods are payment methods that are only available for certain merchants and
customers countries and currencies. They also depend on your acquirer.

To enable specific Local Payment Methods with your acquirer, list them as supported payment icons.
To do so, go to :menuselection:`Payment Acquirers --> Stripe --> Configuration` and add the desired
payment methods in the **Supported Payment Icons** field. If the desired payment method is already
listed, you don't have anything to do.

.. image:: payment_acquirers/media/stripe_enable_local_payment_method.png
   :align: center
   :alt: Select and add icons of payment methods you want to enable

.. note::
    If a payment method icon doesn't exist at all in the database, the corresponding local payment method is always offered
    to customers.

.. _payment_acquirers/save_cards:

Save and reuse Credit Cards
***************************

With the **Save Cards** feature, Odoo can store **Payment Tokens** in your database, which can be
used for subsequent payments, without having to reenter the payment details. This is particularly
useful for subscriptions' recurring payments.

.. _payment_acquirers/capture_amount:

Place a hold on a card
**********************

If you wish to manually capture an amount instead of having an immediate capture, you can enable the
manual capture. Capturing payments manually has many advantages:

  - You can have the payment confirmation before shipping and only make the capture after it's done.
  - You avoid potentially high credit card fees in the event of overselling or cancelled Orders.
  - It allows you to review and verify that orders are legitimate before the payment is completed and
    the fulfillment process starts.

The **Capture Amount Manually** field is under the **Configuration** tab. If enabled, the funds are
reserved for a few days on the customer's card, but not charged yet.

.. image:: payment_acquirers/media/capture_manually.png
   :align: center
   :alt: Adyen Configuration tab on Odoo

To capture the payment, you must then go to the related
Sales Order and manually *capture* the funds before its automatic cancellation, or *void the
transaction* to unlock the funds from the customer's card.

.. image:: payment_acquirers/media/capture.png
   :align: center
   :alt: Hold the credit card payment until you capture or revoke it on Odoo

.. note::
   Odoo may not yet support the manual capture for all acquirers, but you can manage the capture in
   your chosen acquirers interfaces.

.. _payment_acquirers/countries:

Countries
*********

Restrict the use of the Payment Acquirer to a selection of countries. Leave this field blank to make
the Payment Acquirer available to all countries.

.. _payment_acquirers/journal:

Payment Journal
***************

The **Payment Journal** selected for your Payment Acquirer must be a *Bank* journal.

.. _payment_acquirers/messages:

Messages tab
~~~~~~~~~~~~

Change here the messages displayed by Odoo after a payment's confirmation or failure.

.. _payment_acquirers/accounting:

Accounting perspective
======================

The **Bank Payments** that go directly to one of your bank accounts follow their usual
reconciliation workflows. However, payments recorded with **Online Payment Providers** require you
to consider how you want to record your payments' journal entries. We recommend you to ask your
accountant for advice.

Odoo default method is to record the payments on a *Current Assets Account*, on a dedicated *Bank
Journal*, once the *Payment Authentication* is confirmed. At some point, you transfer the funds from
the *Payment Acquirer* to your *Bank Account*.

Here are the requirements for this to work:

- Bank Journal

  - The Journal's **type** must be *Bank Journal*.
  - Select the right **Default Debit Account** and **Default Credit Account**.
  - | Under the *Advanced Settings* tab, make sure that **Posting** is set as *Post At Payment
      Validation*.
    | This implies that the Journal Entry is recorded directly when your Odoo database receives the
      confirmation of the *Payment Authentication* from the Online Payment Provider.

- Current Asset Account

  - The Account's **type** is *Current Assets*
  - The Account must **Allow Reconciliation**

.. note::
   Odoo automatically creates a new **payment method** for your new Payment Acquirer when you
   activate it. You can modify it necessary.

.. seealso::

   - :doc:`../finance/accounting/receivables/customer_payments/recording`
   - :doc:`../websites/ecommerce/shopper_experience/payment_acquirer`
   - :doc:`payment_acquirers/wire_transfer`
   - :doc:`payment_acquirers/adyen`
   - :doc:`payment_acquirers/alipay`
   - :doc:`payment_acquirers/authorize`
   - :doc:`payment_acquirers/buckaroo`
   - :doc:`payment_acquirers/mollie`
   - :doc:`payment_acquirers/ogone`
   - :doc:`payment_acquirers/paypal`
   - :doc:`payment_acquirers/sips`
   - :doc:`payment_acquirers/stripe`
