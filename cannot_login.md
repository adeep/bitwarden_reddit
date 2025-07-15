This guide is based on https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188/4. 
Kudos to [Nail1684](https://community.bitwarden.com/u/Nail1684/summary); any mistakes are doubtless mine, not his.

## Introduction

“Unofficial Community Guide”
– from a user to other users, as I’m not a Bitwarden employee!

This is a collection of suggestions and tips for Bitwarden “login problems”. It is a collection 
of various possibilities. 

Go through this list, take your time, and you certainly don’t have to “study” everything in detail. 
Beware and be careful! If you are having login issues, you may be already in a “danger zone”.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
This post is mainly for individual, families or Teams accounts. Enterprise accounts have some different 
setups (such as SSO and account recovery) that are not part of this post.
For Enterprise accounts, contact your Enterprise organization administrator for help.

Parts of this guide are intentionally repeated. Some important topics, like mentioning exports/backups,
apply in multiple situations.

## Contents

[1. Before You Start](#1-before-you-start)
<br>
[2. First Steps](#2-first-steps)
<br>
[3. Simple Tests](#3-simple-tests)
<br>
[4. Advanced Tests](#4-advanced-tests)
<br>
[5. Getting Desperate...](#5-getting-desperate)
<br>
[6. Lost Password](#6-lost-password)
<br>
[7. An Ounce of Prevention...](#7-an-ounce-of-prevention)
<br>
[8. Credits](#8-credits)

## 1. Before You Start

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
_Depending on what exactly has happened, you may be in danger of losing access to your vault.
Proceed very carefully with everything you try and do -– including the things that are suggested here.

_If you are still logged in (whether “locked” or “unlocked”) in one or more Bitwarden apps_:

* _Stay logged in there_ -- do _not_ log out!
* _Disconnect_ the device from the internet.
* Do try to make an _export_ of your data. Use the 
[export function](https://bitwarden.com/help/export-your-data/)
if you can, else--if necessary--copy your contents out by hand. Worst comes to worst, this will ensure you have
not lost your data.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> When 
using the export function,

* This is only possible if you still have access to that function in at least one of the Bitwarden apps.

* Be aware that exports do not contain Sends and any items in the trash.

* CSV exports furthermore do not contain file attachments, cards, identities and passkeys.

* JSON exports are thus recommended, and preferably the encrypted password-protected ones. _Do not use the
"restricted" export format._
The unencrypted JSON exports are acceptable in this situation, since you are already in disaster recovery.

* If you have an organization/collections, you have to export those separately via the
  [admin console](https://bitwarden.com/help/export-your-data/#export-an-organization-vault) in the web vault.

* If your exports have missed an item, do whatever it takes to manually copy the data to another place..

* Exporting your vault requires the master password. If it your login problems include 
an issue with your master password, you won’t be able to use the export function. Again, you 
need to export everything manually. It bears repeating that an export is only possible if you still have 
access to an unlocked Bitwarden client. 


## 2. First Steps

Verify whether you are "locked" versus "logged out" in your app 
([what’s the difference between locking/unlocking and logging in?](https://bitwarden.com/help/unlock-with-pin/#understanding-unlock-vs-log-in)).

* If you’re _locked_, you must unlock locally with your chosen method(s) 
  ([Unlock with PIN](https://bitwarden.com/help/unlock-with-pin/), 
  [Unlock with Biometrics](https://bitwarden.com/help/biometrics/) or simply unlock with you master password).

* If you’re _logged out_, you must log in, which includes your registered email, your password, and your 
  2FA. There may also be a [new-device-verification-code](https://bitwarden.com/help/new-device-verification/). 
  You may also have access via a [passkey](https://bitwarden.com/help/login-with-passkeys/).

<img src="https://community.bitwarden.com/images/emoji/twitter/bulb.png?v=14" title=":bulb:" class="emoji" alt=":bulb:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> We 
focus on login problems in this post! (Unlocking problems are a separate issue.)

Make sure whether you are being asked for your _master password_ (possible for either unlocking or logging in) 
or for your _PIN_ (only applicable when unlocking). These are not interchangeable; the PIN won’t work when 
you’re asked for your master password (and vice versa), and you cannot ever login with your PIN alone.


## 3. Simple Tests

If you cannot login in via _one_ of the Bitwarden apps,

* _Try to login to the web vault_ ([vault.bitwarden.com](https://vault.bitwarden.com/) for the US server region 
or [vault.bitwarden.eu](https://vault.bitwarden.eu/) for the EU server region)

* If that doesn't work, try to login with _different browsers_. Also try a _private/incognito browser session_.
* Try _deleting the browser cache_.
  <img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
Only  delete the cached browser content, _not your browser cookies_. 
Losing your browser cookies at this point could case Bitwarden to "forget" your device as a "known device", which
might lead to you needing [new device verification](https://bitwarden.com/help/new-device-verification/) if
you neglected to enable 2FA on your account.

* Try to login via other [Bitwarden app(s)](https://bitwarden.com/download/).
* Try to log in via _other devices and other networks_ (that is, WiFi versus cellular).

<img src="https://community.bitwarden.com/images/emoji/twitter/bulb.png?v=14" title=":bulb:" class="emoji" alt=":bulb:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> This 
can show whether it is a _general_ login problem (when you can’t login anywhere)
versus a problem with a single app or device.

* _If the problem is across more than one Bitwaden client_ you should focus on things that have a 
kind of “general approach”. 
* _If 
it’s a problem with one app and/or device_, you probably can focus on more “narrow” measures regarding that 
app and/or device.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> When 
trying to login “too often”: the Bitwarden servers 
[will require CAPTCHA verification](https://bitwarden.com/help/security-faqs/#q-how-can-i-protect-my-bitwarden-account-from-brute-force-attacks) 
after 9 failed login attempts from an unknown device”, so be careful with your attempts.


## 4. Advanced Tests

* Have you tried the [Simple Tests](#3-simple-tests)?

_Checking the Server_

* Check whether _the Bitwarden (US/EU) servers are temporarily down_. This could happen during
a planned server update; start with the [Bitwarden Status Page](https://status.bitwarden.com/).
[Downdetector](https://downdetector.com/status/bitwarden/) is also a good crosscheck to see if other users
are also having a problem.

* See if your server is down by trying to load the vault page directly:
[vault.bitwarden.com](https://vault.bitwarden.com) or [vault.bitwarden.eu](https://status.bitwarden.com/).
Note these two servers are _not_ interchangeable. You need to know which one has your account.

* Did you choose the _right server region_ – US/.com or EU/.eu? These are distinct servers.
  They are not interchangeable. You must use the one that has your Bitwarden account.

* _If you are not sure which server region your account was created on_, try them both.

* If you cannot load this web page, wait until you can before trying anything else 
(except making an [export function](https://bitwarden.com/help/export-your-data/), if possible).

* _If you’re self-hosting_, verify your own server _is functioning correctly_.  It is possible your
login problems due to local errors misconfigurations of your self-hosted Bitwarden server.
These issues are out of the scope of this guide). But please do verify you have the _latest server version_ 
installed. (“New” client versions and “old” server versions do get incompatible eventually!)

_Email and Master Password_

* _Verify your email address and master password_. It's time to look at your 
[emergency sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md)! 
If necessary, consider getting your master password hint, if you have one.
(Pro tip: many people set 
the whereabouts of their emergency sheet(s) as their master password hint…)

* Perhaps _you changed your email address and/or master password_? 
And didn’t update that on your emergency sheet?

* _Look for any typos in your email address and/or master password_, especially silly mistakes or more obvious 
ones like _0 (zero) versus O (capital letter “oh”)_, _l (small “L”) versus I (capital letter “i”)_, 
or _| (special character “vertical bar”)_.
* _Look for added or missing spaces_: trailing spaces, leading spaces or double spaces within your master 
password. The discrepancy could either when you were typing it in or when you created the
master password.

> For the email address, Bitwarden doesn't care whether you use lower case letters or upper-case letters, 
> so whether you try to login with example@example.com or EXAMPLE@EXAMPLE.COM – both should work exactly the 
> same. This is not true for the master password!

_Special Characters_

Do you have _problematic special characters_ in your master password? 
Non-ASCII / Unicode characters may work on one system, but not on other systems.

We recommend only to use the 95-character ASCII set (or “less”) for master passwords to stay on the safe side, 
or rather to guarantee “cross-system-wide” compatibility:

* A-Z
* a-z
* 0-9
* The following special characters: `!"#$%&'()*+,-./:;<=>?@\`[~]^_{}|` and the "space" character

If you can log in to your web vault, but not to another one of the Bitwarden apps - you
may have a problematic special character in your master password. Consider changing your master password
to one that only has 95-character ASCII characters just described.
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
Start by exporting your vault 
before you change your master password! – see [First Steps](#1]2-first-steps).

* While you're changing your master password, consider using a 4-word passphrase, generated by Bitwarden itself, for
your master password.  For instance, `polka-fame-curled-either-passover`.

_Autocorrect Issues_

Beware of autocorrections by your keyboard(s)/app/device – you may not even notice it, especially 
since password input may be obscured! Even if you stick to the 95-character ASCII set, as recommended above, 
some characters may get auto-corrected by your keyboard/app/device):

* For example, replacing straight-quotes with curly-quotes (i.e., “smart-quotes”), or inserting a . 
(period/full stop) and/or invisible spaces after pressing the “space-bar”,  or automatically changing a 
typed lower-case letter into an upper-case letter (or vice versa)…

* In general, all kinds of apostrophes and quotation marks (', ", `, ´, ‘, ’, ‛, “, ”, ‟) may be 
autocorrected into a different form preferred by the device you are typing on.

* _turn off autocorrect_ if possible. Try to _change your (virtual or physical) keyboard_. 
  Make your _keyboard input visible_ if possible. Make sure you input the exact character. Use the _on-screen visible
  keyboard_. If those things don’t help, change your master password in the web vault to one that contains only 
  the 95-character ASCII set, or better yet a 4 word random passphrase without any special characters at all.
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> Again, 
  make an export/backup before changing your master password; see [First Steps](#2-first-steps).
  * On iOS: _deactivate smart punctuation_, since that can “auto-correct” characters you type in

_Other Login Issues_

* On mobile devices: Try _turning off WiFi temporarily_, i.e. changing to cellular. 
(–> this might “solve” some network and/or IP address problems)

* For all devices in your local network: restart the router. 
(–> this might also “solve” some network and/or IP address problems)

* If you use a VPN: turn it off (or on). (at least temporarily…)

* Have you changed your KDF settings from the default? If so, do you use default settings for Argon2 or PBKDF2? 
If not, maybe try to set your KDF settings to the default values.
(<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
Make an export before you change the KDF settings!)

> Especially on iOS, the Argon2 settings can be “too high” → change them to the default values (at least for 
> “memory”) 
> (<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
> make an export before you change the KDF settings!)
 According to Bitwarden: “iOS limits app memory for autofill. Increasing memory from the default 64 MB may result in errors while unlocking the vault with autofill.”

* If your Bitwarden app has a crash or other inexplicable behavior,

  * <img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> But 
  proceed with caution, make a backup/export if you still can – more info to exports: see [First Steps](#2-first-steps).

  * Also, beware: uninstalling the Bitwarden mobile app, desktop app and browser extension make those apps 
  “unknown devices” for Bitwarden again, requiring the email login verification code due to the new device 
  verification / login protection. This is critical if you have failed to enable 2FA on your
  vault – make sure you have access to your email account, where you might get the email verification codes.

  * Uninstall the app, (Do not worry if you cannot "log out" before doing the uninstall.)
  * delete the local storage of the app,
  * reboot your device,
  * reinstall the app,
  *  try to log in again.
  

## 5. Getting Desperate...

   Here is [_another older post_](https://community.bitwarden.com/t/how-to-master-password-problems-and-best-practices/43282) 
   that might give you insights.

   You can create a new post to get further help. Try to describe the problem as detailed as possible, 
   what exact error message you get (ideally with a screenshot, but make sure to blur any personal and 
   sensitive data), maybe what you already tried (and didn’t work) etc.

   And you can always contact Bitwarden support.

   If you believe you have found a bug -- you have “other” or “weird” error messages -- you can also report it on 
   GitHub ([here](https://github.com/bitwarden/clients/issues) for the browser extension, desktop app, 
   web vault and CLI, [here](https://github.com/bitwarden/android/issues) for the Android mobile app and
   Android Authenticator app, and [here](https://github.com/bitwarden/ios/issues) for the iOS mobile app and 
   iOS Authenticator app…)

   Another consideration: Did you also get "login-" or “attempted-login” emails from Bitwarden 
   you can’t explain? If yes - and it wasn’t you yourself who logged in or tried to login - … 
   in combination with login problems - and when nothing else resolves those - 
   you should take into consideration, your account may be compromised. But first make sure those mails 
   aren’t “fake Bitwarden” or even phishing mails – and still, most login problems are probably not due to 
   compromise.

   _If you have truly lost your Bitwarden account_,
   [you can delete your Bitwarden account](https://bitwarden.com/help/forgot-master-password/) as long as 
   you have access to the email address you used 
   (<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
   but make sure you exported your data before that, 
   if still possible – account-deletion is not reversible!) - before that or after that, you 
   can create a new account, and hopefully import/restore your most recent backup/export for that
   More info to exports: see [First Steps](#2-first-steps).


## 6. Lost Password

If you have truly lost your password, then – unfortunately – there is no way around that… 
Bitwarden can neither reset your master password nor “circumvent” it in any way.

<img src="https://community.bitwarden.com/images/emoji/twitter/bulb.png?v=14" title=":bulb:" class="emoji" alt=":bulb:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> Simplified 
explanation: the Bitwarden master password does not only “authenticate” you, but is also a
   major factor in the encryption of your vault. Without the master password – and Bitwarden doesn’t have your master password due to it’s zero-knowledge-architecture – your vault can’t be decrypted… And that’s also why, as long as your master password isn’t there, it can’t be resetted or changed for another on.

   Your only chance that remains would be to remember the master password again – or to “guess it”… 
   If you think, there may be a chance of remembering or “guessing” it, then take your time. 
   Even a few days… maybe you remember it. Sometimes it is good to sit down and focus on it, and sometimes 
   it is good to stop thinking about it for a few days…
   <img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
   But, when you try to login “too often”: Be aware, that the Bitwarden servers e.g. “[…] will require CAPTCHA verification after 9 failed login attempts from an unknown device”, so be careful (and as “accurately” as possible") with your attempts, before getting “slowed down”…

   If it doesn’t come back to you, then eventually it’s time to delete the account you have lost access to… (see the previous section for details about that).


## 7. An Ounce of Prevention...

* Create one (or more) emergency sheet(s) with all login information for your Bitwarden account - 
and store that in (a) secure location(s)… also make sure to keep the emergency sheet(s) up-to-date when you 
change something. – Here is one template for an emergency sheet and what it should contain:
[Emergency Sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md).

* Schedule [full backups](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) of your vault. 
These won’t prevent a “lockout scenario” _per se_, but if you ever 
have a login problem or a “lockout” from your Bitwarden account, then you will still have most or all of your 
important data, and be able to restore that data to a new vault.

* Set a timer / task / reminder to at least every three, six, or even twelve months to make an export of the vault.
More info to exports: see [First Steps](#2-first-steps).

* In addition to being a smart cybersecurity measure, if you set up 2FA it will bypass potential problems with
the Bitwarden "new device verification".

* Bitwarden [Emergency Access](https://bitwarden.com/help/emergency-access/) is also a good idea. Note this requires
a paying Bitwarden subscription.

* An additional login-“backup-method” for the Bitwarden account/vault can be to set up 
“login-with-passkey”-passkeys, ideally “with encryption” which makes it possible to login without entering 
the master password and without your 2FA or “new device verification”-OTP code. 
Those login-passkeys with encryption depend on a PRF capable browser, the “passkey-wallet” 
(i.e. where you store that passkey) and the OS must support the creation of those. And currently 
“login-with-passkey” is still in Beta and only possible for login to the web vault.
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> But, 
as nice as additional login-passkeys to your Bitwarden account/vault are: currently, those 
Bitwarden-login-passkeys don’t replace your master password, as some critical actions still need a 
master password confirmation (like changing the master password and exporting the vault). So don’t rely 
solely on Bitwarden-login-passkeys (for now).

## Credits

Thanks to [@grb](https://community.bitwarden.com/u/grb), [@DenBesten](https://community.bitwarden.com/u/denbesten), 
[@Neuron5569](https://community.bitwarden.com/u/neuron5569) and [@dh024](https://community.bitwarden.com/u/dh024),
whose contributions on the 
[Community Forum](https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188) 
have served as inspirations for this post!

 