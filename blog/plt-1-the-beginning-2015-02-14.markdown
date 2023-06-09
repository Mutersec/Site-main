---
title: The Saga of plt, Part 1
date: 2015-02-14
series: plt
---

The following is adapted from a real story. Parts of it are changed to keep it
entertaining to read but the core of the story is maintained. I apologize that
this issue in the epic will be shorter than the others, but it gets better.

The Beginning of The Interesting Pain
-------------------------------------

It all started when I got this seemingly innocuous PM on Freenode:

```
2015-01-23 [18:32:48] <plt> Hello. I am writting a new ircd and can I have the channel ##ircd please?
```

This is a fairly common event on larger IRC networks, especially given the
length of the channel name and the fact that it references IRC daemons
specifically. At this point I had *forgotten* I owned that channel. So
naturally I decided to give it a join and see if the person who requested the
channel was worthy of it or had brought enough activity to it such that it was
morally correct to hand it off.

This was not the case.

```
[18:33:54] *** Joins: Xe (xe@unaffiliated/xe)
[18:34:02] <plt> Hello xe.
[18:35:17] <plt> Xe the project name pbircd.
[18:37:09] <plt> Xe the project site is http://sourceforge.net/p/pbircd
```

In case the site is removed from SourceForge, it is the default sourceforge
page.

After taking a look at this and then getting off the call with my family I was
on at the point, I decided to reply.

```
[20:30:49] <Xe> plt: I've decided against giving you my channel
[20:31:03] <Xe> you have no code in your repo.
[20:31:31] <plt> I am currently working on the project. Can I help you in the channel?
[20:32:04] <Xe> if you are working on it
[20:32:11] <Xe> I'd expect to see at least something
[20:32:25] <Xe> for example: https://github.com/Xe/scylla
[20:32:35] <Xe> that's mostly autogenerated code and makefiles, but it's something
[20:33:31] <plt> Take a look at this http://pastebin.com/F8MH3fSs
[20:34:04] <plt> You know it takes a while to write ircd code.
[20:34:16] <Xe> I don't see any commits
[20:34:20] <Xe> not even framework code
[20:34:24] <Xe> or design
[20:34:26] <Xe> or an outline
[20:34:30] <Xe> all I see is that pastebin
[20:34:39] <Xe> which is in no way connected to that git repo
[20:35:07] <plt> I am still adding more features so its not going to be posted on the main web site yet.
```

The contents of the pastebin looked like a changelog, but that pastebin has
since expired or was explicitly deleted. He was all talk and no game. I admit
at this point I was pretty tired and frustrated, so I told him off:

```
[20:35:19] <Xe> fucking commit it then
[20:35:52] <plt> I was going to wait until the code was completed.
[20:36:43] <Xe> yeah good lick then
[20:36:45] <Xe> luck*
[20:37:14] <plt> Itgoing to get done and I am the only one working on the project so what do you expect?
[20:37:29] <Xe> to be able to look at the in-progress code?
[20:39:24] <plt> The code will do you no good because you will not be able to compile it.
[20:39:51] <Xe> then you have nothing
[20:40:06] <plt> I am not required to approve it.
[20:41:08] <plt> I can post the run program on the web site.
[20:42:33] <Xe> then do that
[20:43:28] <plt> Done.
```

The "run program" was nothing but a wrapper around the nonexistent binary for
pbircd and seemed to be compiled in a language that doesn't respect assembly
functions and all of the forms of RE that I know how to do were useless. If you
know how to better do RE on arbitrary binaries please let me know.

```
[20:44:12] <Xe> there are binaries
[20:44:15] <Xe> not source code
[20:44:25] <Xe> this is what you use git for
[20:44:35] <plt> The source code will do you no good since you can not compile it.
[20:52:02] <plt> In order for you to compile it you need the encryption program and I am not going to release the source code.
[20:54:43] <Xe> lol
[20:55:34] <plt> The program is freeware and I have no obligation to release the code under the License agreement.
[21:00:56] <Xe> you also will get no users
[21:03:13] <plt> The company that wrote Conferenceroom has a lot of customers.
```

ConfrenceRoom was a company that made a commercial IRC daemon. They have lost
to Slack and other forms of chat like HipChat. Note here that he says "you can
not compile it". This is true in more ways than you would think. He also claims
it is Freeware and not full fledged open source software. As someone who is
slightly proactive and paranoid after the Snowden bullshit, I find this highly
suspect. However, this "encryption program" was something I was oddly most
interested in.

```
2015-01-24
[12:11:14] <plt> Xe why do you always demand to see the source code?
```

Curiosity? To learn from other people's ideas? To challenge myself in
understanding another way of thinking about things? To be able to improve it
for others to learn from? Those seem like good reasons to me.

```
[22:46:33] <plt> PBIRCD is a irc daemon.
[22:46:36] <plt> Hello xe
```

The `PB` in that name will become apparent later.

```
[23:09:31] <plt> Would you like to see what I have in the updates?
[23:09:40] <Xe> sure
[23:09:47] <plt> http://pastebin.com/2udHPSyP
[23:13:10] <plt> Tell me what you think about it?
[23:16:32] <plt> I need to take a short break.
```

Again, the paste is dead (I should really be saving these gems) but it was
another set of what appeared to be patch notes.

```
[23:22:37] <plt> Do you like what I have in the notes?
[23:23:49] <Xe> I still think it's ridiculous  that you don't have the balls to release your code
[23:24:36] <plt> I understand what you telling me.
[23:25:48] <plt> There is no way to working around protecting the encrypted information.
[23:34:19] <plt> Why are you do want to see the code?
[23:43:36] <plt> Xe The encryption is used to encrypt the Operators, Link and the other passwords.
```

This sounds suspect. Any sane system of encrypting passwords like this would be
a mathematical one-way function. By not showing the code like this, is this
a two-way function?

```
2015-01-25
[00:05:55] <plt> Xe Question if the authors that wrote free pgp do not release their source code then why should I have do
```
