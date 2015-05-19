---
layout: post
title: Ted Talks Similarity Index
---


### My experiment for creating a recommendation engine for all the TED Talks present out there.

<div class="message">
  I have been longing to write this post, for the past 3 weeks I have been working on this idea to create a recommendation system for ted talks using NLP and the talks manuscripts. I have been able to create a proof of concept app <a href="http://ted-sim-index.rajeev-reddy.com/" target="none">here</a>. In this post I will be explaining my implementation.
</div>

----

# Preface or Theory:
First the theroy behind the idea. I believe what a ted talk is nothig but a text manuscript of content, So as always we can use nlp to compare two or more taxt documents for similarity between them by checking for matching features between the documents. This is the primary theory based on which the idea and the proof of concept app is built on

# Implemantation Stuff:

Before going any further, I just want to put it out there this is just a proof of concept app, the code is available in github [link](https://github.com/drreddy/tedtalks-similarity-index). Any one can edit it, optimize it, can create their own spinoff.

I have followed the following steps during the development of this app:

1. First I have collected all the ted talks data from this handy [spreadsheet](https://docs.google.com/spreadsheet/ccc?key=0AsKzpC8gYBmTcGpHbFlILThBSzhmZkRhNm8yYllsWGc&hl=en#gid=0). I have parsed the sheet and stored the data in ElasticSearch.
2. To let user search on this data, I have tried to use direct strings but then decided to use tags available on the TED Talk page. This tags was obtained by scraping the site (I have done this thing very responsibly by giving hueg time interval gaps between requests).
3. Now with all the data availble, I have started creating a application using python tornado for my backend.
4. I have decided to not to download all the manuscripts of  ted talks (which were used to compare the talks) before hand but to access them as needed. So, tornado was my obvious choice since its non-blocking and also its written in python.
5. I used python as my primary language for this app because we can process the manuscripts easily in python using nltk and scikit.
6. I have preffered to use sockjs for persistent communication between server and client because as soon as server processes stuff it needs to push the response back to client and I felt web sockets is the best way to go.

----

Now I will be explaining the working steps of the app:

1. First a user selects a set of tags and presses search, upon which all the tags selected are sent to server using sockjs-client.
2. Upon receving tags the server searches the db and gets all the TED Talks with the tags and pushes the formatted data back to client.
3. Once the data is received, the data is shown in divs and the data is also stored in data-*(tags) on the client side.
4. The user can select various talks to compare them upon selecting and pressing the compare button, the selected talks data is sent to server.
5. The server on recieving the data, will get the manuscript for ach talk (async way) and then it compares all the ted talks against a talk and generates the similarity data.
6. The data is then pushed to client using sockjs-tornado.

### You can view the [App's Working Screenshot](https://db.tt/bbqWzHLZ) for a better understanding.

----

Finally I will be explaining the comparision procedure here:

1. Once all the manuscripts are retreived, A talk is selected as the main talk and the main text features (by excluding stopwords) present in this talks manuscript are extracted.
2. These features now become the basis for comparision, All the other manuscripts are checked for similar kind of features.
3. Based on the features matched a cosine similarity is calculated.
4. All the above things were implemented using nltk and scikit-learn.

---

I beleive that completes the full explanation of the app and the idea, Obviously the app can be improved in areas like:

1. User can search using string instead of using tags (which is implemented now).
2. Implement a CRON like service so that the data gets updated periodically.
3. Feature extraction and processing can be improved.
4. UI improvements and also Client side data validation.
5. Better algorithms for comparing the manuscripts.
 

I have just created this app to check whether it is physically possible or not to implement such a thing. So, this kind of nlp (document similarity detection) can be applied to any text material. As always if there are any questions/suggestions shoot me a mail (mailid available in my [website](http://rajeev-reddy.com)).

----- 
