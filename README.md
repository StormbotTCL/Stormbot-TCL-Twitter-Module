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
1285908026

*	Now have the search feature implemented for tweets. I thank Mai for the tutorial on how to handle the flags. It handles MOST search queries. Some 
that it doesn't are instances where you are looking for tweets until a certain time frame. I don't foresee this being something this search feature 
will be able to handle.
*	Updated the HELP. Removed a duplicate entry for setting profile elements and noticed I had how to call rate limiting worded wrong for the command 
in the help.
*	Updated the error message returned if a 403 error is encountered.

1285642009

*	Added the latest tweet posted for each user searched for via BOT TWITTER SEARCH USER <name>.
*	Working on adding the ability to search for text within tweets. This feature not complete yet. Have to add flag handling as they aren't placed
in the typical SB6 location which would be after the command name, in this case, TWITTER. Thes flags will be after the sub command TWEET which in 
return is part of SEARCH. The command syntax will be TWITTER SEARCH TWEET <flags> <query>.

1285250941

*	Fixed display of the URL shortner. Only moourl was displaying properly, now all do once again.

1285244867

*	Added the ability to link a tweet to a specific status ID so you can chain tweets to form a conversation. Use `BOT TWITTER STATUS REPLY <msg id #> <msg text>`

1285223866

*	Added the ability to show certain status messages by their ID. Result give you who sent, status, source, date/time, and reply-to id so
you can trace back the conversation.
*	Add the ability to reset your mentions timeline so you can review them. Originally, once you viewed them once, you couldn't go back and review 
them again, only view most recent ones.
*	Created a wiki to explain how to set your bot up with Twitter. <http://github.com/demonicpagan/Stormbot-TCL-Twitter-Module/wiki>
*	Performed a check to see that you are running at least TCL version 8.5, gives suggestions of what to do if you aren't.

1285052087

*	Fixed an error when trying to call the mentions timeline. Parameter needed to pass the GET parameter.

1284329312

*	Added the ability to add and remove tweets to your favorites.
*	Set the default syntax of BOT Twitter Favorites to list your twitter favorites.

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