---
layout: post
title: TweetCast v0.1
---


### My experiment for creating a chrome extension that lets users broadcast beautifully crafted content cards using their content to twitter.

<div class="message">
  This will be a blog posts series explaining my implementation of the new chrome extension that I have started developing. The idea behind the extension is obtained from a iOS app called <a href="http://getcite.io/" target="none">cite</a>, a big shout out and kudos to the app's team for implementing a great idea, do check out their app its awesome. The base idea is the same with some extra features that I plan to implement.
</div>

----

# Idea & Use case:
The main idea behind the extension is: when a user browsing web finds something interesting and whishes to share it to his/her followers, the follwing ways are already available: 

1. Look for a twitter share button
    * This will fail if a users just wants to share part of the text
2. Open twitter and post the link/tweet about it
    * This will fail in the sense this is very tedious since a user has to fit the whole idea into 140 characters including the links and stuff.

With the above reasons the use case of the extension TweetCast comes to light. A user just has to select the text he wishes to broadcast and pressing a keyboard shortcut the text will be automatically read by the extension and the extension will generate a image card with the text along with the name of the source in the image. So the user just need's to add the tweet's content and the extension will then automatically post a tweet with the image attached to that tweet.

# What's in v0.1:

I won't be dwelling deep into any technical details. I will be just mentioning stuff and if possible any resources that I have followed. There aren't any huge sci-fi stuff implemented, everything implemented in this version can be found out by effective use of google.

The technical things in this version are: 

1. Recognizing user command i.e keyboard shortcuts (Ctrl + Shift + F/Command + Shift + F) to open the extension and copy the selected text from the browser window into the extension [Technical Stuff: chrome.command; DOMContentLoaded event; chrome.tabs.query; chrome.tabs.sendMessage; chrome.runtime.onMessage].
2. From the copied text create an canvas element using HTML5 canvas and then using the canvas inbuilt toDataURI method convert the canvas to base64 encoded png image uri.

### You can view the [v0.1 Screenshot](https://dl.dropboxusercontent.com/u/29921236/TweetCast%20gifs/app_v0.1.gif) for a better understanding of the extension.

----

# What to expect in future versions & blog posts:

There are two major ways to interact with twitter API (we need to use the API since we are posting on behalf of the user):

1. The hard way which is to implement the functionalities inside the extension itself.
2. The easy way which is to create a backend server which handles our tokens, API interactions etc.

The hard way as the name suggests is **HARD** since I haven't found much useful documentation/examples to interact with twitter from an extension, but I was able to salvage bits and pieces which I now have to fuse together to complete the implementation (more information in future blog posts). In the easy way the major hurdle would be to connect the user info from the backend server with the extension. After user authentication using twitter. I have to implement a method to directly use the data uri for image upload instead of downloading the image and then uploading it. Final thing would be to use a users access token obtained from authentication and upload media, post a tweet linking the uploaded media.

---

Finally to sum up this post, I wouldn't have gotten the idea without the cite iOS app. I have implemented the capturing user content and creating an image from that content. Need to implement the so called backend/twitter interaction. The code will be **open-sourced** once I reach a critical point in the development. As always if there are any questions/suggestions shoot me a mail (mailid available in my [website](http://rajeev-reddy.com)).

----- 
