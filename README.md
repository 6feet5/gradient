gradient
========

Gradient is a small perl script that will make text appear in a gradient color when viewed with dzen.
I made it so that I could have a gradient output in dzen, based on input from conky.

Features
--------

   * Text is read from STDIN, processed, then output to STDOUT, making it easy to pipe from conky to dzen
   * Start and stop color is given as command arguments
   * Number of steps in gradient is based on printable characters in input (not counting spaces)
   * Control sequences in input, for dzen, is not touched or processed

Requirements
------------

In order to run gradient you need Color::Spectrum from CPAN.

Installation
------------

Put script in a suitable location (making sure its path is in $PATH or use full path when running gradient)
Make sure it's executable by running:
    
    chmod +x <path to script>

Running gradient
----------------

gradient will read text from standard input and calculate the number of steps in the gradient based on the number of visible characters, not counting spaces and control sequences for dzen.
The result is then printed to standard output.  
In order to make a gradient from red to green, using conky and dzen, this is what you would run:
    
    conky | gradient FF0000 00FF00 | dzen ...

Known bugs
----------
No known bugs, but the detection of dzen color sequences is rather naive so you may run in to problems if you use advanced ones.

Contact
-------
Feature requests, patches or what ever else related to gradient can be sent  
to: johan dot stenarson at gmail dot com

Copyright and license
---------------------
Copyright (C) 2013 by Johan Stenarson

Licensed under [GPL](http://www.gnu.org/licenses/gpl.html "GPL v3 License")
