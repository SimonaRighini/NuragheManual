******************
Antenna operations
******************

Besides the overall telescope setup previously described, individual commands are available to change the antenna mount status and manage its steering/pointing: 
		resets the antenna status after a failure, for example after the emergency stop button is released
		the minor servo system according to the selected receiver. Mount is 
		set to ProgramTrack mode
		it sets the mount to ProgramTrack mode, allowing the execution of sidereal 
		tracking, on-off, OTF scans, etc…Even beam-parking acquisitions (i.e. on a 
		fixed Az-El position) can be now performed in ProgramTrack mode by means 
		of the goTo command
		ProgramTrack mode
       			e.g. > goTo=180d,45d
		within the station catalogue (which includes the most commonly observed 
		calibrators), it directly points to the source and tracks it
		position and temporarily assigns the sourcename label to it. Epoch can 
		be ‘1950’, ‘2000’ or ‘-1’, the last one meaning that the provided 
		coordinates are precessed to the observing epoch. The sector keyword 
		forces the cable wrap sector, if needed: its value can be ‘cw’, ‘ccw’ 
		or ‘neutral’. The last option means the system will automatically choose the optimal alternative

.. note:: **COORDINATE FORMATS** 
   Whenever celestial coordinates (Equatorial, Horizontal or Galactic) are specified, the allowed formats are:
   *  **decimal degrees**, using a ‘d’ suffix, for any coordinate →  e.g.   30.00d   


Back to the commands:

		frame (‘eq’, ‘hor’ or ‘gal’). The user provides the offset value (degrees only), 
		but the system automatically chooses on which axis to perform the slewing, 
		taking into account the present position of the antenna
		The following example sets an azimuth offset to 0.5 degrees and the elevation offset to 0.3 degrees
		  	
		The following example sets the right ascension offset to 0.3 degrees and the elevation offset to 0.0 degrees
		The following example sets the galactic longitude offset to 0.1 degrees and the galactic latitude offset to 0.5 degrees
   and they are mutually exclusive! If the user commands the offsets several times in a row 
   (in one or different frames) only the last one will be effective. **Offsets specified within schedules, 
   at subscan level, sum up to these user-defined offsets.**
			
On with the list:

	**> setServoOffset=[axis_code],[value]**       (→ for technical activities)
			* SRP_TX 	# SRP translation along the X axis (mm)
		The [value] argument is a mm value that is assigned to the offset. For instance, in order to set a 5mm offset to the subreflector Z axis: 
			> setServoOffset=SRP_TZ,5