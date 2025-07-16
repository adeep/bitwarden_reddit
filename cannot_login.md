## Contents

TBD

## Foreword

This guide is based on https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188/4.

That version is in turn based on
[_another older post_](https://community.bitwarden.com/t/how-to-master-password-problems-and-best-practices/43282).

Thanks to [@grb](https://community.bitwarden.com/u/grb), [@DenBesten](https://community.bitwarden.com/u/denbesten),
[@Neuron5569](https://community.bitwarden.com/u/neuron5569) and [@dh024](https://community.bitwarden.com/u/dh024),
whose contributions on the
[Community Forum](https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188)
have served as inspirations for this post!

Kudos to [Nail1684](https://community.bitwarden.com/u/Nail1684/summary); any mistakes are doubtless mine, not his.

## Introduction

Oh no! You can't log into your vault. What could be the problem?

First, the bad news: you are going to have to run some experiments to find out what the problem is.

Even worse, there is a chance that you have entirely lost the contents of your vault. If you have not made
preparations in advance, you may be forced to 
[delete your vault](https://bitwarden.com/help/forgot-master-password/) and 
[start over](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md).

If you are reading this, and you still have access, please create an
[emergency sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md).
You can go further and actually create a
[full backup](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md).
That is more work; if you are overwhelmed, please do at least create the emergency sheet.

## Where is your backup?

> Where are we going, and why I am I in this handbasket?

An [Emergency Sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md)
is your rescue in a number of simple situations:

* You forget your master password (that's right; you cannot trust your brain to remember _anything_);
* Your vault is secured via [TOTP](https://en.wikipedia.org/wiki/Time-based_one-time_password), the
TOTP app is on your phone, and your phone slipped and fell under the wheels of a passing bus;
* Your vault is secured via a FIDO2 security key, but your security key is lost or broken.
* You _are DEAD_, and your husband needs to get into your vault to pay the electric bill

...and so forth. An emergency sheet presumes that your credential datastore is intact, but you cannot open it
and use it.

A [full backups](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) 
goes one step further: what if the cloud copy of your credential datastore is lost or corrupted?
How could that happen?

* You fumble-finger an update to a vault entry, damaging or deleting it, and you don't notice until months have passed;
* A malicious ex or teenager gains momentary access to the Bitwarden backing email and explicitly 
  [deletes your vault](https://bitwarden.com/help/forgot-master-password/).
  (A lot of people are astonished to hear that the security of this backing email leaves this minor Achilles heel.
  This in addition to the critical messages from Bitwarden such as unusual activity on your account.)
* The Earth opens up and swallows the Bitwarden datacenters, so there is literally no copy on any cloud server.

If you cannot log into your Bitwarden vault, and you do not already have a backup, _you are in disaster recovery_.
Your first priority should be to recover and save as much data as possible.

In the next section, we will outline how to do that.
This is your first priority, and the rest of this document will assume you have made as much of a backup
as you can.

## Making an Export

Bitwarden has an
[export function](https://bitwarden.com/help/export-your-data/).
There are some things you should be cognizant about exports in general:

* Exports require that you are still logged into Bitwarden in at least one client.

* Exporting your vault requires the master password. 
  If your login problems include
  an issue with your master password, you won’t be able to use the export function. Again, you
  need to export everything manually. 

* Exports do not contain [Sends](https://bitwarden.com/products/send/) or any items in the trash.

Bitwarden exports are either in CSV or JSON format.

* CSV exports do not contain file attachments, cards, identities and passkeys.

* JSON exports are best.
  If possible, use the encrypted password-protected ones. _Do not use the
  "restricted" export format._
  However, unencrypted JSON exports are acceptable in this situation, since you are already in disaster recovery.

* If you have an organization/collections, you have to export those separately via the
  [admin console](https://bitwarden.com/help/export-your-data/#export-an-organization-vault) in the web vault.

If you cannot use the Bitwarden export function, _but you still have access to an unlocked Bitwarden client_:

* Unplug that device from the network. 
  If it is a mobile device, put it in "Airplane Mode".
  If it is a desktop, unplug your Ethernet cable or otherwise disconnect it from the rest of the world.
  The risk is that a Bitwarden client may act strangely when it talks to the server and log you out.

* Grab pen and paper. In a quiet private place, go through each and every entry in your unlocked vault.
* Copy every single entry onto your paper.
* Write neatly.
* Pay close attention to the differences between "0" (zero) and "O" (capital oh), "1" (one), and "l" (small ell),
  "5" (five), and "S" (capital ess) and so forth.
* Take your time! Double-check your work.


* If your exports have missed an item, do whatever it takes to manually copy the data to another place.

_For the rest of this guide, we assume that you have made a backup, if you can.

## Are you "locked"? "logged out"? Something else?

([What’s the difference between locking/unlocking and logging in?](https://bitwarden.com/help/unlock-with-pin/#understanding-unlock-vs-log-in))

If you are merely "locked", you need to unlock your current Bitwarden client. This is not a server problem. There
are three common possibilities here:

*   ([Unlock with PIN](https://bitwarden.com/help/unlock-with-pin/) -- you must have set this up in advance;
*   [Unlock with Biometrics](https://bitwarden.com/help/biometrics/) -- you must have set this up in advance;
*   Unlock with your master password -- this is always allowed.
*   You may also have access via a [passkey](https://bitwarden.com/help/login-with-passkeys/).

Look closely; is your client asking for your _master password_,
or for your _PIN_ (only applicable when unlocking)? 
These are not interchangeable; the PIN won’t work when
you’re asked for your master password (and vice versa), and you cannot _ever_ log in with your PIN alone.

If unlocking with your master password does not work, either your Bitwarden client has gone sideways (not
common, but possible), or (horror of horrors!) you have forgotten your master password.

## An Ounce of Prevention

> Barn door? Needs to be closed?

Not specifically on topic, here are some additional thoughts to try to prevent this from happening again.

* Schedule the backups of your vault.
  These won’t prevent a “lockout scenario” _per se_, but if you ever
  have a login problem or a “lockout” from your Bitwarden account, then you will still have most or all of your
  important data, and be able to restore that data to a new vault.

* Set a timer/task/reminder for every three, six, or even twelve months to make an export of the vault.
  More info to exports: see [First Steps](#2-first-steps).

_Set up Two Factor Authentication now_

In addition to being a smart cybersecurity measure, if you set up 2FA it will bypass potential problems with
the Bitwarden "new device verification", which can cause a "circular lockout" problem. Just make sure to
include your 2FA recovery information in your full backup.

_Emergency Access_

Bitwarden [Emergency Access](https://bitwarden.com/help/emergency-access/) may also help.
Note this requires
a paying Bitwarden subscription, and there is a mandatory waiting period before someone will have access
to your vault.

_Login With Passkey_

You can add a backup login method for the Bitwarden account via
“login-with-passkey”-passkeys, ideally “with encryption.
This makes it possible to login without entering
the master password and without your 2FA or “new device verification” code.
These login-passkeys with encryption depend on a PRF capable browser, the “passkey-wallet”
(i.e. where you store that passkey) and the OS must support their creation.
Currently “login-with-passkey” is still in Beta and only possible for login to the web vault.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> But, 
as nice as additional login-passkeys to your Bitwarden account/vault are: currently, those 
Bitwarden-login-passkeys don’t replace your master password. Some critical actions still need a 
master password confirmation (like changing the master password and exporting the vault). Do not rely 
solely on Bitwarden-login-passkeys (for now).

## Is it your Bitwarden client?

> It's not me, honey, it's you.

If you cannot log in via your Bitwarden client, the question remains whether this is just on one device or
widespread. 
Again, make sure you have a backup (if you can) before you proceed.

* _Try to log in to the web vault_ ([vault.bitwarden.com](https://vault.bitwarden.com/) for the US server region
  or [vault.bitwarden.eu](https://vault.bitwarden.eu/) for the EU server region).
* 
* If you aren't certain which one you created your account on, try them both!

* Try to log in with _different browsers_. 
* Try using a _private/incognito browser session_.
* Try _deleting the browser cache_.
  <img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
  Only  delete the cached browser content. 
  _Do not delete your browser cookies_.
  Losing your browser cookies at this point could case Bitwarden to "forget" your device as a "known device", which
  might lead to you needing [new device verification](https://bitwarden.com/help/new-device-verification/) or 2FA on your account.
* Try _uninstalling the Bitwarden client and installing a fresh version_. There seem to be multiple situations where
  an existing Bitwarden client can get confused after an upgrade. If you are currently logged with that client,
  _do not uninstall the client until you have [made an export](#1-before-you-start)_.

* Try to log in via other [Bitwarden app(s)](https://bitwarden.com/download/).
* Try to log in via _other devices and other networks_ (that is, Wi-Fi versus cellular).

* On mobile devices: Try _turning off Wi-Fi temporarily_, i.e. changing to cellular. Or vice versa.
  This might “solve” some network and/or IP address problems.

* For all devices in your local network: restart the router.
  This might resolve some network addressing issues.

* If you use a VPN: turn it off (or on), (at least temporarily).

These experiments will tell you, at a high level, whether the problem is with a single Bitwarden client or
a single one of your devices.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> When 
trying to login “too often”: the Bitwarden servers 
[will require CAPTCHA verification](https://bitwarden.com/help/security-faqs/#q-how-can-i-protect-my-bitwarden-account-from-brute-force-attacks) 
after 9 failed login attempts from an unknown device”, so be careful with your attempts.

* _If the problem is across more than one Bitwarden client_ you should focus on things that have a
  kind of “general approach”.
* _If
  it’s a problem with only one app and/or device_, you probably can focus on more “narrow” measures regarding that
  particular setup.

## Checking the Server

* Are _the Bitwarden (US/EU) servers are temporarily down_? This could happen during
  a planned server update. Look at the [Bitwarden Status Page](https://status.bitwarden.com/).
  [Downdetector](https://downdetector.com/status/bitwarden/) is also a good crosscheck to see if other users
  are also having a problem.

* See if your server is down by trying to load the "web vault" page directly:
  [vault.bitwarden.com](https://vault.bitwarden.com) or [vault.bitwarden.eu](https://status.bitwarden.com/).
  Note these two servers are _not_ interchangeable.
  You need to know which one has your account.
  If you are not sure, try them both!

* If you cannot load the page for your web vault, wait until you can before trying anything else.
  In this situation, you should consider making an [export](https://bitwarden.com/help/export-your-data/) if
  do not already have one.

* _If you’re self-hosting_, verify your own server _is functioning correctly_.  It is possible your
  login problems due to local errors misconfigurations of your self-hosted Bitwarden server.
  These issues are out of the scope of this guide). But please do verify you have the _latest server version_
  installed. (“New” client versions and “old” server versions do get incompatible eventually!)

## Email and/or Master Password

At this point, you believe that the Bitwarden servers are functioning, but you still cannot log in,
especially via the web vault.
What's next?

* _Verify your email address and master password_.
  Look at your
  [emergency sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md).
* Did you set a "master password hint"? If so, it's time to request it.

> Pro tip: many people use the master password hint to remind them where they stored their emergency sheet.

* Perhaps _you changed your email address and/or master password_?
  And worse, didn’t update your emergency sheet?
  Step back, relax, take a walk, get a cup of coffee.
  Perhaps it will come back to you in a moment.

* _Look for any typos in your email address and/or master password_, especially silly typos or more obvious
  ones like _0 (zero) versus O (capital letter “oh”)_, _l (small “L”) versus I (capital letter “i”)_,
  or _| (special character “vertical bar”)_.
* _Look for added or missing spaces_: trailing spaces, leading spaces or double spaces within your master
  password. The discrepancy could be either when you were typing it in or when you created the
  master password.

> For the email address, Bitwarden doesn't care whether you use lower case letters or upper-case letters,
> so whether you try to login with example@example.com or EXAMPLE@EXAMPLE.COM – both should work exactly the
> same. This is not true for the master password!

_Special Characters_

Do you have _problematic special characters_ in your master password?
Non-ASCII, Unicode, or Emoji characters may work on one system but not on other systems.
You should only use (at most) the 95-character
[printable ASCII character set](https://commons.wikimedia.org/wiki/File:ASCII-Table-wide.svg)
for master passwords. Other characters can even fail on your current system after a
system upgrade.

The safe character set consists of:

* capital letters A-Z
* small letterts a-z
* numerals 0-9
* the space character
* ! (exclamation point)
* " (double quote)
* \# (octothorpe, a.k.a. "pound", "hashtag", or "sharp")
* $ (dollar-sign)
* % (percent)
* & (ampersand)
* ' (apostrophe)
* ( (left parenthesis)
* ) (right parenthesis)
* \* (asterisk, a.k.a "star" or "splat")
* \+ (plus)
* , (comma)
* \- (dash)
* . (period, or "dot")
* / (slash)
* : (colon)
* ; (semicolon)
* < ("less than")
* = (equal)
* \> ("greater than")
* ? (question mark)
* @ (at-sign)
* ^ (carat)
* _ (underscore)
* \` (back tick)
* ~ (tilde)

> Note that although these characters are acceptable in a Bitwarden master password, be aware
> that other websites may have trouble with some of the above characters.

If you can log in to your web vault, but not to another one of the Bitwarden apps, you
may have a problematic special character in your master password.
Consider changing your master password
to one that only has the 95-character ASCII characters just described.

If you change your master password, consider using a 4-word passphrase, generated by Bitwarden itself,
such as `polka-fame-curled-either-passover` or `WinnerPlasmaKabobSinuous`. If you want extra security, have
Bitwarden add a word (or two) to the passphrase _instead of_ punctuation or special characters. Punctuation and
special characters do not add as much security as an extra word, and it makes the master password harder to memorize
and harder to type.

_Autocorrect Issues_

Beware of autocorrections by your keyboard(s)/app/device. You may not easily spot this, especially
since password input may be obscured. Even if you stick to the 95-character ASCII set, as recommended above,
some characters may get autocorrected by your keyboard/app/device:

* Some systems will replace straight-quotes with curly-quotes (i.e., “smart-quotes”, such as "&ldquo;", "&rdquo;",
  "&lsquo;" and "&rsquo;"). MacOS is especially notorious for this.
* You may have inserted a "." (period/full stop) and/or invisible spaces after pressing the “space-bar”.
* Some systems will automatically change a
  typed lower-case letter into an upper-case letter or vice versa.
* On iOS: _deactivate smart punctuation_, since that can “autocorrect” characters you type in
* In general, all kinds of apostrophes and quotation marks (', ", `, ´, ‘, ’, ‛, “, ”, ‟) may be
  autocorrected into a different form preferred by the device you are typing on.

* _Turn off autocorrect_, if possible. Try to _change your (virtual or physical) keyboard_.
* Make your _keyboard input is visible_ if possible.
* Type it more carefully (look at your hands!).
* Use the _on-screen visible keyboard_
  such as the [Character Map](https://support.microsoft.com/en-us/topic/how-to-use-special-characters-in-windows-documents-ec1a4e84-706e-67a5-e52b-e3ebab90313f)
  in Windows.
* Consider composing the password in a text editor such as `Notepad` or `TextEdit` and then pasting it into your
  login form.

## Other Login Issues

* Did you change your 
  [KDF settings](https://bitwarden.com/help/kdf-algorithms/) from the default? 
  If so, do you use default settings for Argon2 or PBKDF2?
  Consider temporarily switching your KDF settings back to the default.

> Especially on iOS, the Argon2 settings can be “too high” → change them to the default values (at least for
> “memory”)
> (<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
> make an export before you change the KDF settings!)
According to Bitwarden: “iOS limits app memory for autofill. Increasing memory from the default 64 MB may result in errors while unlocking the vault with autofill.”

## Application hangs or crashes, or otherwise acts inexplicably

If your Bitwarden app consistently crashes or has other inexplicable behavior:

Beware that uninstalling the Bitwarden mobile app, desktop app and browser extension will make those apps
“unknown devices” for Bitwarden again, requiring the email login verification code due to the new device
verification and login protection. This is critical if you have failed to enable 2FA on your
vault; make sure you have access to your email account, where you will get the email verification codes.

1. Uninstall the app, (Do not worry if you cannot "log out" before doing the uninstall.)
2. Delete the local storage of the app--make sure the uninstall did not leave traces of the app on your system.
3. Reboot your device,
4. Reinstall the app from a fresh download.
5. Try to log in again.

You can create a new post to get further help. Try to describe the problem as detailed as possible,
what exact error message you get (ideally with a screenshot, but make sure to blur any personal and
sensitive data), maybe what you already tried (and didn’t work) etc.

And you can always contact [Bitwarden support](https://bitwarden.com/contact/).

If you believe you have found a bug--you have “other” or “weird” error messages--you can also report it on
GitHub ([here](https://github.com/bitwarden/clients/issues) for the browser extension, desktop app,
web vault and CLI, [here](https://github.com/bitwarden/android/issues) for the Android mobile app and
Android Authenticator app, and [here](https://github.com/bitwarden/ios/issues) for the iOS mobile app and
iOS Authenticator app…)


## Lost Password or Lost 2FA

If you have truly lost your password, then--unfortunately--there is no super-duper sneaky secret back door
to get back into your vault.
Bitwarden can neither reset your master password nor “circumvent” it in any way.

Simplified explanation: the Bitwarden master password does not only “authenticate” you; it is also a
major factor in the encryption of your vault. Without the master 
password--and Bitwarden doesn’t have your master password due to its zero-knowledge-architecture--your vault 
cannot be decrypted. This is also why, as long as your master password isn’t available, it 
cannot be reset or changed by anyone else.

Your only remaining hope is if you can remember the master password or even “guess it”.
If you think, there may be a chance of remembering or “guessing” it, then take your time.
Even a few days--maybe you will remember it. Sometimes it is good to sit down and focus on it, and sometimes
it is good to stop thinking about it for a few days…

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
When you try to log in “too often”: Be aware, that the Bitwarden servers e.g. “[…] will require CAPTCHA verification after 9 failed login attempts from an unknown device”, so be careful (and as “accurately” as possible") with your attempts, before getting “slowed down”…

If it doesn’t come back to you, then eventually it’s time to delete the account you have lost access to… (see the previous section for details about that).

_If you have truly lost your Bitwarden account_,
[you can delete your Bitwarden account](https://bitwarden.com/help/forgot-master-password/) as long as
you have access to the email address you used.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
Make sure you exported your data beforehand, if possible;
account deletion is not reversible. Your next step will be to create a new account and hopefully 
import/restore your most recent backup/export. Again, see if you can export your data;
see [First Steps](#2-first-steps).

## Was I "hacked"?

Sometimes when someone cannot log into their password manager, they believe they "must have been hacked".
Let's look at that more closely.

For the purpose of this discussion, I will assume you have a strong master password (unique, complex, and
randomly generated) as well as good 2FA on your vault (a FIDO2 hardware security token or a TOTP app).

The overwhelming odds are that you _did this to yourself_. Yes, there are exotic attacks out there that you
might be helpless against, but they are extremely rare. One report indicates that the entities that deploy
these sophisticated attacks charge $250,000 _per person_.

If you really have malware, the overwhelming odds are _you downloaded and installed it_. This can be from a bad download
from the Google Play Store, intentionally downloading a "hack" or "cracked" game, or perhaps incautiously opening
a strange or unexpected email attachment.

_Why the password manager?_

If an attacker wanted to plunder your bank accounts and other assets, they would make sure it took you as long as
possible to discover the breach. They want as much time as possible. Modifying the login for your password
manager is close to the bottom of the list of things they would do.

They might co-opt your Amazon account, for instance, to deliver merchandise to a drop location or initiate
a "brushing scam".

They might modify the login to a social media account in order to publish illegal content (and avoid you removing it quickly).

The one exception to this might be a spiteful ex-spouse who is looking to cause you grief _by denying your
access to your own secrets_. Outside a real corner case like this, an attacker modifying your vault is not a
likely scenario.
