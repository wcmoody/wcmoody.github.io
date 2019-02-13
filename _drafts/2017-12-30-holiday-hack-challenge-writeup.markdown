---
layout: post
title: "2017 SANS Holiday Hack Challenge Writeup"
excerpt_separator: <!--more-->
date: 2017-12-30 13:13:37
youtubeId: olJAk8iRqUM
disqus: true
---

Its that's time of year again. The SANS Holiday Hack Challenge presented by Counter Hack Challenges and Friends. This year my write up will be a little different that last years.
But more on that a little bit laters.

This year's challenged is called *Wintered: The Untold Story of the Elves of the North Pole* and can be found at [https://holidayhackchallenge.com/2017/](https://holidayhackchallenge.com/2017/).
![logo](/assets/images/holidayhack2017/HHC_banner.png)

<!--more-->

My write up this year will be done in multiple parts. This overview one you are reading and then additional entries for each question of the narrative and an entry for the terminal challenges. But before we dive into this years challenge, let me give you some perspective on my history with the Holiday Hack Challenge.


## Christmas Past 

### 2015
I first started doing CTF's in the Fall of 2015 when I began teaching at Hogwartz. I was offered the chance to work with Bits For Everyone (BFE for short) and the Cadet Competitive Cyber Team (C3T). I had tons of computer experience having three degrees in some computer field, a career as an Army communicatior, and as a webmaster and multi-language programmer. But I had never done a CTF. Once I started hackign in CTFs, I was hooked.

