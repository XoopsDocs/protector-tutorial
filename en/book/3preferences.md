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

|Module configuration option|	Function|
|---|---|
|Action if a UNION is found|	Anti SQL injection measure. Select the action when the UNION syntax of SQL is found. Options are:<br>•	None (only logging).<br>•	Sanitizing.<br>•	Blank screen.<br>•	Ban the IP.<br><br>"Sanitizing" means changing "union" to "uni-on". This is the default and recommended option.|
|Force intval to variables like id|	This measure was to guard against a problem in an older weblog module, which has since been patched.<br><br>All requests with names such as "*id" will be treated as integers. This option protects you from some kind of XSS and SQL Injections. It is recommended to turn this option on, but it can cause problems with some modules. The default is ‘off’.|
|Protection from Directory Traversals|	This setting eliminates ".." from all requests that look like attempted directory traversals. Options are to turn this on (yes) or off (no). The default setting is on.|
|Anti Brute Force|	Here you can set the number of times you allow guests to try to login with 10 minutes. If someone fails to login in excess of this limit their IP will be banned. This prevents people mounting brute force attacks against logins. The default value is 10.|
|Modules out of DoS/Crawler checker|	Protector can ban IPs that seem to be mounting DoS attacks or crawlers that consume excessive resources (see below). However, you can exclude individual modules from this protection by entering their directory names here. Separate multiple modules with a &#124; character. This option is useful for things like chat modules.|
|Watch time for high loadings (sec)|	This value specifies the watch time for high / frequent reloading (F5 attack) and high loading crawlers. The default is 60 seconds.|
|Bad counts for F5 Attack|	Measure against DoS attacks. This value specifies the number of reloads (within the watch period above) that must be made before an IP is considered to be making a malicious attack. The default 10.|
|Action against F5 Attack|	What do you want to do when an F5/DoS attack is detected? Options are:<br>•	None (only logging).<br>•	Sleep.<br>•	Blank screen.<br>•	Ban the IP.<br>•	Deny by htaccess (an experimental feature). <br><br>The default response is a blank screen. If you want to use the deny by htaccess feature you need to set XOOPS_ROOT_PATH/.htaccess as writable. However, please note that this entails some risk in itself.

|Module configuration option|	Function|
|---|---|
|Bad counts for crawlers|	Measure against high loading web crawlers or bots. The value set here specifies the number of access attempts that can be made before a crawler is considered to be ‘badly behaved’, ie. consuming too many resources. The default is 30 reloads.|
|Action against high loading crawlers|	What do you want to do when a ‘bad’ crawler is detected? Options are:<br>•	None (only logging).<br>•	Sleep.<br>•	Blank screen.<br>•	Ban the IP.<br>•	Deny by htaccess (experimental feature). <br><br>The default response is a blank screen.|
|Welcomed User-Agent|	A perl regex pattern for User-Agent. You can use this to prevent Protector from accidentally reacting against ‘good’crawlers, such as those from Google. If it matches, the crawler is never considered as a high loading crawler. The default is: /(msnbot&#124;Googlebot&#124;Yahoo! Slurp)/i |
|Groups never registered as Bad IP|	A user who belongs to the group specified here will never be banned. The default is ‘webmasters’, and it is recommended to leave it this way.|
|Disable dangerous features in XOOPS|	This option can be used to protect against some known bugs and security holes. This is largely relevant to old versions of xoops as these have been closed in recent versions (if you are running an old version of XOOPS you should consider upgrading it).<br><br>The default is xmlrpc, other options are xmlrps + 2.0.9.2 bugs, or none.|
|enable anti-XSS (BigUmbrella)|	This protects you from some attacks via cross-site scripting (XSS) vulnerabilities. But it is not 100% . The default is no (off), probably a good idea to turn it on.|
|anti-SPAM: URLs for normal users|	You can set a limit on how many URLs will be tolerated in POST data from registered users (eg. in forum posts and comments) other than administrators. If the POST contains too many URLs it is considered to be spam. The default is 10. If you want to disable this feature, set it as 0.|
|anti-SPAM: URLs for guests|	As above, but for anonymous (guest) users. The default in this case is 5. Set it to 0 if you want to disable this feature.|

