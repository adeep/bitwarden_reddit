# A Password Journey

## Introduction

Back when I was starting out in software development, passwords were a very
different value proposition. We did all our work on large "timeshare" mainframes. This was the era of
Digital Equipment Corporation, TOPS-20, and similar machines.

Passwords in this era were pretty trivial. Our computers were inside of
large corporate offices, with many locked doors as well as 24x7 security guards. I may have had as many as two? three?
passwords. I typically wrote them on a piece of paper and left them in my wallet. 

If my wallet was lost or stolen, the passwords would not benefit a thief. Physical access controls aside,
they would also need to know WHICH machines to log into, and typically what username was used. If I forgot
my password as well, I could visit the IT admin on duty, who would happily reset my password.

The 1980s started a revolution in computing, where desktop computers went from a novelty to an essential
part of computing. We started out with very small IBM PCs (running DOS), until by the end of the decade we
were running SunOS and MentorGraphics workstations. Even by the advent of the 1990s, security and
disaster recovery were pretty much the same. To wit, physical access was still the prime protection for all
your computing resources.

## And then...THE INTERNET

Things got a lot more complex as the 1990s rolled on. We had dialup such as CompuServe, America Online, and
its related services. Even my places of employment started offering dialup: in the comfort of my own
spare bedroom, I could dial into my workstation at work or even other workstations or servers, such as a 
SPARCstation supercomputer. That slip of paper in my wallet now had as many a half a dozen or more passwords.
Usernames started to become non-obvious.

What if I lost my wallet? How would I even remember exactly which passwords I had on that piece of paper? Even
more concerning, some of those passwords might actually be useful if someone snagged that wallet and understood
what they were looking at. Something needed to change...

*My Palm III to the Rescue*

In a happy serendipity, this was the time I invested in my first personal digital assistant, a Palm Computing
[Palm III](https://en.wikipedia.org/wiki/Palm_III). In terms of computing, my Palm was a very limited (and
frustrating) device. It had very little storage. Its OS barely worked. It was so slow you wanted to stick your
foot out the door and help push it along.

But what it COULD do was...revolutionary. For the first time, I had my address book, calendar, task list, and even a
recent copy of my email sitting in my pocket. (You put the Palm into a special cradle, pushed a button, and
it synchronized with Outlook Express.) If I lost my Palm, I still had my data on my desktop device. I no longer
had to worry about losing a physical day planner.

