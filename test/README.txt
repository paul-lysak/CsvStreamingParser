This folder contains some basic tests which don't cover all tricky things, they rather test overal functionality. 

How to run tests:
	1. Create a symlink dojo-src in this folder (test) which points to Dojo source distrubution (tested with 1.8.1 version)
	2. Start a web-server which serves project root directory (parent of test directory). If you don't want to set up heavy full-featured server you may use
a tip from http://www.artificialworlds.net/blog/2012/10/30/running-dojo-doh-tests-in-a-browser-without-a-web-servero/ 
With python 2.X:
python -m SimpleHTTPServer
With python 3.X:
python3 -m http.server
	2. Open runTests.html in your browser. Tested with Firefox 15.0.1 on 64 bit Linux
	3. Enjoy!

DOH (Dojo testing framework) can also be run from command line, please see Dojo docs if you're interested.
