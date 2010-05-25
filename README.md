Twitter Client for Stormbot 6 - TCL
===================================
Developer: Dustin Lennon<br />
Email: <demonicpagan@gmail.com>

Install Instructions
--------------------
Just place this module in your botdir/scripts/beads directory and then run BOT maint load twitter to load the module.

Refer to the help file in the module for usage instructions: BOT TWITTER help

If you experience any issues please submit a bug report on
<http://github.com/demonicpagan/Stormbot-TCL-Twitter-Module/issues>.

You can always get the latest source from <http://github.com/demonicpagan/Stormbot-TCL-Twitter-Module> as well.

Changelog - Dates are in Epoch time
-----------------------------------
1274798544

*	Redone the help to make it clearer between the difference of SHORTENER and 
SHORTEN
*	Changed the multiple if statements in the SHORTENER switch to a list index 
setting
*	Removed the requirement for handle as a procedure call parameter for 
twitter:urlshorten and twitter:shorten
*	Made moourl.com an available option as a URL shortener (must have the updated 
sb6_tail.tcl file for this to work. See me if you need it and SB6 isn't back 
online for distribution yet)

1274652765

*	Went from Basic Authentication to OAuth Authentication

1273180216:

*	Created a README for GitHub and brought this repository online.