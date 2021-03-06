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

Please read <https://github.com/demonicpagan/Stormbot-TCL-Twitter-Module/wiki> for instructions on how to set
up your eggdrop bot to work with [Twitter] (http://twitter.com "Twitter")

Changelog - Dates are in Epoch time
-----------------------------------
1413603340

*	Patched the TLS call to use -tls1 1 due to the Poodle vulnerability disclosed by Google. Information can be found [here] (https://www.openssl.org/~bodo/ssl-poodle.pdf)

1409454028

*	Fixed an error in the friend timeline request command where if you had your name set to be highlighted it threw an error of 'invalid command name "encode"'. Should have been 'encoding'.

1408057248

*	Fixed error where the TLS TCL package was not being loaded. Missed this due to having something else loading the TLS TCL package until now.

1398871633

*	Due to being returned with error code 403 (Forbidden) and doing some digging, found out the 
reason was because SSL was required. All URLs were converted to https. As such, had to do some reconfiguration
to the ::http:: command and register the https protocol.
*	Added TLS package requirement
*	Updated error return code to be more helpful.

1388918657

*	Fixed a small typo in the help documentation when running BOTNICK TWITTER HELP.

1376855542

*	Made it to where I'm using Twitter's secure site addresses for their API
*	Fixed changed API in pulling trending data.
*	Added the ability to verify user credentials that were saved.
*	Changed error message returned for error code 401.

1362878243

*	More optimization changes.
*	Restructered the help again (Thanks Mai!)
*	Fixed the "[SB6 FAIL] An error occurred while using the TWITTER command: missing value to go with key error" when rate limit was exceeded. Will now return an actual error message stating this.
*	Added notice in the bead's help (until something else can be thought of) stating that using this bead will make your twitter timeline public even if you have a private lock on Twitter's web site.

1362828901

*	After much headache, the consumer_key and consumer_secret have been moved over to the eggdrop user data file. Information that was stored globally for this has been removed from the global data file.
*	Updated code dealing with displaying rate limits to coincide with v1.1 of the API
*	Moved package checking into SB:proc_twitter for better and optimized processing.
* Added How-To section to the help to guide users on how to set this bead up to work with Twitter.

1357418923

*	Changed the storage location of the consumer key and consumer secret IDs. This means you will have to run the /msg Botname TWITTER SETKEY <consumer key> and 
/msg Botname TWITTER SETSECRET <consumer secret> commands again to restore the values.
*	Moved the "Display the readable name of twitter user" configuration setting to the user file where it should be, not a global setting for all users.
*	If /msg Botname TWITTER SETKEY or /msg Botnname TWITTER SETSECRET have nothing after them, they will return in private the two keys that are stored if any.

1355365707

*	Updated the sbd:set twitter:author line to read "Dustin Lennon (demonicpagan@gmail.com)" instead of "Dustin Shea (demonicpagan@gmail.com)"
*	Updated help to let first time users of the command know they need to run a couple specific commands before the command can be used.
*	Fixed a syntax error in the code.

1355264993

*	Updated the API call to delete tweets
*	Fixed timeline retrieval
*	Due to permission changes, in order to access your direct messages, you will need to reauthorize the application. This means using the REQTOKEN and ACCTOKEN again.
*	Removed the command BLOCK CHECK due to it being removed from v1.1 of the Twitter API
*	Updated URLs for v1.1 of the Twitter API

1318634315

*	Updated the twitter trends api calls, they depreciated the method I was using
*	Added TRENDS AVAILABLE command to give results as to where there is trending information. This will be a long list. When I ran it for testing 111 results were returned.
Pagination has not been added to the API for this call.

1301397334

*	Normalized some lines of coding in the help documentation for it to be more uniform.

1296337943

*	Cleaned up help all display to make it look cleaner.
*	Fixed error display when getting a 400 or 403 error. Actually displays the error instead of a URL.

1291286136

*	Added f and l for following a user and unfollowing a user as command shortcuts due to finding out that sending a tweet as f <screen name> caused 
the api to return that last tweet sent from your account. If any other command syntax sent as a tweet causes this, let me know so I can add it to the 
appropriate command.

1288886393

*	Failed to put a space after a } and before a { thus causing the following error: Retrieval error. (extra characters after close-brace)

1288858914

*	Fixed how I was creating my list to parse through for the 403 error response.
*	When I wrote the code for errors returned for Twitter's 403 response code, I failed to pass the error display in the follow and unfollow commands.
*	Since 400 errors are returned the same way 403 errors are returned, cleaned up code for this.

1288852992

*	Added a default error message when trying to search for something without specifying USER or TWEET after SEARCH.
*	Added the number of tweets a user has contributed to twitter when viewing their profile.
*	Made the numbers commanized (is that even a word?) in the profile viewing.

1288238995

*	When upgrading this bead to use oAuth instead of Basic Auth, I inadvertantly pulled storing your TWITTER username to your bot's user data file.
This was stored and used in displaying messages that contained your TWITTER username. Those messages were returned as a different color when displayed 
in the room. For those of you just starting to use this bead, you would have never seen this, only those that started using this bead prior to TWITTERs
conversion. I have added back the ability to store your username and made this feature available to all once again.

1286514407

*	Just added a couple more words to the replace text list. This isn't a big update. Nothing to fix, update until I locate (or you locate) any bugs.

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
