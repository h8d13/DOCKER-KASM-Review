# KASM DOCKER COMBO QUICKSTART

Step 1. Do not install Dokcer any other way than specified on their official docs. (Snap, flatpaks, etc those will not work because Cocker needs to at lowest seat level.)

https://docs.docker.com/engine/install/ubuntu/#os-requirements

Chech KVM type (Intel vs AMD) and compatibility too.
Add source, keyrings, run post install hello world test. You know the drill.
 
---

Step 2. Kasm

Downloaded Kasm put in on my desktop extract. Then simply in terminal same directory > `./install.sh` 

Note: It might throw errors if you haven't installed all the necessary stuff, follow their instructions.

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

![image](https://github.com/user-attachments/assets/4b43f5d1-9ec2-4bbf-b167-57de0b111f9f)

![image](https://github.com/user-attachments/assets/a3c3803c-ffce-41f7-86b3-6716091ea590)


Step 3. Have fun! 

This is both a fun way to share but also a seems like there is quite a bit of security, performance options. 

They also have fun pre-installed images like Doom or RetroArch if you're not that much into dev :)

There is also extensible scripting you can do directly through the interface: For examples see: https://kasmweb.com/docs/latest/how_to/running_as_root.html

---

Then the second step you will need is probably some kind of persistence. 

They've procided a friendly example ont he website 

```
/mnt/kasm_profiles/
├── admin@kasm.local
│   ├── chrome
│   └── firefox
└── user@kasm.local
    ├── chrome
    └── firefox
```

Useful in dashboard sessions > Delete stop etc 

GO back to work spaces set the profile path.

I simply entered: /mnt/kasm_profiles/{username} 

When you go back you should now have this new option:

![profile_launch_option](https://github.com/user-attachments/assets/a6dfd0a8-4af1-4b0e-ad78-2b4c10884e97)

You can test by closing your session and creating a hello folder on the desktop. Also trying to access from another device. Cool!

If you've set up groups you might have to play around with perms as it's designed for sysadmins. 

Edit Group > Persistent Profile > Check

---
You can try to add to your docker run config: 

```
{
  "hostname": "kasm",
  "user": "root",
  "privileged": true
}
```

It might not be recommended on larger systems but gives host capabilities. 
You can also check GPU access by going into chrome: ```chrome://gpu```

Another thing you can do is: 
```
apt-get install -y glmark2
glmark2
```

If you're getting consistent high FPS, your set up might be good! I got 500 fps on an old Nvidia card, not sure how relevant. 

----
Working with PyQt

Had to export the path manually: 

```
export LD_LIBRARY_PATH=/home/kasm-user/Desktop/Code/REPO/venv/lib/python3.12/site-packages/PyQt5/Qt5/lib:$LD_LIBRARY_PATH
```

I guess this is due to non-standard paths or something I'm not 100% sure. It's okay but not amazing because of framebuffers using VNC. 



---
That's it folks! 

If you plan to run this on bare metal (making a cloud retro or something)
```Go to Infrastructure > Docker Agents```

Give the desired amount of RAM/Cores
Do the same for the VM itself. 

I also recommend going to your host machine settings: Find your power or sleep settings:
Put it to: when inactive: do nothing. But keep the turn off screen option so you can save some power while keeping your server online.  

The interface feels great to work with, congratz on the UI to the devs because it feels intuitive for such a long subject. I've always loved virtual machines, servers, but this kind of just ties it all together. 

