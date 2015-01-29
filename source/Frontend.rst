*******************
Frontend operations
*******************


General rules
=============

To change the frontend Local Oscillator frequency, use the following command:: 
	e.g.  > setLO=5600 



Specific notes for the L/P receiver
===================================

The L/P receiver is actually seen by Nuraghe as a group of three different receivers, each having its own setup code: 

PPP
---

Only the P band can be used. The possible configurations are:: 

LLP
---

Only the L band can be used. The possible configurations are:: 

PLP (dual band)
--------------- 

In this setup, both bands are used and can be configured, according to the following scheme, based on the permutation of all the previously described codes::