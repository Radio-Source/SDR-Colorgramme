# SDR-Colorgramme
SDR Colorgramme is cross plateform RF Meteor real Time detector and send results on www.rmob.org 


SDR Colorgramme v 1.0
SDR Colorgramme is a software designed for the detection and counting of meteors via
radio echoes within the RF spectrum rather than the audio spectrum.
It is a dedicated program using PothosSDR, capable of controlling various SDR receivers
such as:
• RTL-SDR (USB dongles based on Realtek RTL2832U / R820T chips, etc.)
• HackRF (HackRF One)
• BladeRF (bladeRF x40 / x115)
• LimeSDR (LimeSDR Mini, LimeSDR USB)
• USRP (Ettus Research / UHD hardware)
• Airspy (Airspy R2 / Mini) and Airspy HF+
• SDRplay (via SoapySDRplay compatible modules)
• PlutoSDR (Analog Devices ADALM-PLUTO)
• FCD / Funcube Dongle

This documentation does not cover the installation of your SDR hardware; we assume it is
already installed and has been tested using another software.
If this is not the case, we advise you to first install Gqrx SDR, which is cross-platform and
highly effective at hardware recognition.
As a reference, SDR Colorgram was developed using an HB9CV antenna and a Nooelec
NESDR SMArTee SDR dongle tuned to 143.05 MHz to monitor the Graves radar.
The software is configurable and designed to minimize the impact of interference such as
the Graves carrier, aircraft, numerous satellites, and transient noise covering a wide
frequency spectrum (such as lightning storms).
The detection principle is simple: it relies on a technique used in optical astronomy, namely
the measurement of the Full Width at Half Maximum (FWHM), applied to an RF spectrum.
Detection is performed in real time, and the relevant RF spectrum curve is saved as an
image in a "meteors_captures" subfolder.
An image of the "time zone" waterfall is also saved—with a delay—in a
"waterfall_captures" subfolder.

The images in these two subfolders are organized by year/month/day, and the timestamp
is included in the image filename.

Windows install :  Download https://www.rmob.org/file/SDR_Colorgramme_v1_Setup.zip unzip and run setup

Linux Install :
If you have allready installed and tested our SDR now you can install  SDR_Colorgramme v 1.0 by typing this command in a terminal :
bash <(curl -s https://www.rmob.org/download/install.sh)
The download and installation process is automatic and guided.

If you whant remove SDR_Colorgramme v 1.0
You can delete it by typing this command in a terminal : ~/sdr_colorgramme_v1/uninstall.sh
The waterfall helps interpret the validity of the detection within the RF spectrum by
contextualizing it within its temporal environment, is always recorded when the detected
meteor is at the center of the image (y=100px).
Two additional parameters supplementing FWHM detection allow you to "filter" and
prevent false detections:
• An adjustable threshold (in dB) of the FWHM "height" (FWHM Threshold) green
line.
Secondary Threshold line in red is automatic threshold for strong power echoes
detection adjustable with Max Power Coeff (multiplier coefficient of FWHM
Threshold)
• A filter for multiple peak detections or interference lines, adjustable via a variable
named px Max.
These simple parameters give me great satisfaction on my setup, despite living under an
air corridor, dealing with an extraordinarily high number of Starlink echoes, and facing the
Graves radar shifting its frequency and phase more or less randomly.
In any case, it must be understood that 100% automatic detection is virtually impossible;
you must accept "losing" a few echoes by giving yourself a safety margin on the settings,
otherwise false detections will become too numerous.
This software can also be used on other frequencies, such as dedicated transmitters
around 50 MHz or for observing AM transmitters.
It features an audio output filtered for comfortable listening. Naturally, you can simply mute
the computer's sound or change the audio source if you prefer not to hear it.
When launching the software, nothing seems to happen at first—this is normal.
Calibration is the only operation requiring supervision the first time you run the software.
Press the "Start" button to start the receiver; you will see the RF spectrum come to life
along with the FFT waterfall below it.
An initial calibration will run over 200 lines (the height of the RF waterfall). This is entirely
arbitrary, but generally sufficient for the software to "discover" at least the basic
parameters—such as the Median FWHM—and set an initial FWHM Threshold accordingly.
You can then fine-tune the FWHM Threshold and Detection Threshold settings.
Once the settings yield results that satisfy you best, click the "Save CONFIG" button. Your
parameters are then saved. If you close the software or experience an unexpected power
outage, your settings will be automatically restored without any action on your part.
Finally, if you wish to participate on www.rmob.org, you must fill out the form that opens
when you click the "Observer" button.
Fill in all fields properly and submit. Normally, every 30 minutes, the software will transfer
your data to the web server at www.rmob.org/live.php.
You will also find two files bearing your name in the root folder of the software:
• The RMOB report in text format.
• A Colorgram image corresponding to that rmob text file.
• The logs in txt files in LOGS subdir
ALL TIMES and DATE in images timestamp



and RMOB file is in UTC AUTOMATICALLY
calculated from your computer location zone, don’t change anything about date and time 
