---
layout: post
title: "2017 SANS Holiday Hack Challenge Writeup"
excerpt_separator: <!--more-->
date: 2017-12-30 13:13:37
youtubeId: olJAk8iRqUM
disqus: true
---

Its that's time of year again. The SANS Holiday Hack Challenge presented by Counter Hack Challenges and Friends. This year my write up will be a little different that last years.
But more on that a little bit later.

This year's challenged is called *Wintered: The Untold Story of the Elves of the North Pole* and can be found at [https://holidayhackchallenge.com/2017/](https://holidayhackchallenge.com/2017/).
![logo](/assets/images/holidayhack2017/HHC_banner.png)

<!--more-->

My write up this year will be done in multiple parts. This overview one you are reading and then additional entries for each question of the narrative and an entry for the terminal challenges. But before we dive into this years challenge, let me give you some perspective on my history with the Holiday Hack Challenge.


## Christmas Past 

### 2015
I first started doing CTF's in the Fall of 2015 when I began teaching at Hogwartz. I was offered the chance to work with Bits For Everyone (BFE for short) and the Cadet Competitive Cyber Team (C3T). I had tons of computer experience having three degrees in some computer field, a career as an Army communicatior, and as a webmaster and multi-language programmer. But I had never done a CTF. Once I started hacking in CTFs, I was hooked.