So how did this help passwords? I [found an app](https://splashid.com/) that allowed my to store my passwords. Everything
was encrypted, so if my Palm III was stolen, the thief would still need a special password to read it. (Note the
Palm III didn't have a desktop password. If you got your hands on the device, you could read everything. But
this app ensured your secrets were safe.) Even better,
it integrated with my synchronization in Outlook Express; when I synchronized everything else, it would coordinate
the updates, and then I could even read that same database via my desktop.

By modern standards, this app was pretty basic. In modern terms, it was only a database of "secure notes". You
could open an entry called "AOL", and you'd see a small text document that would, for instance, have the username
and password for your online account.

But on top of everything else, it was pretty neat. If I updated my credential datastore, 
added a calendar event or updated a contact, I just made a mental note to sync the Palm as soon as I got home.
I didn't worry so much about my email, since my dialup service kept copies on their servers.

## But disaster recovery?

Even though this new system was a lot better, I got to thinking about the corner cases. I realized I still had
problems.

First, my backup copy was the hard disk on my Windows 98 machine. This device was shared by the entire family.
Security and backups were <ahem> limited. Kids could accidentally brick the OS or worse. And then...my house used a wood store as an auxiliary source of heat. Fire was plausible threat. (Though 
everyone in my family was pretty cautious, accidents do happen.)

So I added a step: after I synced my Palm, I would copy the Outlook Express datastore to a 3.5" floppy disk,
carry it to work, and store it--in a waterproof plastic bag--in a locked drawer at my desk. I knew we had fire
suppression at the office, and the likelihood of losing both the desktop machine at home and the office were remote.

Later I added a second 3.5" floppy, and kept that one in a fireproof box ([like this](https://www.amazon.com/SentrySafe-Resistant-Chest-Cubic-1160/dp/B008NHKWZU/ref=sr_1_6)).

## Time marches on...

As the 20-aughts went on, my credential store grew in size. More of a problem though, was the _number of devices_
I was using.  It was more than a PDA and a desktop machine. I had a laptop and a tablet (because I am a
voracious reader). I had a [Samsung S III](https://en.wikipedia.org/wiki/Samsung_Galaxy_S_III) instead of my Palm. 
Outlook Express was no longer so interesting, but I really needed my credential datastore on all these devices.

My password manager had matured quite a bit. It was still a secure notes app, but I could sync it locally-via wifi--on my
home intranet. No exposure to the Web, no wired connections, hooray! But it opened up another can of worms. If I updated
my Samsung while I was away from home, _I had to remember that_. If I made another change on my laptop, I would lose
an update if I tried to sync.  I was back to a single point of failure, and I could be my own worst enemy if I
got it wrong.  This was getting hard!

## Hooray, LastPass!

I started casting about for another solution and came upon [LastPass](https://www.lastpass.com/). This was before
their latest series of stumbles and fumbles. They had a free tier that seemed--at least at the time--to be a great
value proposition: LastPass operated as a cloud backing store, providing seamless high availability and data
recovery for all my devices.

LastPass also helped me raise my password security. They have an excellent [leaderboard](https://www.lastpass.com/features/security-dashboard) that
allows you to see your weak passwords and even gives you a relative security ranking against other LastPass users.
I went through and updated all my passwords to be strong (randomly generated), and a [passphrase](uhttps://xkcd.com/936/)
for my corporate laptop.

I didn't have to worry about a lost-update problem. Every time I made a change, the latest version was pushed
to the cloud, and every time I opened my vault, I got the latest version.

The browser integration in LastPass was also a real culture shock for me. Instead of having to dig into my
glorified "secure notes" app to find a password, LastPass would helpfully allow passwords to be "autofilled"
in my browser.

Backups consisted of copying the LastPass datastore--at a convenient time interval--onto removable media.
Again, I'd keep a copy at home and one at my office desk. But with the LastPass cloud storage, I didn't have
to worry about my phone dying before I got home. Heck, I didn't really have to worry (much) about a house fire
anymore...maybe?

## Uh-oh, my master password...

At this point I have to confess that the master password I had for about ten years was <ahem> quite weak. I had used
the same one for most of that time. Remember, at the start all of these computers were behind locked doors. And
at the end, someone would have to unlock my Samsung phone and/or break into my house and unlock my Windows
desktop.  The vault password was really secondary. I tended to use very simple master passwords like 
`xyzzyxyzzy` or `plughplugh`.

With exposure on the Internet, I clearly needed to do better. I never got attacked, but now I had a brand-new problem! What if I forgot my master password? I understood--based on my advanced degree in Information Science
Artificial Intelligence--that human memory could not be trusted.

At this point, the solution was obvious. I put a copy of the email address and master password on a piece of paper in
my fireproof safe, where either a family member or me could get to it.


## Moving to the present... 

It started when LastPass 
[stumbled](https://www.wired.com/2015/06/hack-brief-password-manager-lastpass-got-breached-hard/) in 2015.

Now, I will admit that this was not the _first_ time that LastPass had an operational error, but for me, it was
the last straw. I had been poised to become a paying user, and this got me looking alternatives. (Talk about
snatching defeat from the jaws of victory!)

Fortunately,
at almost the exact time, an [open source zero-knowledge alternative](https://en.wikipedia.org/wiki/Bitwarden) became available.
Even better, it was (and still is) free!

My journey since then has been serious dives into 2FA ([TOTP](https://en.wikipedia.org/wiki/Time-based_one-time_password)
and [FIDO2](https://en.wikipedia.org/wiki/FIDO_Alliance)) and [hardware security keys](https://www.yubico.com/).

I still worry a lot about fault tolerance and backups, but I feel I at least have a better handle on the problem.
Passkeys are still very rocky. I think the future is going to involve some interesting twists on password
sharing and reliability. The future is going to be interesting!


