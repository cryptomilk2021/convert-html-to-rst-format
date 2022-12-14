kucoin-lending
==============

Overview
--------

This bot automates your asset lending on kucoin.com, it improves on the
auto-lend feature by cancelling orders that have been sitting around for
a given number of hours

It than goes and relends these assets

Features
--------

-  Implementation of REST endpoints

-  Cancel loan orders that are more than certain number of hours old

-  Submit lend orders, splitting them into (and up to) 3 lowest lending
   rates

-  Generate transaction report

-  add to 'unlendable' assets file, (assets with no landing rates
   available)

-  add to 'lending precision' file, if an asset already does not exist
   in it, precision = decimal place accuracy for lend orders, ie USDT is
   1, AVAX is 0.1 etc

Setup
-----

-  Generate a 'Trade' API in Kucoin

-  Kucoin Sandbox doesn't really work with lending at the time of
   writing

-  Store generated keys in your env under

   -  API_NAME,

   -  API_KEY,

   -  API_PASSPHRASE,

   -  API_SECRET

-  set delete_orders_older_than_hours to how long you want orders to
   persist

-  no need to switch off auto-lend, old orders will get cancelled and
   resubmitted before auto-lend wakes up, however, I recommend to switch
   off auto-lend anyway

-  assets that you do not want processed add to unlendable.csv

-  run program, trans_log.txt will report of cancellations and new lend
   orders

Going forward
-------------

-  have one call to kucoin in the object implement \*args to pass 2 or 3
   values depending on call

-  check which way an asset is trending, if it's going up use slightly
   higher interest rates

Change Log
----------

+-------+-------------------------------------------------------------+
| 0.1.2 | -  lending rates step up at 0.0001 from lowest available,   |
|       |    therefore if current rates from Kucoin are 0.00001 and   |
|       |    00003, our lending rates will fill in the 0.00002 gap    |
|       |                                                             |
|       | -  production (True/False) flag taken out                   |
|       |                                                             |
|       | -  if after rounding lend amount is 0.00, no lending,       |
|       |    especially true for ETH                                  |
|       |                                                             |
|       | -  improved rounding of amount to be lent out               |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
| 0.1.1 | fix up some assets amount format issues in trans_log.txt    |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
|       |                                                             |
+-------+-------------------------------------------------------------+
| 0.1.0 | initial Alpha                                               |
+-------+-------------------------------------------------------------+

| 

| 

| 
