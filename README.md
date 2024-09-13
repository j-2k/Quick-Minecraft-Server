# Quick-Minecraft-Server
A quick MC guide because I encountered some issues I had never experienced before. Maybe I will also try to just make a quick setup method like 1 button! That would be fun.

**Contents**
1. Pre-requisites
2. Server Setup Guide
3. Port-Forwarding

After step 3 the server should be working!

# 1. Pre-requisites (Java Development Kit)
- Make sure to have the latest-lts Java dev kit or whatever is latest on the Java dev kit download page ***(It is especially important you get the latest versions in the case you want to play the latest verisons of minecraft java edition!)***.
- You can download it here first > https://www.oracle.com/java/technologies/downloads/
  - Choose your correct operating system first in the downloads section.
  - I'm on Windows, so I got the x64 installer in the Windows tab.
- If you come across issues/java linkage issues later on when the server starts you can read more about a java linking error I recieved when running my server by scrolling down or by clicking [here](#javalinkage) to take you down to where I talked about my java linkage issue! 

# 2. Server Setup Guide
1. Choose a Server!
  - Vanilla / Optimized Vanilla + Plugins
    - Vanilla MC Server (1/5, Worst/Should never be used)
    - CraftBukkit (2/5, Decent/Bad)
    - Spigot (2-3/5, Decent/Better than CraftBukkit)
    - Paper (3-4/5, Basically a performant Spigot) - [Papermc website](https://papermc.io/) with multiple performant different servers to choose from!
    - ~~Tuinity (5/5, Performance Based)~~ 1.17.x Paper Fork? - Archived Repository
    - ~~Airplane (5/5, Performance Based)~~ 1.17.1 Paper Fork? - Repository last commit dated 2 years ago
    - Purpur (4-5/5, Very good & Performant + has extra functionality)
  - Modded Servers
    - Fabric
    - Forge
  - Modded Client (Can be used to download server mod pack files from!)
    - CurseForge
    - ATLauncher (Performant + Better than CurseForge)
2. Setup guide!
  - Setup the chosen server
    -  X
  - Setup Port & IP
    - Y
  - Test Connection!
    - Z
3. Extra Notes & Custom Options!
  - Server RAM Allocation: ```java -Xmx1024M -Xms1024M -jar minecraft_server_name.jar```
    - ```-Xmx1024M``` this flag needs to be changed to dedicate different amounts of ram this is currently 1 GB.
    - If you have 16 GB+ of RAM and its a server for some friends just allocate 4 GB, and there should be no issues.
    - ```-Xmx4096M``` is 4 GB of ram dedicated to the server, which in most cases is more than good.
    - Going 2 GB (```-Xmx2048M```) in most cases is also fine but mainly for vanilla, 4 GB is suggested for modded. If you have more players you also need to increase the amount, these amounts though are good enough for now. You can also just search up the amount of ram needed for your requirements online.
  - Server Properties file:
    - This controls a large part of how the server works, so go through it and set the parameters to what you want, here are some examples.
    - ```pvp: false``` disables pvp
    - ```force-gamemode=false``` will not force a gamemode (ex. you would turn this on if you played an adventure map that required adventure mode)
    - ```server-ip=xxx.xxx.xxx.xxx``` IP for the server to run on
    - ```server-port=25565``` port for the server to listen to
    - ```resource-pack-prompt=``` if you play an adventure map you probably want to enter a custom message to how important getting the resource pack is
    - ```simulation-distance=10``` if players have major lag, you can reduce this value (it ranges from 3 - 32, 10 is the default), this is what it does > *Sets the maximum distance from players that living entities may be located in order to be updated by the server, measured in chunks in each direction of the player (radius, not diameter). If entities are outside of this radius, then they will not be ticked by the server nor will they be visible to players.*
    - Thats just a bunch of things that the file contains so go through it and customize your experience accordingly, if you are on a modded server you might want to check out the variables.txt file also!


# 3. Port-Forwarding
***These steps might be different for some people since not everyone has the same router brand, so it's a good idea to actually just look up a portforwarding guide on your specific router brand! But I made this since I just do it manually everytime & I came across a dumb issue with 2 routers that had me do an extra step I never had to do before!***
1. To get started open your terminal/command prompt. ***(Port Forwarding is easy, but there are some caveats like in my special case of 2 routers!)***
2. Paste in the command ```ipconfig /all``` then hit enter!
3. Find your connected network to the internet & in that section find these 2 entries ```Default Gateway: 192.168.X.XXX``` & ```IPV4 Address: 192.168.X.XXX (Preferred)``` (X is placeholder number as they are different, 192.168 "should" be constant) Note these 2 numbers down.
4. Open your browser of choice & paste the default gateway IP into the browser URL, here you need to enter your username & password, if you dont know them you should try the commonly used default usernames & passwords on routers which I put below! (Below I seperate the username on the left and the password on the right!)
  - Before you even start trying the usernames & passwords I put below, go to your router and check the underside panel of the router, in most cases a username and password is ALREADY listed on a small piece of paper glued to the bottom of the router, you should try that username & password first!
  - admin | admin
  - admin | *empty password, dont put anything in the password slot!*
  - username | password
  - ADMIN | ADMIN
  - You can look up a table of common usernames & password for your specific router by just googling it as well but one of these "should" work unless someone put a custom user & pass.
5. Assuming you now are logged in, you need to find where your port forwarding section is:
  - This is different for all routers, so either google your router or play around the tabs to find it, dont fuck up & change anything here thats on you, unless you know what you are doing.
  - Common places to look for are in the wireless tab &/OR NAT forwarding tab, in most cases the port forwarding section should be there somewhere.
6. Now if you are in the port forwarding page of your router, add a port entry. There is just 3 things that are important here you need to fill out.
  - External/Internal Port (Also called just Port on some routers): 25565
  - IP Address: Put your ```IPV4 Address: 192.168.X.XXX (Preferred)``` (Remember that 2nd number we noted down? put it here just the IP (the numbers))
  - Connection Type: TCP & UDP
  - You can also name this entry, put whatever you want I just put mctest.
7. Done! Now if you want your friends to connect to your server, just open your server first then go on google and search "what is my ip?" and copy that and google should list your public IP, give that IP to your friends, followed by 25565, so assume my public ip is ```269.69.420.100```, you give your friends ```269.69.420.100:25565``` (I think it isnt important to include the port iirc, so dont worry).
- IMPORTANT Extra Notes:
  - You should know the security risks that comes with exposing a port! So be mindful who you give the IP to!
  - YOUR PUBLIC IP AND IPV4 ADDRESS WILL MOST LIKELY CHANGE FROM TIME TO TIME (unless you have a static IP, in which I guess you already know what you are doing, but most have dynamic!). If your public IP changes, which is what showed up when you typed "what is my ip" into google, you need to give that new IP to your friends, some cases the IPV4 Address will also change, if that changes you need to enter your portforwarding tab in your router again in step 6 and edit the entry of the port that you forwarded & change IPV4 Address listed in there!

### Port forwarding on 2 routers!
This part messed me up & didn't think about it since I'm now connected to an extender/secondary router. An extra step is needed for forwarding a port on 2 routers. This part will not be very detailed, sorry it's a reminder for me.
1. The connection to be assumed: Internet -> Router 1 (Main) -> Router 2 (Extender/2nd Router) -> Device/PC.
2. Enter the gateway of Router 1 and port forward to the IPV4 address of Router 2, with port 25565 + both UDP/TCP.
3. Enter the gateway of Router 2 and port forward to the IPV4 address of the device running the server, with port 25565 + both UDP/TCP.
- It's simple but I didn't think of it ever since getting a extender, so I wasted some time untill I found the reddit post below!


## Other Issues:
- ### 2 Router setup/extender:
  - ![Screenshot_8](https://github.com/user-attachments/assets/a62c9783-85c0-477a-b342-90eeea320d76)
  - Thank god for this random guy because I didn't know I had to port forward the first router to the second one and the second router routes to my computer!

##

- ### <a name="javalinkage"> Java Versioning / Linkage Issues: 
Linkage errors occur when you have an outdated Java version compared to what the mc server is running on!
  1. First, open your desired terminal and paste the following ```javac -version``` & then ```java -version``` (my java -version displayed java 18 from 2022 which was outdated when trying to make an mc server on 1.21.1! javac and java -v commands didn't match either!)
  2. If you know you installed multiple Java versions I suggest you uninstall all of them and start fresh, I came across a conflict where Bash was detecting an old version and not using my latest versions!
    - Uninstall Java Versions on the Control Panel - If doing ```java -version``` now shows java isn't a recognized command or something along that line proceed to step 3.
    - Sometimes this isn't enough and doing ```java -version``` will still show an older java version (what happened in my case). This part is going to be annoying you need to find where Java is installed and delete the file manually, common places to look for are in: ```C:\Program Files``` ```C:\Program Files (x86)``` look for a file with the name of just "Java" you can press J in the file to skip to the J folders!
  3. Java DEVELOPMENT kit is needed, it will contain everything download it here first > https://www.oracle.com/java/technologies/downloads/
  - Choose your correct operating system first in the downloads section.
  - I'm on Windows, so I got the x64 installer in the Windows tab.
  4. Do the 2 commands again ```javac -version``` & then ```java -version``` if they match & show the newly installed version then its done!
    
##

- ### Inbound Rules/Firewall/Antivirus issues (Most likely not the case):
  - Make sure port 25565 isn't blocked.
  - Check javaw is allowed through the firewall for both public & private.
  - Make sure your antivirus isn't blocking java somehow (if you have windows defender it shouldn't block by default!).

##

### Port 25565 is taken/blocked
  - There are many reasons why this could be the case, but a very common mistake is running the server and you not noticing it ran with nogui and is running in task manager, always, and always run with bash and gui ON.
  - If that isn't the case you have something else running on that port! you should probably know what it is.
