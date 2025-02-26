# KASM-DOCKER-Tutorial-Linux

Step 1. Do not install Dokcer any other way than specified on their official docs. (Snap, flatpaks, etc those will not work because Cocker needs to at lowest seat level.)

https://docs.docker.com/engine/install/ubuntu/#os-requirements

Chech KVM type (Intel vs AMD) and compatibility too.
Add source, keyrings, run post install hello world test. You know the drill.
 
---

Downloaded Kasm put in on my desktop extract. Then simply in terminal same directory > `./install.sh` 
Now we can naviguate to `https://localhost:443` Where we will find a security warning (self-signed) go to Advanced > Proceed. 

At the end of the install script you will get credentials, make sure to save them somewhere safe. 

Once you're in you can also use the Access Management to change these or create new users. 


You can chose a workspace which will trigger Kasm update and download of said workspace. 
It is interesting to note that Kasm devs directly tell you how much the image will take on disk, which is neat. 

They also have a registry section, this let's you access stuff like other Docker images that are available on the web. 

I decided to try OpenSuse as many have been recommending to me but never had the chance (too much in love with Debian systems.)
I was suprised at how smooth this felt, I thought that there would be a lot more overhead to running such things in browser. 


They also have this neat control panel that has everything you would need for VMs. Has been very well thought-out. 
Overall, this app seems to do a great job at simplifying something that is complex by default. Which is amazing. 

---






