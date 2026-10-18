# master-tv-server
Hindi TV Master: Setup Guide
18 Oct 2026 · @Vaibhav Trivedi
What you get
Hindi TV Master plays 742 Indian live TV channels in your browser: Doordarshan, news, movies, music, sports, cartoons, devotional and more. Each channel has several backup servers (1,628 in total), and the player switches to the next one by itself when a stream fails.
The zip hindi-tv-master.zip holds four files:
• server.js: the small program you run on your computer
• index.template.html: the player page
• data.json: the channel list and server links
• README.txt: a short version of this guide
Why you need to run a server
A plain web page cannot play most of these channels. Browsers block video requests to other websites, refuse plain http links on secure pages, and some channels check which site is asking. The server runs on your own computer, fetches each stream for the browser, and hands it over in a form the browser accepts. It listens only on your computer, so nobody else can reach it.
Setup on Windows
You do the first three steps once. After that, only steps 4 and 5 are needed each time you watch.
1. Install Node.js. Go to nodejs.org, download the LTS version, run the installer, and click Next on every screen with the default options. Restart your computer afterwards.
2. Unzip hindi-tv-master.zip. Right-click the zip, choose Extract All, and open the folder until you can see server.js in it.
3. Check that Node works. Click the address bar at the top of that folder, type cmd, and press Enter. In the black window type node -v and press Enter. A number such as v22.12.0 means it works.
4. Start the server. In the same black window type node server.js and press Enter. It prints Hindi TV Master running at http://localhost:8080. Leave the window open.
5. Open Chrome or Edge and go to http://localhost:8080.
Setup on Mac
1. Install Node.js from nodejs.org (LTS version) and open the installer you downloaded.
2. Double-click hindi-tv-master.zip to unzip it.
3. Open the Terminal app. Type cd  (with a space after it), drag the unzipped folder into the Terminal window, and press Enter.
4. Type node -v and press Enter to confirm Node works.
5. Type node server.js and press Enter, then open http://localhost:8080 in Chrome or Safari. Leave Terminal open.
Using the player
Start with Scan all channels at the top. It checks every channel and takes a few minutes. Working channels get a green LIVE tag and the rest get OFFLINE. Tick Hide offline to see only what plays.
• Genres are in the left list: Doordarshan, News, Movies, Music, Sports, Cartoons & Kids, Devotional, Knowledge, and Entertainment & Regional.
• Tick Hindi only to narrow the list to the 299 Hindi channels.
• Click a channel to play it. If a server fails, the player tries the next one and shows "server 2 of 5". It remembers the server that worked.
• Tap the star on a channel to add it to Favourites.
• Keys: left and right arrows change channel, / opens search, f goes fullscreen, m mutes.
• Use Copy stream URL to paste a channel into VLC if you prefer it.
Troubleshooting
Problem
Cause
Fix
node is not recognized
Node.js is not installed, or the window was open during install
Install Node.js, restart the computer, open a new black window
Cannot find module or file not found
The terminal is in the wrong folder
Open the terminal from inside the folder that contains server.js
Port 8080 already in use
Another program uses that port
Windows: set PORT=9000 then node server.js. Mac: PORT=9000 node server.js. Open http://localhost:9000
Page does not load
The server window was closed
Run node server.js again and keep the window open
Many channels show OFFLINE
Streams are geo-locked or dead
Run it from India or with an Indian VPN, then scan again
One channel will not play
All its servers are down
Try again later, or paste its URL into VLC
Limits
No setup can guarantee that all 742 channels play. The links come from the public iptv-org/iptv playlists and belong to the broadcasters, so any of them can go offline, change address or restrict viewers outside India. 143 of the Hindi channels have only one server, so nothing is left to fall back to if that link dies. Genres were assigned by channel name, so a few channels sit in the wrong list.
