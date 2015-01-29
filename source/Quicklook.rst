**********************************
Data formats and online quick-look
**********************************

Waiting for a comprehensive GUI which is going to include also a real-time preview of the data under acquisition, users are provided with two different tools in order to inspect the data produced by the TPB. 

If writer is MANAGEMENT/FitsZilla
=================================
When acquiring FITS files through a schedule, there is an IDL tool available for the semi-realtime quick-look of the saved data.
 
Open a terminal on *nuraghe-obs2*. Launch IDL::
          while using 'atemp' the antenna temperature - *if available* - is shown.



If writer is MANAGEMENT/Point or MANAGEMENT/CalibrationTool
===========================================================

When data are acquired – both manually or through a schedule – using the Point or CalibrationTool writers, the quick-look must be performed using the CalibrationToolClient. 

.. figure:: images/CalToolClient.png
   :scale: 80%
   :alt: calibrationtoolclient 
   :align: center

.. note:: In this client, the subscan currently being acquired is shown *in real-time* (upper plot), even if in a low-res version. Under this display, the last completed subscan - in its full sampling - is shown. 