# PoC documentation

## The goal
I have a rowing machine and found about the app "Kinomap". I liked the concept of watching videos of boats rowing in the water while rowing. But I had that before with watching this videos on youtube. The main feature which stood out from the app is, that the video playback speed gets adjusted based on your workout performance. The culprit of the app is, that the company wants to sell you a high priced (personal opinion) abonnement for using the app. So I want to create my own app which does the same. I do not need a fancy interface or community features or challenges or whatever.  
So the goal of this "thing" is, to create a solution, which can connect to my rowing machine and can adjust playback speed of videos.


## The research
First I asked my friends on [#selfhosted:matrix.org](https://matrix.to/#/#selfhosted:matrix.org) if they know of an already existing solution, before reinventing the wheel. It seems that noone was aware of any kind of software this niche.  
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
To include it in the existing project, only a few steps were required: copy the video.min.js and video.min.css into the project folders and include some code in the index.html file.  
```
<h2>Rowing video</h2>
<video id="rowing_video" class="video-js" controls preload="none" width="640" height="480" poster="video/posters/video.png" data-setup="{}">
	<source src="video/video.mp4" type="video/mp4">
	<p class="vjs-no-js">To view this video please enable JavaScript, and consider upgrading to a web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a></p>
</video>
```
So we have our training video embedded now, but we have to hit play ourselfes and it does not adjust its playback speed according to our training yet. So first, let's find out if we can start/pause/stop the video with our exercise. To do that, first I have to find out how to control the video.js from code. Then I have to find something in our training data, to figure out if training has startet, paused or stopped.  
For the first step, I figured out, to trigger play/pause/stop I should use the value for "Instantaneous Pace". It is 0 before training has started, is also 0 when paused and 0 too when training has stopped. So a good starting point, but to figure out the difference for pause/stop, I will need to have a closer look later.  

Now that we control the video basically via code, we want to turn off (either hide, like the picture-in-picture button) or disable (like the progress bar) user controls for the video playback. This is easily done by adding this to the javascript code in our index.html.  
```
const player = videojs('rowing_video');
player.bigPlayButton.hide(); //just don't show it
player.controlBar.playToggle.dispose(); //remove completely
player.controlBar.progressControl.disable(); //show, but disallow user to use it
player.controlBar.fullscreenToggle.dispose();
player.controlBar.pictureInPictureToggle.dispose();
player.controlBar.playbackRateMenuButton.disable();
```

But that does not prevent play/pause when I click on the video, so I had to add another piece of code to prevent users from controling the video playback.  
```
```
Stay tuned for further updates...  


## misc links for future things
https://www.tutorialspoint.com/how-to-speed-up-down-the-video-in-video-js-player
https://stackoverflow.com/questions/19112255/change-the-video-playback-speed-using-video-js