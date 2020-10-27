# VAreport
VA Report writing
Vulnerability Assessment of Government Website

Website- http://www.xxxx.ac.in
Vulnerabilities – 18                                                                          (Overall Risk- Medium)

1.	X-Frame-Options Header Not Set
Medium (Medium)
CWE Id : 16
WASC Id : 15
Description
X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks.
•	URL: https://xxxx.ac.in/xmlrpc.php
•	Method: GET
•	Parameter: X-Frame-Options
•	URL: https://xxxx.ac.in/install.php
•	Method: GET
•	Parameter: X-Frame-Options
•	URL: https://xxxx.ac.in/update.php?op=info
•	Method: GET
•	Parameter: X-Frame-Options
Instances: 3
Solution
Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. ALLOW-FROM allows specific websites to frame the web page in supported web browsers).
Reference
•	http://blogs.msdn.com/b/ieinternals/archive/2010/03/30/combating-clickjacking-with-x-frame-options.aspx
2.	Secure Pages Include Mixed Content (Including Scripts)
Medium (Medium)
CWE Id : 311
WASC Id : 4
Description
The page includes mixed content, that is content accessed via HTTP instead of HTTPS.
•	URL: https://xxxx.ac.in/visitor-analytics
•	Method: GET
•	Evidence: http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics&domain=xxxx.ac.in&width=250&height=250&ana_type=pageviews
Instances: 1
Solution
A page that is available over SSL/TLS must be comprised completely of content which is transmitted over SSL/TLS.
The page must not contain any content that is transmitted over unencrypted HTTP.
This includes content from third party sites.
Other information
tag=script src=http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics&domain=xxxx.ac.in&width=250&height=250&ana_type=pageviews
tag=script src=http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics-referer&domain=xxxx.ac.in&width=250&height=250&ana_type=referer
tag=script src=http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics-browser&domain=xxxx.ac.in&width=250&height=250&ana_type=browser
tag=script src=http://analytics.wrc.nic.in/cmfanalytics/widget?div=browser_cat&domain=xxxx.ac.in&width=250&height=250&ana_type=browser_cat
Reference
•	https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet
3.	Cookie No HttpOnly Flag
Low (Medium)
CWE Id : 16
WASC Id : 13
Description
A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=misc/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=node/88273
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=admin
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=node
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=themes/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=user/logout
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=filter/tips
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=node/88273
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=user/logout
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=misc/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=modules/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=profiles/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=modules/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=themes/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=user/password
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=profiles/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=user/logout
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=misc/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=misc/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=profiles/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
Instances: 90
Solution
Ensure that the HttpOnly flag is set for all cookies.
Reference
•	http://www.owasp.org/index.php/HttpOnly
4.	Cookie Without Secure Flag
Low (Medium)
CWE Id : 614
WASC Id : 13
Description
A cookie has been set without the secure flag, which means that the cookie can be accessed via unencrypted connections.
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=filter/tips
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=themes/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=profiles/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=user/login
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=misc/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=node/add
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=user/password
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=admin
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=themes/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=themes/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=filter/tips
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=node/add
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=misc/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=filter/tips
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=admin
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=node
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=comment/reply
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=profiles/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=node/88273
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=themes/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
Instances: 90
Solution
Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Ensure that the secure flag is set for cookies containing such sensitive information.
Reference
•	http://www.owasp.org/index.php/Testing_for_cookies_attributes_(OWASP-SM-002)
5.	Incomplete or No Cache-control and Pragma HTTP Header Set
Low (Medium)
CWE Id : 525
WASC Id : 13
Description
The cache-control and pragma HTTP header have not been set properly or are missing allowing the browser and proxies to cache content.
•	URL: https://xxxx.ac.in/themes/seven/ie6.css?0
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: max-age=1209600
•	URL: https://xxxx.ac.in/newsandevents/three-day-national-level-workshop-application-artificial-intelligence-conservation
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/library/inter-library-loan-service
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/feedback
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=21600
•	URL: https://xxxx.ac.in/LICENSE.txt
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: max-age=1209600
•	URL: https://xxxx.ac.in/install.php
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: no-cache, must-revalidate
•	URL: https://xxxx.ac.in/library/library-statistics
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/acts/obc-cell
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/library/books-reservation
•	Method: GET
•	Parameter: Pragma
•	Evidence: public
•	URL: https://xxxx.ac.in/?q=filter/tips/
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/acts/rti
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/acts/nss-cell
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/xmlrpc.php
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=21600
•	URL: https://xxxx.ac.in/library/awarness-service
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/academic-program
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/CHANGELOG.txt
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: max-age=1209600
•	URL: https://xxxx.ac.in/sites/all/themes/cmf/css/bxslider.css
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: max-age=1209600
•	URL: https://xxxx.ac.in/library/resource/current-journals
•	Method: GET
•	Parameter: Pragma
•	Evidence: public
•	URL: https://xxxx.ac.in/academics/academic-calendar
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
•	URL: https://xxxx.ac.in/admissions/central-universities-common-entrance-test-cucet-2020-wwwcucetexamin
•	Method: GET
•	Parameter: Cache-Control
•	Evidence: public, max-age=900
Instances: 170
Solution
Whenever possible ensure the cache-control HTTP header is set with no-cache, no-store, must-revalidate; and that the pragma HTTP header is set with no-cache.
Reference
•	https://www.owasp.org/index.php/Session_Management_Cheat_Sheet#Web_Content_Caching
6.	Cookie Without SameSite Attribute
Low (Medium)
CWE Id : 16
WASC Id : 13
Description
A cookie has been set without the SameSite attribute, which means that the cookie can be sent as a result of a 'cross-site' request. The SameSite attribute is an effective counter measure to cross-site request forgery, cross-site script inclusion, and timing attacks.
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=user/login
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=profiles/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=modules/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=user/password
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=themes/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=modules/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=node/88273
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=user/logout
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=comment/reply
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=misc/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=filter/tips
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=node/88273
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=profiles/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=profiles/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=misc/%2A.js%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=filter/tips
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=user/login
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=themes/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=user/register
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=themes/%2A.css%24
•	Method: GET
•	Parameter: styleswitcher[cmf]
•	Evidence: Set-Cookie: styleswitcher[cmf]
Instances: 92
Solution
Ensure that the SameSite attribute is set to either 'lax' or ideally 'strict' for all cookies.
Reference
•	https://tools.ietf.org/html/draft-ietf-httpbis-cookie-same-site
7.	Server Leaks Information via "X-Powered-By" HTTP Response Header Field(s)
Low (Medium)
CWE Id : 200
WASC Id : 13
Description
The web/application server is leaking information via one or more "X-Powered-By" HTTP response headers. Access to such information may facilitate attackers identifying other frameworks/components your web application is reliant upon and the vulnerabilities such components may be subject to.
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=filter/tips
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=node
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/modules/*.js$
•	Method: POST
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=user/register
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=user/password
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/screen-reader
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/?q=comment/reply/
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/maps
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=node
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/library/our-team
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/misc/*.png
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/modules/*.js
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/hi
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/library/reference-service
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=node/add
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/acts/grievance
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=user/register
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=profiles/%2A.css%24
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
•	URL: https://xxxx.ac.in/group/internal-committees-university
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
Instances: 280
Solution
Ensure that your web server, application server, load balancer, etc. is configured to suppress "X-Powered-By" headers.
Reference
•	http://blogs.msdn.com/b/varunm/archive/2013/04/23/remove-unwanted-http-response-headers.aspx
•	http://www.troyhunt.com/2012/02/shhh-dont-let-your-response-headers.html
8.	Absence of Anti-CSRF Tokens
Low (Medium)
CWE Id : 352
WASC Id : 9
Description
No Anti-CSRF tokens were found in a HTML submission form.
A cross-site request forgery is an attack that involves forcing a victim to send an HTTP request to a target destination without their knowledge or intent in order to perform an action as the victim. The underlying cause is application functionality using predictable URL/form actions in a repeatable way. The nature of the attack is that CSRF exploits the trust that a web site has for a user. By contrast, cross-site scripting (XSS) exploits the trust that a user has for a web site. Like XSS, CSRF attacks are not necessarily cross-site, but they can be. Cross-site request forgery is also known as CSRF, XSRF, one-click attack, session riding, confused deputy, and sea surf.
CSRF attacks are effective in a number of situations, including:
•	The victim has an active session on the target site.
–	The victim is authenticated via HTTP auth on the target site.
•	The victim is on the same local network as the target site.
 	CSRF has primarily been used to perform an action against a target site using the victim's privileges, but recent techniques have been discovered to disclose information by gaining access to the response. The risk of information disclosure is dramatically increased when the target site is vulnerable to XSS, because XSS can be used as a platform for CSRF, allowing the attack to operate within the bounds of the same-origin policy.
•	URL: https://xxxx.ac.in/?q=user/login/
•	Method: POST
•	Evidence: <form action="/?q=user/login/" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/group/foreign-admissions
•	Method: GET
•	Evidence: <form action="/group/foreign-admissions" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/acts/online-fees-deposit
•	Method: GET
•	Evidence: <form action="/acts/online-fees-deposit" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/library/downloads
•	Method: GET
•	Evidence: <form action="/library/downloads" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/library/news-paper-clipping
•	Method: GET
•	Evidence: <form action="/library/news-paper-clipping" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/profiles/*.css$
•	Method: GET
•	Evidence: <form action="/profiles/*.css$" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/?q=user/password/
•	Method: GET
•	Evidence: <form action="/?q=user/password/" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/?q=user/login/
•	Method: POST
•	Evidence: <form autocomplete="off" action="/?q=user/login/" method="post" id="user-login" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/node/add/
•	Method: GET
•	Evidence: <form action="/node/add/" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/jrf-research
•	Method: GET
•	Evidence: <form action="/jrf-research" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/library/library-statistics
•	Method: GET
•	Evidence: <form action="/library/library-statistics" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/acts/anti-discrimination
•	Method: GET
•	Evidence: <form action="/acts/anti-discrimination" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/user/login/
•	Method: GET
•	Evidence: <form autocomplete="off" action="/user/login/" method="post" id="user-login" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/acts/placement-cell
•	Method: GET
•	Evidence: <form action="/acts/placement-cell" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/comment/reply/
•	Method: GET
•	Evidence: <form action="/comment/reply/" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/youtubevidoes/curaj-documentary
•	Method: GET
•	Evidence: <form action="/youtubevidoes/curaj-documentary" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/visitor-analytics
•	Method: GET
•	Evidence: <form action="/visitor-analytics" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/admissions
•	Method: GET
•	Evidence: <form action="/admissions" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/library/resource/userpolicy
•	Method: GET
•	Evidence: <form action="/library/resource/userpolicy" method="post" id="search-block-form" accept-charset="UTF-8">
•	URL: https://xxxx.ac.in/library/rules-regulations
•	Method: GET
•	Evidence: <form action="/library/rules-regulations" method="post" id="search-block-form" accept-charset="UTF-8">
Instances: 162
Solution
Phase: Architecture and Design
Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid.
For example, use anti-CSRF packages such as the OWASP CSRFGuard.
Phase: Implementation
Ensure that your application is free of cross-site scripting issues, because most CSRF defenses can be bypassed using attacker-controlled script.
Phase: Architecture and Design
Generate a unique nonce for each form, place the nonce into the form, and verify the nonce upon receipt of the form. Be sure that the nonce is not predictable (CWE-330).
Note that this can be bypassed using XSS.
Identify especially dangerous operations. When the user performs a dangerous operation, send a separate confirmation request to ensure that the user intended to perform that operation.
Note that this can be bypassed using XSS.
Use the ESAPI Session Management control.
This control includes a component for CSRF.
Do not use the GET method for any request that triggers a state change.
Phase: Implementation
Check the HTTP Referer header to see if the request originated from an expected page. This could break legitimate functionality, because users or proxies may have disabled sending the Referer for privacy reasons.
Other information
No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, csrf, csrfSecret] was found in the following HTML form: [Form 1: "edit-search-block-form--2" "edit-submit--2" "form_build_id" "form_id" ].
Reference
•	http://projects.webappsec.org/Cross-Site-Request-Forgery
•	http://cwe.mitre.org/data/definitions/352.html
9.	Private IP Disclosure
Low (Medium)
CWE Id : 200
WASC Id : 13
Description
A private IP (such as 10.x.x.x, 172.x.x.x, 192.168.x.x) or an Amazon EC2 private hostname (for example, ip-10-0-56-78) has been found in the HTTP response body. This information might be helpful for further attacks targeting internal systems.
•	URL: https://xxxx.ac.in/library/resource/books
•	Method: GET
•	Evidence: 10.0.0.16:8380
•	URL: https://xxxx.ac.in/sitemap.xml
•	Method: GET
•	Evidence: 10.248.106.220
•	URL: https://xxxx.ac.in/library
•	Method: GET
•	Evidence: 10.0.0.16:8380
•	URL: https://xxxx.ac.in/library/our-team
•	Method: GET
•	Evidence: 10.0.4.9
Instances: 4
Solution
Remove the private IP address from the HTTP response body. For comments, use JSP/ASP/PHP comment instead of HTML/JavaScript comment which can be seen by client browsers.
Other information
10.0.0.16:8380
10.0.0.16:8380
Reference
•	https://tools.ietf.org/html/rfc1918
10.	Secure Pages Include Mixed Content
Low (Medium)
CWE Id : 311
WASC Id : 4
Description
The page includes mixed content, that is content accessed via HTTP instead of HTTPS.
•	URL: https://xxxx.ac.in/library
•	Method: GET
•	Evidence: http://xxxx.ac.in/sites/default/files/library/jgate.png
•	URL: https://xxxx.ac.in/anti-ragging
•	Method: GET
•	Evidence: http://www.xxxx.ac.in/images/right.gif
Instances: 2
Solution
A page that is available over SSL/TLS must be comprised completely of content which is transmitted over SSL/TLS.
The page must not contain any content that is transmitted over unencrypted HTTP.
This includes content from third party sites.
Other information
tag=img src=http://xxxx.ac.in/sites/default/files/library/jgate.png
tag=img src=http://xxxx.ac.in/sites/all/themes/cmf/images/myaccount.png
tag=img src=http://xxxx.ac.in/sites/all/themes/cmf/images/archive.png
tag=img src=http://xxxx.ac.in/sites/all/themes/cmf/images/lblibrary.png
tag=img src=http://xxxx.ac.in/sites/all/themes/cmf/images/newarrival.png
tag=img src=http://xxxx.ac.in/sites/all/themes/cmf/images/new_wog.gif
Reference
•	https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet
11.	Information Disclosure - Debug Error Messages
Low (Medium)
CWE Id : 200
WASC Id : 13
Description
The response appeared to contain common error messages returned by platforms such as ASP.NET, and Web-servers such as IIS and Apache. You can configure the list of common debug messages.
•	URL: https://xxxx.ac.in/CHANGELOG.txt
•	Method: GET
•	Evidence: internal server error
Instances: 1
Solution
Disable debugging messages before pushing to production.
Reference
12.	Cross-Domain JavaScript Source File Inclusion
Low (Medium)
CWE Id : 829
WASC Id : 15
Description
The page includes one or more script files from a third-party domain.
•	URL: https://xxxx.ac.in/visitor-analytics
•	Method: GET
•	Parameter: http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics&domain=xxxx.ac.in&width=250&height=250&ana_type=pageviews
•	Evidence: <script type="text/javascript" src="http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics&domain=xxxx.ac.in&width=250&height=250&ana_type=pageviews"></script>
•	URL: https://xxxx.ac.in/visitor-analytics
•	Method: GET
•	Parameter: http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics-browser&domain=xxxx.ac.in&width=250&height=250&ana_type=browser
•	Evidence: <script type="text/javascript" src="http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics-browser&domain=xxxx.ac.in&width=250&height=250&ana_type=browser"></script>
•	URL: https://xxxx.ac.in/visitor-analytics
•	Method: GET
•	Parameter: http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics-referer&domain=xxxx.ac.in&width=250&height=250&ana_type=referer
•	Evidence: <script type="text/javascript" src="http://analytics.wrc.nic.in/cmfanalytics/widget?div=cmf-analytics-referer&domain=xxxx.ac.in&width=250&height=250&ana_type=referer"></script>
•	URL: https://xxxx.ac.in/visitor-analytics
•	Method: GET
•	Parameter: http://analytics.wrc.nic.in/cmfanalytics/widget?div=browser_cat&domain=xxxx.ac.in&width=250&height=250&ana_type=browser_cat
•	Evidence: <script type="text/javascript" src="http://analytics.wrc.nic.in/cmfanalytics/widget?div=browser_cat&domain=xxxx.ac.in&width=250&height=250&ana_type=browser_cat"></script>
Instances: 4
Solution
Ensure JavaScript source files are loaded from only trusted sources, and the sources can't be controlled by end users of the application.
Reference
13.	Server Leaks Information via "X-Powered-By" HTTP Response Header Field(s)
Low (Medium)
CWE Id : 200
WASC Id : 13
Description
The web/application server is leaking information via one or more "X-Powered-By" HTTP response headers. Access to such information may facilitate attackers identifying other frameworks/components your web application is reliant upon and the vulnerabilities such components may be subject to.
•	URL: http://xxxx.ac.in
•	Method: GET
•	Evidence: X-Powered-By: PHP/7.0.33
Instances: 1
Solution
Ensure that your web server, application server, load balancer, etc. is configured to suppress "X-Powered-By" headers.
Reference
•	http://blogs.msdn.com/b/varunm/archive/2013/04/23/remove-unwanted-http-response-headers.aspx
•	http://www.troyhunt.com/2012/02/shhh-dont-let-your-response-headers.html
14.	Absence of Anti-CSRF Tokens
Low (Medium)
CWE Id : 352
WASC Id : 9
Description
No Anti-CSRF tokens were found in a HTML submission form.
A cross-site request forgery is an attack that involves forcing a victim to send an HTTP request to a target destination without their knowledge or intent in order to perform an action as the victim. The underlying cause is application functionality using predictable URL/form actions in a repeatable way. The nature of the attack is that CSRF exploits the trust that a web site has for a user. By contrast, cross-site scripting (XSS) exploits the trust that a user has for a web site. Like XSS, CSRF attacks are not necessarily cross-site, but they can be. Cross-site request forgery is also known as CSRF, XSRF, one-click attack, session riding, confused deputy, and sea surf.
CSRF attacks are effective in a number of situations, including:
•	The victim has an active session on the target site.
–	The victim is authenticated via HTTP auth on the target site.
•	The victim is on the same local network as the target site.
 	CSRF has primarily been used to perform an action against a target site using the victim's privileges, but recent techniques have been discovered to disclose information by gaining access to the response. The risk of information disclosure is dramatically increased when the target site is vulnerable to XSS, because XSS can be used as a platform for CSRF, allowing the attack to operate within the bounds of the same-origin policy.
•	URL: http://xxxx.ac.in
•	Method: GET
•	Evidence: <form action="/" method="post" id="search-block-form" accept-charset="UTF-8">
Instances: 1
Solution
Phase: Architecture and Design
Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid.
For example, use anti-CSRF packages such as the OWASP CSRFGuard.
Phase: Implementation
Ensure that your application is free of cross-site scripting issues, because most CSRF defenses can be bypassed using attacker-controlled script.
Phase: Architecture and Design
Generate a unique nonce for each form, place the nonce into the form, and verify the nonce upon receipt of the form. Be sure that the nonce is not predictable (CWE-330).
Note that this can be bypassed using XSS.
Identify especially dangerous operations. When the user performs a dangerous operation, send a separate confirmation request to ensure that the user intended to perform that operation.
Note that this can be bypassed using XSS.
Use the ESAPI Session Management control.
This control includes a component for CSRF.
Do not use the GET method for any request that triggers a state change.
Phase: Implementation
Check the HTTP Referer header to see if the request originated from an expected page. This could break legitimate functionality, because users or proxies may have disabled sending the Referer for privacy reasons.
Other information
No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, csrf, csrfSecret] was found in the following HTML form: [Form 1: "edit-search-block-form--2" "edit-submit" "form_build_id" "form_id" ].
Reference
•	http://projects.webappsec.org/Cross-Site-Request-Forgery
•	http://cwe.mitre.org/data/definitions/352.html

15.	Information Disclosure - Suspicious Comments
Informational (Low)
CWE Id : 200
WASC Id : 13
Description
The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.
•	URL: https://xxxx.ac.in/content-awaited
•	Method: GET
•	URL: https://xxxx.ac.in/sites/all/modules/cmf/guidelines/js/script.js?q7cgqh
•	Method: GET
•	URL: https://xxxx.ac.in/acts/anti-sexual-harassment-cell
•	Method: GET
•	URL: https://xxxx.ac.in/misc/jquery-extend-3.4.0.js?v=1.10.2
•	Method: GET
•	URL: https://xxxx.ac.in/group/iqac-naac
•	Method: GET
•	URL: https://xxxx.ac.in/examinations
•	Method: GET
•	URL: https://xxxx.ac.in/misc/*.css$
•	Method: GET
•	URL: https://xxxx.ac.in/group/foreign-admissions
•	Method: GET
•	URL: https://xxxx.ac.in/sites/all/modules/contributed/jquery_update/replace/ui/ui/minified/jquery.ui.mouse.min.js?v=1.10.2
•	Method: GET
•	URL: https://xxxx.ac.in/library/our-team
•	Method: GET
•	URL: https://xxxx.ac.in/acts/placement-cell
•	Method: GET
•	URL: https://xxxx.ac.in/group/nirf-2018
•	Method: GET
•	URL: https://xxxx.ac.in/filter/tips/
•	Method: GET
•	URL: https://xxxx.ac.in/admissions/central-universities-common-entrance-test-cucet-2020-wwwcucetexamin
•	Method: GET
•	URL: https://xxxx.ac.in/sites/all/modules/contributed/admin_menu/admin_devel/admin_devel.js?q7cgqh
•	Method: GET
•	URL: https://xxxx.ac.in/sites/all/modules/contributed/jquery_update/replace/ui/ui/minified/jquery.ui.core.min.js?v=1.10.2
•	Method: GET
•	URL: https://xxxx.ac.in/misc/jquery.js?v=1.4.4
•	Method: GET
•	URL: https://xxxx.ac.in/annual-accounts-and-reports
•	Method: GET
•	URL: https://xxxx.ac.in/library/inter-library-loan-service
•	Method: GET
•	URL: https://xxxx.ac.in/?q=admin/
•	Method: GET
Instances: 158
Solution
Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.
Other information
The following comment/snippet was identified via the pattern: 
The following comment/snippet was identified via the pattern: 
Reference
16.	Timestamp Disclosure - Unix
Informational (Low)
CWE Id : 200
WASC Id : 13
Description
A timestamp was disclosed by the application/web server - Unix
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=admin
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/?q=filter/tips/
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/library/resource/theses-dissertations
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=node
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/user/login
•	Method: GET
•	Evidence: 20100101
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/blue?destination=themes/%2A.css%24
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/academic-program
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/library/awarness-service
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/group/internal-committees-university
•	Method: GET
•	Evidence: 20100101
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/green?destination=node/88273
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/default?destination=profiles/%2A.js%24
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/acts/rti
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/filter/tips/
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=user/logout
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/orange?destination=filter/tips
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/?q=node/add/
•	Method: GET
•	Evidence: 20100101
•	URL: https://xxxx.ac.in/news-and-events
•	Method: GET
•	Evidence: 37253726
•	URL: https://xxxx.ac.in/styleswitcher/switch/cmf/custom/purple?destination=node
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/acts/notifications
•	Method: GET
•	Evidence: 31536000
•	URL: https://xxxx.ac.in/acts/nss-cell
•	Method: GET
•	Evidence: 31536000
Instances: 340
Solution
Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.
Other information
31536000, which evaluates to: 1971-01-01 05:30:00
Reference
•	https://www.owasp.org/index.php/Top_10_2013-A6-Sensitive_Data_Exposure
•	http://projects.webappsec.org/w/page/13246936/Information%20Leakage
17.	Information Disclosure - Suspicious Comments
Informational (Low)
CWE Id : 200
WASC Id : 13
Description
The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.
•	URL: http://xxxx.ac.in
•	Method: GET
Instances: 1
Solution
Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.
Other information
The following comment/snippet was identified via the pattern: 
The following comment/snippet was identified via the pattern: 
Reference
18.	Timestamp Disclosure - Unix
Informational (Low)
CWE Id : 200
WASC Id : 13
Description
A timestamp was disclosed by the application/web server - Unix
•	URL: http://xxxx.ac.in
•	Method: GET
•	Evidence: 20100101
•	URL: http://xxxx.ac.in
•	Method: GET
•	Evidence: 31536000
Instances: 2
Solution
Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.
Other information
20100101, which evaluates to: 1970-08-21 20:51:41
Reference
•	https://www.owasp.org/index.php/Top_10_2013-A6-Sensitive_Data_Exposure
•	http://projects.webappsec.org/w/page/13246936/Information%20Leakage

