
*****************************************
Checklist for schedule-based observations
*****************************************

Notice that actions take place in three different “locations”:

  * **(1)** = action to be performed in a terminal on the observing machine
  * **(2)** = action to be performed in a terminal on the data-access machine

**Login on both (1) and (2)** 

**Launch the monitors, if necessary** (1):: 


	> antennaReset  (if resuming after the emergency stop button is released)  
	> setupCCB      (or other receiver code) 
	> asSetup=S     (or other AS code)
	> setServoASConfiguration=ON    (if using a secondary focus receiver)	
	> setServoElevationTracking=ON  (if using a secondary focus receiver)

	—> e.g. setLO=6600 - start frequency of the observed band will depend on the backend

	> goTo=[Az]d,[El]d 
	—> e.g. goTo=180d,45d
	> chooseRecorder=BACKENDS/TotalPower    

	—> iteratively adjust attenuations until the level is about 850 counts 


	> chooseRecorder=MANAGEMENT/Point 
		$ calibrationtoolclient MANAGEMENT/Point            (to display the plots) 
 


.. NOTE::
   If using XARCOS, edit schedule in order to tune its internal frequency and the frontend LO

		
 
 


 

