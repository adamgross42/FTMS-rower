# PoC documentation

## The goal
I have a rowing machine and found about the app "Kinomap". I liked the concept of watching videos of boats rowing in the water while rowing. But I had that before with watching this videos on youtube. The main feature which stood out from the app is, that the video playback speed gets adjusted based on your workout performance. The culprit of the app is, that the company wants to sell you a high priced (personal opinion) abonnement for using the app. So I want to create my own app which does the same. I do not need a fancy interface or community features or challenges or whatever.  
So the goal is, to create a solution, which can connect to my rowing machine and can adjust playback speed of videos.


## The research
First I asked my friends on #selfhosted:matrix.org if they know of an already existing solution, before reinventing the wheel. It seems that noone was aware of any kind of software this niche.  
So then I looked more into, what it needs to connect any device to my rower, and read training data from it. I found out, that it is called FTMS, which stands for FiTness Machine Service protocoll and is widely used by many training device manufacturer and seems to be industry standard.  
The next step was to search github for everything related to FTMS and rowing machines. I found quite a lot, which surprised me. Also I found an interesting repo from Alex Tomberg, which seems as a good starting point for me. The basic functionality to connect to my rowing machine and reading basic data seems to be implemented.  


## The first steps
Ok, so I found a minimalistic starting point, in Alex' repo and cloned it and tried it out. But it did not work, the training stats were not displayed. After a quick debug, I found out that my rowing machine sends two responses, while the second one seems to be invalid (have to check that later, maybe those two need to be combined?). So I quickly adjusted the code, to filter that out.  
Tada - it is working :)  
![picture](https://git.kmpr.at/kamp/FTMS-Rower/raw/commit/31d3722901d83f19e72cb33a61ee68664689b391/docs/concept-1.png)

Now I need to put a video player into the page, found video.js for that, where the playback speed can be controlled. Without further assessment, I want to use it and see what I can do with it.  
Also quickly downloaded a random rowing video from youtube for that purpose, Someone rowing in my home country on the lake "Grundlsee".  


## Video.js
I use the latest release of Video.js, version 8.19.1.  
To include it in the existing project, only a few steps were required:  copy the video.min.js and video.min.css into the project folders and include some code in the index.html file.  
Stay tuned for further updates...  