I did my first HHC in 2015 with the amazing [Gnome in your Home](https://holidayhackchallenge.com/2015/). I was not able to make it very far, as I only found one images needed to solve the mystery. I did complete all the challenges of the game portion but not all the hacking. It was an eye opening experience of doing a CTF in an emersive story driven and video game environment. I remember having to get my youngest to help find that darn _cookie_ in the Secret-Secret Room. I was delighted to actually tweet something during that CTF and have Ed Skoudis actually reply to it.  When the write up were posted, I read many of them to help learn better. My favorite (and the overall winner) was [Cory Duplantis](https://twitter.com/ctfhacker) and can be found on his excellent [blog](http://ctfhacker.com/ctf/pcap/pwn/web/2016/01/06/counterhack-holiday.html).

In March of 2016, I took [SANS SEC 560]() with Ed in Orlando. We loves to talk about HHC and I asked him all kinds of questions about that years challenge. Many people in the class were unfamiliar with the event, but I was fascinated so we spoke about it in detail. Ed and I had many mutual friends as he's always been a friend of the Army and Hogwartz on the Hudson specifically.

### 2016
When it came time for HHC 2016, I counted down the days and was ready. I spent most of the month of December after exams solving the entire challenge. I was able to accomplish all the in-game achievements and recover all the audio files to reveal the ultimate villain. While working on the puzzle, I even traded twitter DM's with Ed Skoudis and the last year's winner, Cory Duplantis. I published a full write up and submitted it on this [blog](http://wclaymoody.com/blog/2016/12/holiday-hack-challenge-writeup). When I got an email after my write up review from Tad Bennett, the Army Training with Industry intern at the time, I invited Tadd to come visit school and speak to the students and my team. To my surprise, I got an email back from Ed himself. Ed thought the visit was a good idea and wanted to come visit also. We arranged a visit for him during early January.

During his visit, we talked about many things catching up from my time in Orlando the previous March. One of the main topics we discussed was Holiday Hack and its ongoing success along with Counter Hack's continued participation in the Training with Industry program and the interns from the Army's Cyber and Signal Warrant Officer population. At the end of the visit, I asked Ed if he would be interested in having an Hogwartz Facutly member work with his team during the summer for a few weeks. He was interested and we promised to talk about it some more.

After some coordination between my academic department, the Army Cyber Institute, and Counter Hack Challenges, it was agreed that I would work with Counter Hack for about 5 weeks during the summer of 2017. As this coordination was on-going, the awards ceremony for HHC 2016 occurred. In a completely unrelated and coincidential occurance, I was selected as a _random_ prize winner of a super soft SANS Netwars T-shirt. You can see the results on the [winners page](https://holidayhackchallenge.com/2016/winners_answers.html) and the video below, jump to 11 minutes and 23 seconds left to hear my name.

<!-- {% include youtubePlayer.html id=page.youtubeIdi %} -->

## Christmas Present

So long story short (_too late_), I got to work with Counter Hack this past summer. My primary role was working on NetWars 5. I did beta testing, auto-solve scripting, hint authoring, and my most famous contribution, naming most of the problems. I have been called the NetWars punmaster for all the puns I put in the names. If you don't know what NetWars 5 is about, lets just say it takes place in a galaxy far, far away. I know a little about that universe also and it fit right in my wheel house. See this tweet from Derek Rook to Jeff McJunkin discussing some of those questions.

<!-- percent twitter https://twitter.com/_r00k_/status/930608702381584384 %}
-->

Maybe one day, I will blog about my work with NetWars 5 in the future. But for now, lets talk HHC.

Ed thinks about HHC all year long, in fact I think he has already said he knows what is going to happen in HHC 2018. Over the summer, Ed gave me the full run down on HHC 17. The story, the theme, the visuals, the technology of the game and even some of the challenges. I knew it was going to be great, I had some homework to do and had to watch a few movies to get caught up. The first thing I thought when reviewing Rankin and Bass _Rudolph the Red-Nosed Reindeer_ TV special was how Sam the Snowman looked like Heisenberg from _Breaking Bad_ whom many people tell Ed he looks like also. I am glad this little nugget made it into the opening narrative.

![Sam Heisenberg Skoudis](/assets/images/holidayhack2017/sam_the_snowman.png){:height="300px" width="300px"}

As November rolled around, I had been following what the team was doing on HHC but not envolved beyond some puns and ideas kicked around with the team over the summer. Then, Josh Wright asked me to do some front-end webdesign for one of the challenge websites. Ron Bowes had already done the heavy lifting on the [North Pole Police Department](https://nppd.northpolechristmastown.com). So I did the styling on the this website using the great lightweigth CSS framework [PureCSS](https://purecss.io/) and more specifically the [Landing Page](https://purecss.io/layouts/marketing/) layout. The main image on the website of the snowmobile police car was acquired from [Shutterstock](https://www.shutterstock.com/image-vector/snowmobile-car-parked-near-igloo-arctic-68095978). I went all out on this website from a Holiday Hack references, other Christmas themed events, and even some good old Southern 80s nostalga. More on that below.

When I finished up work on the NPPD site, I was asked to give the main game website a shot. This was a huge task and was much more difficult and essential part of the challenge. The frameworks for the site were already in place, and so I had to learn some new skills. Specifically, using the Bootstrap CSS framework in Less and the Ember Node.js platform. Evan Booth and Ron Bowse did amazing work on this site building the bones of the game, the stocking, the chat, the music integration. I just adding the color and style. I was not able to work fully on the site until completion and those guys fixed some of my errors and brought it home magically. I will talk about some of my favorite parts of the site below also.

### North Pole Police Department

#### Items of Interest

On the main page, I added a few shout outs in the Items of Interest Area.

*Nomination for Junior Deputy of the Year*
```
Josh and Jess Dosis have been recognized as the Junior Deputies of the Year for the past two years (2015 and 2016). If you want to nominate other deserving children or elves for this presigious award, completed packets are due by 11:59 PM on December 31, 2017.
```

This was a shoot-out to the heros of the past two Holiday Hack Challenges. Ed intentionally made the decision to not continue with the Dosis kids, but I thought they needed to get at least a mention. So here they are.

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

*Christmas Tree Fire Warming*

*Follow Us on SantaGram*


#### Siren

[Vlad and the NCSA team](https://www.holidayhackchallenge.com/2017/winners/ncsa/report.html#orgc497ad5) found this and included it in their writeup that was the [grand prize winner]((https://www.holidayhackchallenge.com/2017/winners_answers.html)) overall.

#### Meet the Sheriff

The [About](https://nppd.northpolechristmastown.com/about) page of the site was pretty much just one big pun. The Sheriff's name is R. Purvis Coaltrain. This is a spoof of the Sheriff on the Duke's of Hazzard. There is even mention of those darn Duke boys. There is a throwback to 2016 and SantaGram. Mention of the three wise men from the Fire Department (they came from a far). And finally an elf quote. Also, there is an Unix epoch time joke in there also. Like I said, its just one big pun.

The bottom of this page has a nice little hint about one of my most proud aspects of the site. It mentions the humans and robots that went into making the site functional. Its the only page with this footer, so it must mean something.

#### Robots and Humans

Most folks with a web pentest background know to check out the `robots.txt` file. Well, we got one of those also. This is full of Star Wars and NetWars jokes. Again, kudos to [Vlad and the NCSA team](https://www.holidayhackchallenge.com/2017/winners/ncsa/report.html#orgc497ad5) for catching this in their winning writeup.

```
User-agent: hk-47
Disallow: /
Disallow: /needhelp
Disallow: /infractions
Disallow: /community
Disallow: /about

User-agent: threepio
Sand-Crawler-delay: 421

User-agent: artoo
Sand-Crawler-delay: 2187
```

While building this site out, I stumbled upon the concept of a `humans.txt` file also. Read more about it [here](http://humanstxt.org). I decided to do one of those also. It starts with a nice blurb about Counter Hack Challenges, but then had a weird block like this...

```
789cd5584d6fc3200cbdfbd7acfb90bac30e8c4c1ada926aaa266de7494165d2ba5bca7efd804002
04f25172a087e8c5063f3b7e2e422518d18fcd7dbdc6036b11ad46860f88be72448188cf5cebc987
ac4647f57904979470c40c1953c8edcd65efc77d40649f5d9909b402fa04c6ef56c6edf58eacb437
b981dccddc3dcfcd4b9db50089648f5bfcd3843fbd23e3b66a4395dca697511bac8540b670055e01
6c483639a0bfdb9c054825d3035a62d49042a3e865297b55f47ed1c306b4c35908d886a019f8ad75
082cb050661f959a9e1f4c89c34c6640b31520954c0fe849f56e2fb0789a85b0342084a2e7a756cd
f846d6d95309f53a38192227683e022492e9012d082d0f884fa2ec51c00fb3095a6421bf5053214c
05a88d914a3ca430e704bd6035f57c42c9d11f29444f7a641efaeb5184a5011de261c241656411a1
7b806628402a999e4fd1b337d99a2b8950e1f665049d00e517cd7750fbc10e9841eca093205a9997
d121183940f3102091cc1ca0efb4daa38d6a8544630b04b3209ae92c58016ce00fa08c878ec8cf34
650710accc2c1230eb0a7ac96aea01ad0ee89a149f2dca56446c70167c6cc571fced8d314c0c51a2
79c86c3b5cd91957d00b53530fe80d29be68c597218c6e906a4d133163c339154c56967a05cd5e4d
738252bac3e8d64316f28b9f54d086a9c005c82091c0a09acfac054824d1f3b9dba33bd1b36ff522
51a87267db4b11d48bf80dce0a18dfc760e6c600b19ccf53e6ffd32691d5e8f800ffaf39e7fe
```

As someone who spends more time than I should look at weird strings and file (thanks [RunCode](https://runcode.ninja)!) I know that if I see `789c` I just know that is a hex encoding of a zlib compressed file.

Anyway that block is a hex encoded - zlib compressed - base64 encoded - ascii art image of a IBM punchcard ([read more here](http://www.wclaymoody.com/blog/2016/10/eko-party-ctf-2016-old-but-gold-writeup). The punchcard decodes to 

```
MADE WITH LOVE BY MADEYE MOODY PROF DEFENSE AGAINST THE DARK ARTS BFE 4EVA
```

My hacker handle is **madeye**, and teaching network security is like _defense against the dark arts_ and West Point is just like Hogwarts. BFE is [bitsforeveryone](https://www.bitsforeveryone.com) so, this was my calling (punch)card and shout out to my team and cadets back on the Hudson.


[The Three Stagers](https://www.holidayhackchallenge.com/2017/winners/the_three_stagers.pdf) in their write up that won Best Creative solved both the `robots.txt` and `humans.txt` (See "Appendix A – NPDD Humans.txt"). But the highlight of their submission (and maybe the whole stinking event) was their [spoof magazine](https://www.holidayhackchallenge.com/2017/winners/the_hack_magazine.pdf) featuring the image below. 

![](/assets/images/holidayhack2017/madeye-magazine.png)

They so get me. I had a copy of this printed in my office for over a year. Its crazy how such silly things can make you so proud.