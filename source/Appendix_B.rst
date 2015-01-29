**********************************
Appendix B - Complete command list
**********************************

.. note:: COMMAND TEMPORISATION All commands can be temporised (i.e. associated to a starting time) adding a proper **suffix**. There are two possibilities:
      * “@DOY-HH:MM:SS”, where DOY is the Day-Of-Year (1-366) and HH:MM:SS is the UT time; 

      * “@!DAYS-HH:MM:SS”, where DAYS is the number of days and HH:MM:SS is hours, minutes, seconds.


Here follow all the commands exploitable in Nuraghe:

	**> antennaPark**
		sends the antenna to stow position
		resets the alarm conditions
		unstows the antenna, sets it to tracking mode and configures the 
		pointing model according to the specified receiver. It does NOT 
		perform the receiver and backend setup
		stops the antenna. Activities can start again only commanding a 
		mode change as antennaTrack (which does not affect the overall setup) or a new setup
		sets the antenna to PROGRAMTRACK mode. 
		It does not change the pointing model or any receiver setup
		enables the active surface according to the selected setup (see the *asSetup* command)
		sets the Az-El offsets (degrees). They are intended “on sky”, i.e. 
		it is the actual offset run on the sky at the source Elevation. 
		switches the calibration mark on
		switches the calibration mark off
		selects the backend; string can be BACKENDS/TotalPower or BACKENDS/XBackends
		selects the backend; string can be MANAGEMENT/FitsZilla, 
		MANAGEMENT/MBFitsWriter or MANAGEMENT/Point
		zeroes the subreflector system-defined offsets (e.g. the ones resulting from a focus scan) 
		performs a cross-scan on the previously selected target (indicated using the *track* or 
		*sidereal* commands), along the scanFrame (‘eq’,’hor’ or ‘gal’), spanning *span* degrees 
		in *duration* seconds 
		computes the beamsize, taking into account the present receiver and backend 
		configurations relative to section sect
		deletes the N-th element in the queue of temporised commands
		deletes all the queue of the temporised commands
		performs a focus scan over the tracked source, span is in mm along 
		the z-axis, duration is expressed in hh:mm:ss 
		reads the attenuation values (dB) currently configured for the active sections, 
		and lists them according to increasing section number
		reads the signal intensity (raw counts) for the active sections, 
		and lists them according to increasing section number
		slews the antenna to an offset position, in the indicated coordinate 
		frame (‘eq’, ‘hor’ or ‘gal’). The user provides the offset value (degrees only), 
		but the system automatically chooses on which axis to perform the slewing, 
		taking into account the present position of the antenna
		sends the antenna, while in TRACKING mode, to the specified Az-El position 
		respectively (in any case the ranges are limited to mechanical contraints). 
		The jolly character is valid and is considered as: keep the present value. 
		The differences from the *preset* command are:

			  system will acknowledge the “on source” status;
			  are applied. In case they are not required they must be turned off explicitly.
		completes the current scan and then stops the schedule
		configures the backend using the default parameters relative to 
		the selected receiver. It does NOT act on the receiver, pointing model 
		or antenna mount mode. 
		sets the backend integration time (ms)
		defines a custom name for the logfile (do not specify the extension)
		sets the Galactic b-l offsets (degrees). They are intended “on sky”, i.e. 
		it is the actual offset run on the sky at the source latitude. 
		points the antenna to the present coordinates of the center of the Moon
		sends the antenna, if in PRESET mode, to the specified Az-El position, 
		without applying any pointing correction. This is useful when needing to 
		point to a position next to the zenith. Beware: the antenna will reach the 
		destination but no “on source” flag will be raised 
		lets the system know which project is observing (the code/name must correspond 
		to the one provided by the TAC). This code/name is then considered as default 
		when launching schedules: the system will search for them in a folder named 
		“project/schedules”. This code/name also forms part of the output FITS filename. 
		Notice that the PROJECT keyword indicated inside the schedule, which is then written 
		in the “Project Name” keyword in the FITS main header, is a free string and might 
		differ from the project official name. 
		sets the RA-Dec offsets (degrees). They are intended “on sky”, i.e. 
		it is the actual offset run on the sky at the source Declination.  
		configures the working mode of the receiver, according to its peculiar characteristics
		configures the receiver using the default parameters. 
		It does NOT act on the backend, pointing model or antenna mount mode
		stows the minor servo system
		configures the minor servo system only
		sets to att (dB) the attenuator of section sect
		Local Oscillator frequency, in MHz (one per IF, separated by “;”, 
		usually the values are identical) This LO frequency corresponds to: 
		SkyFreq(@band start) – 100 MHz when using the TPB
		configures the backend section sect.
		chooses the subreflector pointing model according to the AS being enabled (ON) or disabled (OFF)
		sets the subreflector to tracking mode, with OFF tracking is disabled
		(see details in Antenna Operations)
		unstows the antenna, sets it to tracking mode, selects the pointing model, 
		and configures the receiver and the backend using default parameters. 
		In practice, it is a shortcut corresponding to this sequence: 

			* antennaSetup=[code] 
			* receiversSetup=[receiverCode] 
			* initialize=[receiverCode] 
			* device=0 
			* calOff 
		points to the supplied RA-Dec position and temporarily assigns the sourcename 
		label to it. Epoch can be ‘1950’, ‘2000’ or ‘-1’, the last one meaning that the provided 
		coordinates are precessed to the observing epoch. The sector keyword forces the cable wrap 
		sector, if needed: its value can be ‘cw’, ‘ccw’ or ‘neutral’. 
		The last option means the system will automatically choose the optimal alternative
		performs an OTF acquisition at the current azimuth position, spanning in elevation from 
		*El1* to *El2* (both expressed in degrees, with ‘d’ suffix), in *duration* seconds. 
		A recorded must have previously been enabled in order to save the data. 
		runs schedule *schedulename*.scd (project is the ID of the observing project, 
		it is optional if it has already been input through the *projectCode* command), 
		reading it from line *N*  
		immediately stops the running schedule, truncating the acquisition
		stows the antenna and parks both the AS and the MS
		lists all the active temporised commands
		points the antenna, in sidereal tracking, to the specified source, 
		which must be present in the local catalogue 
		measures the system temperature (K) in the position the antenna is pointing to. 
		It returns a list of values, one for each section in use.Intermediate steps 
		and calculations are stored in the active logfile
		sets a delay (in seconds) which is applied before the system reads/executes the next command
		returns the current weather parameters: ground temperature (°C), relative humidity (%), 
		atmospheric pressure (hPa), wind speed (km/h).