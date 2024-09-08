# Quick-Minecraft-Server
A quick MC guide because I encountered some issues I had never experienced before. Maybe I will also try to just make a quick setup method like 1 button! That would be fun.

**Contents**
1. Pre-requisites
2. Server Setup Guide
3. Port-Forwarding

# 1. Pre-requisites
abcd

# 2. Server Setup Guide
abcd

# 3. Port-Forwarding
abcd

## Other Issues:
- ### 2 Router setup/extender:
  - ![Screenshot_8](https://github.com/user-attachments/assets/a62c9783-85c0-477a-b342-90eeea320d76)
  - Thank god for this random guy because I didn't know I had to port forward the first router to the second one and the second router routes to my computer!

##

- ### Java Versioning / Linkage Issues:
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
