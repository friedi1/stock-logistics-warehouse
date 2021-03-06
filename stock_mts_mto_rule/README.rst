.. image:: https://img.shields.io/badge/licence-AGPL--3-blue.svg
   :target: http://www.gnu.org/licenses/agpl-3.0-standalone.html
   :alt: License: AGPL-3

==================
Stock MTS+MTO Rule
==================

This module add a Make To Stock + Make to Order Route.

If you choose the make to stock + make to order rule instead of the make to
order route, the creation of a purchase order will depend on the virtual stock.
There are 3 cases : 

1. The virtual stock of the product is 0 
    => It will act exactly like the make to order route.

2. The virtual stock is equal to the quantity ordered
    => It will act exactly like a make to stock route

3. The virtual stock is more than 0 but less than ordered quantity
    => On part of the products will be taken from stock and a purchase order
       will be created for the rest. So it will act like both make to order and
       make to stock rule.

Example : 
We have a virtual stock of : 1 product A
A sale Order is made for 3 products A.
2 Procurements will be created : 

1. 1 with a make to stock rule and a quantity of 1

2. 1 with a make to order rule and a quantity of 2.

After validation, a purchase order with 2 products will be created.

Usage
=====

You have to select the mts+mto route on the product form.
You should not select both the mts+mto route and the mto route.

.. image:: https://odoo-community.org/website/image/ir.attachment/5784_f2813bd/datas
   :alt: Try me on Runbot
   :target: https://runbot.odoo-community.org/runbot/153/8.0

Configuration
=============

You have to select 'Use MTO+MTS rules' on the company's warehouse form.

Bug Tracker
===========

Bugs are tracked on `GitHub Issues
<https://github.com/OCA/stock-logistics-warehouse/issues>`_. In case of trouble, please
check there if your issue has already been reported. If you spotted it first,
help us smashing it by providing a detailed and welcomed `feedback
<https://github.com/OCA/
stock-logistics-warehouse/issues/new?body=module:%20
stock_mts_mto_rule%0Aversion:%20
8.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Credits
=======

Contributors
------------

* Florian da Costa <florian.dacosta@akretion.com>

Maintainer
----------

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

This module is maintained by the OCA.

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

To contribute to this module, please visit https://odoo-community.org.
