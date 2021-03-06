-*- coding: utf-8, tab-width: 2 -*-

Frequently asked questions
==========================

Is this plugin for free?
------------------------
This plugin is for free and licensed to GPL.
It's open source following the GPL policy.

= How can I revert all changes or reset the plugin? =
Paymill for WordPress brings an uninstall routine which allows completely removing all data generated by the plugin from WordPress. This is a great feature for a plugin reset, too which helps if there were upgrade or go live issues. You just have to go to your WordPress Admin Dashboard -> Plugins Overview and deactivate Paymill for WordPress. After that, a "delete" Link will appear which allows completely removing Paymill for WordPress.

Does this plugin calls to another server?
-----------------------------------------
Yes. As Pamill is a payment service provider, it is absolutely required to call home to make sure that the payments are valid.
We are talking about three different reasons for calling home:

1. PAYMILL Javascript Bridge makes sure that payment data is correct and creates a payment token delivered to your server after checkout. This avoids delivering payment data to your server, what is -in most cases- absolutely prohibited by all common credit card providers.
2. PAYMILL PHP Bridge finishes the order and delivers the generated token to the PAYMILL server.
3. For security purposes there is a feature which delivers WordPress version number and PAYMILL Plugin version number upon payment process. This will give us the ability to warn paymill merchants who are using a very outdated WordPress version or about known security holes in specific version when still using them.

Are there any fees for payments?
--------------------------------
Merchants must create an account on https://www.paymill.com/ to use the payment service.
The TEST mode is for free, but there are "per payment" fees in LIVE mode, see https://www.paymill.com/en-gb/pricing/

Do customers need to create an account for payment?
---------------------------------------------------
No. PAYMILL allows payments without annoying your customers creating an account.
They'll just fill out the payment fields on your checkout-page - that's all.

Does this plugin redirects the users to PAYMILL for payment?
------------------------------------------------------------
No. PAYMILL allows payment directly through your website without any extra redirects etc.

Does this plugin supports 3D secure?
------------------------------------
Yes. Please note that you can test 3D secure feature on LIVE mode only.
The TEST mode always gives a positive feedback on 3D secure.

Which Credit Cards are supported?
---------------------------------
Depending on your country and account status, the following credit card provider are currently supported: American Express, CB, Diners Club, Discover, JCB, Maestro, MasterCard, Union Pay, VISA

What is ELV and why it's supported?
-----------------------------------
ELV is a German banking service and stands for "Elektronisches Lastschriftverfahren".
This is a very convenience payment solution for German users, as credit cards are not very common in Germany compared to e.g. USA.

What is SEPA and why it's supported?
-----------------------------------
SEPA is a European banking service and stands for "Single Euro Payments Area".
This is a very convenience payment solution for European users, as credit cards are not very common in Europe compared to e.g. USA.

Is there a update-safe way to edit language files?
-----------------------------------
Yes, just copy language files from /wp-content/plugins/paymill/lib/translate/ as draft to customize into /wp-content/languages/paymill/

Can I use shortcodes to display the Pay Button?
-----------------------------------------------
Yes, here's an example shortcode with all currently available parameters: '[paymill_pb title="test title" products_list="1,2"]'

Are there actions/filters/hooks in the Pay Button?
--------------------------------------------------
Yes, all of them have 1 parameter as array with several vars.
You may use var_dump to get their content and structure.

Does WooCommerce Subscriptions Integration allows setup fees? How are Coupons applied?
--------------------------------------------------
Yes, but it's working through a workaround. There are two transactions made, one for the subscription and one for initial fee.
Subscriptions fee cannot be changed, even through coupons. Please be aware that coupons are working on initial fee only.