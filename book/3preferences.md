# 3.0 Preferences

The configuration options and recommended settings for Protector are summarised in the table below. For the most part, you can just leave the settings at the defaults.


|Module configuration option|	Function|
|---|---|
|Temporarily disabled (yes/no)|	You can turn Protector off temporarily if you are having problems. Don't forget turn it back on when you have fixed the problem. Default is 'no'.|
|Reliable IPs|	Enter IPs that you consider 'reliable' eg. your own. These IPs will not be banned by Protector, which can help stop you locking yourself out. Set IPs you can rely separated with &#124; . ^ matches the head of string, $ matches the tail of string.|
|Logging level|	Options (default is 'full') are: <br>-	None.<br> -	quiet.<br> - Quiet (this is quieter than 'quiet').<br> - Full.|
|Protected IP bits for the session|	This is an anti session hijacking measure that limits how far IP bits can move within a session.<br>•	Default 32 bit - all bits are protected (IP cannot change).<br>•	If you have a dynamic IP that moves within a known range, you can set the number of protected bits to roughly match. <br>•	For example, if your IP can move in the range of 192.168.0.0 to 192.168.0.255, set 24 bit here. If a cracker knew your session IP but tried to access from outside this range (say 192.168.2.50) they would fail.<br>The author of the module suggests 16 bit as a balanced value for general use.|
|Groups not allowed to move their IP in a session|	Anti session hijacking measure. Selected groups are not permitted to change their IP in a session. The default is ‘webmasters’ and it is recommended to leave it that way as the consequences of an administrator’s session getting hijacked could be quite severe.|
|Sanitizing null-bytes|	The terminating character "\0" is often used in malicious attacks. A null-byte will be changed to a space if this option is on (which is the default, and it is highly recommended to leave it this way).|
|Exit if bad files are uploaded (yes/no)|	If someone tries to upload files which have risky extensions like .php , Protector exits XOOPS. If you often attach php files into B-Wiki or PukiWikiMod you may need to turn this off to avoid problems.|
|Action if contamination is found|	Select the action when someone tries to contaminate system global variables into your XOOPS. Options are:<br>•	None – only logging.<br>•	Blank screen.<br>•	Ban the IP.<br>The recommended option is blank screen (default).|
|Action if an isolated comment-in is found|	Anti SQL injection measure. Select the action when an isolated "/*" is found. Options are:<br>•	None (only logging). <br>•	Sanitizing.<br>•	Blank screen.<br>•	Ban the IP.<br>"Sanitizing" means adding another "*/" in the tail, and is the recommended option. However the default is 'none (only logging)'. You might want to change this.|
