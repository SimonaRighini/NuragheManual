*************
Initial Setup
*************


Antenna overall setup
=====================

When opening a Nuraghe observing session, it is necessary to perform a setup which includes the antenna unstow, the mount configuration in tracking mode, the minor servo setup. This is done by means of a unique command, which is specific for the wanted receiver, to be written in the **operatorInput**. 


.. tabularcolumns:: |c|c|c|c|c|

========  ==========  ================  ===============  ==================  =================
Receiver  LO freq     Frontend IF band  Backend IF band  Observed bandwidth  Observed band
--------  ----------  ----------------  ---------------  ------------------  -----------------
code      \(MHz\)     \(MHz\)           \(MHz\)          \(MHz\)             \(MHz\)
========  ==========  ================  ===============  ==================  ================= 
LLP       \(0\) [1]_  1300-1800         (50-2350) [2]_   500                 (1300-1800) [2]_
PPP       \(0\) [1]_  305-390           (50-730) [2]_    85                  (305-390) [2]_
CCB       5600        100-2100          50-2350          2000                5700-7700 
KKG       21964       100-2100          50-2350          2000                22064-24064
========  ==========  ================  ===============  ==================  =================

.. [1] Virtual value: there is no LO for this receiver
.. [2] Still subject to variations

Notice that, depending on the devices in use, the sky frequency at the observed band starting point is given by the LO frequency plus an offset. For the present combinations of the frontends *with the total power backend*, which the above table refers to, this offset is 100 MHz. 


Active Surface setup
====================

After the initial setup, to configure and enable the active surface (AS) give the following commands in the operatorInput panel::


Minor Servo configuration
=========================

When using the Gregorian or BWG focus only, the minor servo must be configured. 


Logfile and project code
========================

The default logfile is named **station.log**. 