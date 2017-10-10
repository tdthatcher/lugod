---
layout: post
title: round table
date: 2015-12-20 15:00:00 -0800
categories: radio notes talk
---

* <b>WSJTX</b>

	* <b>Protocol Info</b>
		* [http://physics.princeton.edu/pulsar/k1jt/index.html](http://physics.princeton.edu/pulsar/k1jt/index.html)
		* JT9/JT65 are extremely weak-signal digital modes for LF, MF, HF, VHF, UHF
		* Designed by Joe Taylor, K1JT
		* JT9: a little more sensitive and only ~10% bandwidth of JT65
		* JT65: originally designed for EME on VHF/UHF, wider bandwidth
		* 65 tone frequency-shift keying
		* JT modes are synchronized by exact timing, so having system clock maintained
	 	 is critical.
		* Biggest benefit of JT is: exceptional sensitivity and error correction for extremely high S/N radio environments

		* QSO format is relatively rigidly defined:

			* CQ K6KA CM98
			* K6KA W1AW -1 [dB]
			* W1AW K6KA R 5 [dB]
			* K6KA W1AW RRR
			* W1AW K6KA 73

		* deviation is possible, but twitter it ain't: 13 characters and you're done 
		* non-standard message lose a level of error correction
		* certain pre-defined phrases have enhanced correction
		* EC done by a [Reed-Solomon 63,12](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction) algoritm
		* Each phrase takes almost a minute to tx/rx: about 47.8 seconds, hence the need for good time sync and plenty of 
		  patience for a full QSO

		* There are some standardized frequencies suggested on every band for JT modes. Examples: 
			* 1.838 - 160m
			* 3.576 - 80m
			* 5.357 - 60m 
			* 7.076 - 40m
			* 14.076 - 20m 
			* 28.076 - 10m 
			* 50.276 - 6m
			* 144.489 - 2m
			* etc etc
		
				
	* <b>Basic Configuration</b>

		* interface of choice to your radio: i use a tigertronics signalink USB
		* use pulseaudio and pavucontrol [screenshot 1: setup]({{ site.url }}/images/desktop1_4.png) 
		* [action shot]({{ site.url }}/images/desktop1_3.png)
		* Configure radio for Upper Sideband (or digital/umode-USB if your radio supports that)
		* Select the band from the dropdown, and a frequency will be suggested. CAT control can automatically
		  tune your radio (if supported) or reach over and operate the dang radio yourself
		* Waterfall: live display of band increasing from left to right.
		  specifics depend on the receive bandwidth of your radio
		* Decodes across the waterfall, but you can focus on a specific signal
		  by moving the RX slider (or manually enter in the main window)
		* Move TX slider to choose where exactly to transmit within the band, so you don't stomp on someone else's weak signal
		* Integration with [PSKReporter](http://pskreporter.info) will automatically show CQs received on a world map (if the sender
		  is using standard-format messages, with location reporting - not everyone does
		* An example of what JT can do - last night listening on 40m using a speaker-wire antenna:	

				Rx at Mon, 21 Dec 2015 06:49:51 GMT
				JA1JRK: Japan: MASATAKE YATABE (Rio) -- 1 class -- QSL: Via Buro ,Direct and LoTW L
				1941-3 SAWA, HITACHINAKA; IBARAKI 312-0001; Japan
				QM06gk 36.447451, 140.538242 src: user -- 8171.9 km, 304° from CM98--
				[Received at -7 dB]

				Rx at Mon, 21 Dec 2015 07:44:50 GMT
				UA0FO: Asiatic Russia : Sergey Litvinenko -- ua0fo@bgtelecom.ru -- 1 class 
				-- IOTA: AS-018 -- prev UA0FDG -- QSL: BUREAU, DIRECT, LOTW, eQSL,
				QRZ.COM, QRZCQ.COM (see below) LE
				Box 41; Yuzhno-Sakhalinsk. 693023; Asiatic Russia
				QN16ix 46.978333, 142.706667 [src: user] -- 9585.7 km, 336° from FN21wa
				QN16ix: 46.9792, 142.7083: Yuzhno-Sakhalinsk, Sakhalin Oblast, Russia -- 7366.5 km, 312° from CM98--
				[Received at -11 dB]


 
	* <b>Sources</b>

		* [http://www.arrl.org/files/file/18JT65.pdf](http://www.arrl.org/files/file/18JT65.pdf)
		* [http://obriensweb.com/wsjtx.html](http://obriensweb.com/wsjtx.html)
		* [http://physics.princeton.edu/pulsar/k1jt/wsjtx.html](http://physics.princeton.edu/pulsar/k1jt/wsjtx.html)


* <b>GPREDICT</b>
	* [http://gpredict.oz9aec.net/](http://gpredict.oz9aec.net/)
	* Looks [super cool]({{ site.url}}/images/desktop2_5.png)
	* Use to track orbital objects for your visual or radio pleasure
	* Create custom "modules" that display custom maps, certain sets of satellites, etc
	* Track your favorite Cubesat projects, like [AO-85](http://www.amsat.org/?page_id=4690) - contains an 800mW
	  repeater split on 145.980 downlink/435.180 uplink (see website for details) and broadcasts telemetry, 
          which can be decoded with [FoxTelem software](http://amsat.us/FoxTelem/linux/)
	* Track International Space Station and make an astronaut contact via [ARISS](http://www.ariss.org/)
	  or just view it with your telescope/bare eyeballs
	* Don't forget to check your TLE "Three-Line Element" files are updated from the menu, or download them
	  manually from [http://www.celestrak.com/NORAD/elements/](http://www.celestrak.com/NORAD/elements/).
	  TLEs are telemetry data from which GPredict can derive orbital predictions (and why it's called GPredict).
	* There are other sources for TLEs, offering alleged tracking of orbital vehicles that "They" 
	  may or may not officially acknowledge...
	  

* <b>FLDIGI</b>
	* [http://www.w1hkj.com/](http://www.w1hkj.com/)
	* It's a monster that does a lot of stuff, including CAT rig control
	* Radio-specific CAT configuration available from community-built XML files
	* good for PSK digital modes and automatic CW decoding
	

* <b>AX.25</b>
	* god help you 
	* So poorly documented that one guy wrote his master's thesis on how poorly documented it is:
	<i>Finnegan, Kenneth W: [Examining Ambiguities in the Automatic Packet Reporting System](http://digitalcommons.calpoly.edu/cgi/viewcontent.cgi?article=2449&context=theses)</i>