I did my first HHC in 2015 with the amazing [Gnome in your Home](https://holidayhackchallenge.com/2015/). I was not able to make it very far, as I only found one images needed to solve the mystery. I did complete all the challenges of the game portion but not all the hacking. It was an eye opening experience of doing a CTF in an emersive story driven environment and video game environment. I remember having to get my youngest to help find that darn _cookie_ in the Secret-Secret Room. I was delighted to actually tweet something during that CTF and have Ed Skoudis actually reply to it.  When the write up were posted, I read many of them to help learn better. My favorite (and the overall winner) was [Cory Duplantis](https://twitter.com/ctfhacker) and can be found on his excellent [blog](http://ctfhacker.com/ctf/pcap/pwn/web/2016/01/06/counterhack-holiday.html).

In March of 2016, I took [SANS SEC 560]() with Ed in Orlando. We loves to talk about HHC and I asked him all kinds of questions about that years challenge. Many people in the class were unfamiliar with the event, but I was fascinated so we spoke about it in detail. Ed and I had many mutual friends as he's always been a friend of the Army and Hogwartz on the Hudson specifically.

### 2016
When it came time for HHC 2016, I counted down the days and was ready. I spent most of the month of December after exams solving the entire challenge. I was able to accomplish all the in-game achievements and recover all the audio files to reveal the ultimate villian. While working on the puzzle, I even traded twitter DM's with Ed Skoudis and the last year's winner, Cory Duplantis. I published a full write up and submitted it on this [blog](http://wclaymoody.com/blog/2016/12/holiday-hack-challenge-writeup). When I got an email after my write up review from Tad Bennett, the Army TWI intern at the time, I invited Tadd to come visit school and speak to the students and my team. To my surprise, I got an email back from Ed himself. Ed thought the visit was a good idea and wanted to come visit also. We arranged a visit for him during early January.

During his visit, we talked about many things catching up from my time in Orlando the previous March. One of the main topics we discussed was Holiday Hack and its on going success along with Counter Hack's continued participation in the Training with Industry interns from the Army's Cyber and Signal Warrant Officer population. At the end of the visit, I asked Ed if he would be interested in having an Hogwartz Facutly member work with his team during the summer for a few weeks. He was interested and we promised to talk about it some more.

After some coordination between my department, the Army Cyber Institute, and Counter Hack Challenges, I was agreed that I would work with Counter Hack for about 5 weeks during the summer of 2017. As this coordination was on-going, the awards ceremony for HHC 2016 occurred. In a completely unrelated and coincidential occurance, I was selected as a _random_ prize winner of a super soft SANS Netwars T-shirt.You can see the results on the [winners page](https://holidayhackchallenge.com/2016/winners_answers.html) and the video below, jump to 11 minutes and 23 seconds left to hear my name.

{% include youtubePlayer.html id=page.youtubeIdi %}

## Christmas Present

So long story short (_too late_), I got to work with Counter Hack this past summer. My primary role was working on NetWars 5. I did beta testing, auto-solve scripting, hint authoring, and my most famous contribution, naming most of the problems. I have been called the NetWars punmaster for all the puns I put in the names. If you don't know what NetWars 5 is about, lets just say it takes place in a galaxy far, far away. I know a little about that universe also and it fit right in my wheel house. See this tweet from Derek Root to Jeff McJunkin discussing some of those questions.

<!-- {% twitter https://twitter.com/_r00k_/status/930608702381584384 %}
-->

Maybe one day, I will blog about my work with NetWars 5 in the future. But for now, lets talk HHC.

Ed thinks about HHC all year long, in fact I think he has already said he knows what is going to happen in HHC 2018. Over the summer, Ed gave me the full run down on HHC 17. The story, the theme, the visuals, the technology of the game and even some of the challenges. I knew it was going to be great, I had some homework to do and had to watch a few movies to get caught up. The first thing I thought when reviewing Rankin and Bass _Rudolph the Red-Nosed Reindeer_ TV special was how Sam the Snowman looked like Heisenberg from _Breaking Bad_ whom many people tell Ed he looks like also. I am glad this little nugget made it into the opening narrative.

![Sam Heisenberg Skoudis](/assets/images/holidayhack2017/sam_the_snowman.png){:height="300px" width="300px"}

As November rolled around, I had been following what the team was doing on HHC but not envolved beyond some puns and ideas kicked around with the team over the summer. Then, Josh Wright asked me to do some front-end webdesign for one of the challenge websites. Ron Bowes had already done the heavy lifting on the [North Pole Police Department](http://nppdn rthpolechristmastows.com). So I did the styling on the this website using the great lightweigth CSS framework [PureCSS](https://purecss.io/) and more specifically the [Landing Page](https://purecss.io/layouts/marketing/) layout. The main image on the website of the snowmobile police car was acquired from [Shutterstock](https://www.shutterstock.com/image-vector/snowmobile-car-parked-near-igloo-arctic-68095978). I went all out on this website from a Holiday Hack references, other Christmas themed events, and even some good old Southern 80s nostalga. More on that below.

When I finished up work on the NPPD site, I was asked to give the main game website a shot. This was a huge task and was much more difficult and essential part of the challenge. The frameworks for the site were already in place, and so I had to learn some new skills. Specifically, using the Bootstrap CSS framework in Less and the Ember Node.js platform. Evan Booth and Ron Bowse did amazing work on this site building the bones of the game, the stocking, the chat, the music integration. I just adding the color and style. I was not able to work fully on the site until completion and those guys fixed some of my errors and brought it home magically. I will talk about some of my favorite parts of the site below also.

### North Pole Police Department

On the main page, I added a few shout outs in the Items of Interest Area.

*Nomination for Junior Deputy of the Year*
```
Josh and Jess Dosis have been recognized as the Junior Deputies of the Year for the past two years (2015 and 2016). If you want to nominate other deserving children or elves for this presigious award, completed packets are due by 11:59 PM on December 31, 2017.
```

This was a shotout to the heros of the past two Holiday Hack Challenges. Ed intentionally made the decision to not continue with the Dosis kids, but I thought they needed to get at least a mention. So here they are.

*Volunteers need for the Community Concert*
```
The NPPD is seeking volunteer elves or snowmen to volunteer during the annual post-Christmas concert. This year, we expect a record turnout as the NPPD Crime Scene Investigation Unit sponsors their favorite theme song band, The Who. 
```

The past two years the villian has been Cindy Lou Who and Dr. Who. People have joked over the last year thinking the villian might be the band "The Who". Since all the _CSI_ tv shows have featured a song from "The Who" as its theme, it would make sense they would be the favorite band of the NPPD Criminal Scene Investigators. 

| Show | Song|
|------|-------|
|CSI: Crime Scene Investigation|    "Who Are You"|
|CSI: Miami  |  "Won't Get Fooled Again"|
|CSI: NY  |  "Baba O'Riley"|
|CSI: Cyber  |  "I Can See for Miles"|
