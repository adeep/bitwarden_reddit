This guide is based on https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188/4. 
Kudos to [Nail1684](https://community.bitwarden.com/u/Nail1684/summary); any mistakes are doubtless mine, not his.

---------------------

“Unofficial Community Guide”
– from a user to other users, as I’m not a Bitwarden employee!

This post is a collection of considerations and tips around the issue of “login problems”. As a collection of various possibilities, it is a general list, though some cases are “individual” – and “everything” is too much in many cases.

So, go through that list, take your time, and you certainly don’t have to “study” everything in detail. But be careful with everything you do now, as with login problems, you may be already in the “danger zone”.

:warning: Info: This post is mainly for individual, families or Teams accounts. Enterprise accounts have some different set ups (SSO, account recovery…) that are not part of this post (and in general, contact your Enterprise organization administrator if you encounter problems).

And some repetitions are intentional, as some important topics - like mentioning exports/backups - belong to more than one “point”…

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

## 1. Before You Start

*Depending on what exactly has happened, you may be in danger of losing access to your vault*
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
– so proceed very carefully with everything you try and do – even the things that are suggested here. (the critical things in this post do have a warning message…)

*If you are still logged in (whether “locked” or “unlocked”) in one or more Bitwarden apps: 
_stay logged in there_ (!), _disconnect_ the device from the internet, and try to make an _export_ of your data
ASAP - with the export function, or manually if necessary. – If something goes wrong in the following, 
with an export, you are able to restore your data, hopefully.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> When 
you use the export function (only possible if you still have access to that function in at least one of the Bitwarden apps):

* Be aware that exports do not contain Sends and items in the trash.

* CSV exports furthermore do not contain file attachments, cards, identities and passkeys.

* Therefore, JSON exports are recommended, and preferably the encrypted password-protected ones, 
but unencrypted JSON exports are also fine, since you now have other problems.

* If it isn’t contained in an export file, you will have to export manually.

* When exporting your vault, you will need your master password – so if it turns out your login problems are due 
to a “master password problem”, you unfortunately won’t be able to use the export function. In this case you 
need to export everything manually. (And again, that would be only possible if you still have access to at 
least one Bitwarden app, otherwise you are at an impasse here…)

* If you have an organization/collections, you have to export those separately via the 
[admin console](https://bitwarden.com/help/export-your-data/#export-an-organization-vault) in the web vault.


## 2. First Steps

* Verify whether you are "locked" versus "logged out" in your app 
([what’s the difference between locking/unlocking and logging in?](https://bitwarden.com/help/unlock-with-pin/#understanding-unlock-vs-log-in)).

* If you’re _locked_, you must unlock locally with your chosen method(s) 
  ([Unlock with PIN](https://bitwarden.com/help/unlock-with-pin/), 
  [Unlock with Biometrics](https://bitwarden.com/help/biometrics/) or simply unlock with you master password).

* If you’re _logged out_, you must log in, which includes your registered email, your password, and your 
  2FA. There may also be a [new-device-verification-code](https://bitwarden.com/help/new-device-verification/). 
  You may also have access via a [passkey](https://bitwarden.com/help/login-with-passkeys/).

<img src="https://community.bitwarden.com/images/emoji/twitter/bulb.png?v=14" title=":bulb:" class="emoji" alt=":bulb:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> We 
focus on login problems in this post! (Unlocking problems are a separate issue.)

* Make sure whether you are being asked for your _master password_ (possible for either unlocking or logging in) 
or for your _PIN_ (only applicable when unlocking). These are not interchangeable; the PIN won’t work when 
you’re asked for your master password (and vice versa), and you cannot ever login with your PIN alone.


## 3. Simple Tests

If you cannot login in via _one_ of the Bitwarden apps, …

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
way you can check whether it is a _general_ login problem (when you can’t login anywhere)
versus a problem with a single app or device.

* _If it’s a general problem_ you should focus on things that have a kind of “general approach” – _and if 
it’s a problem with one app and/or device_, you probably can focus on more “narrow” measures regarding that 
app and/or device.

<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> When 
trying to login “too often”: the Bitwarden servers 
[will require CAPTCHA verification](https://bitwarden.com/help/security-faqs/#q-how-can-i-protect-my-bitwarden-account-from-brute-force-attacks) 
after 9 failed login attempts from an unknown device”, so be careful with your attempts.


## 4. Advanced Tests

* Please look at the previous section [Simple Tests](#3-simple-tests) first! 

* Check whether _the Bitwarden (US/EU) servers are temporarily down_. This could happen during
a planned server update; check the [Bitwarden Status Page](https://status.bitwarden.com/)

* Check to see if your server is down by trying the vault page directly:
[vault.bitwarden.com](https://vault.bitwarden.com) or [vault.bitwarden.eu](https://status.bitwarden.com/).
If the server is down in general, wait until it is fixed, and then try to login again.

* _If you’re self-hosting_, check, whether your own server _works as expected_.  It is possible your
login problems due to local errors misconfigurations of your self-hosted Bitwarden server.
These issues are out of the scope of this guide). But please do verify you have the _latest server version_ 
installed. (“new” client versions and “old” server versions do get incompatible eventually!)

* Did you choose the _right server region_ – US/.com or EU/.eu? These are distinct servers, and 
they are not interchangeable. You must use the one your Bitwarden account was created and located on.

* _If you are not sure which server region your account was created on_, try logging in both places.

* _Verify your email address and master password_. It's time to look at your 
[emergency sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md)! 
If necessary, consider getting your master password hint, if you have one.
(Pro tip: many people set 
the whereabouts of their emergency sheet(s) as their master password hint…)

* Perhaps _you changed your email address and/or master password_? 
And didn’t update that on your emergency sheet?

* _Look for any typos in your email address and/or master password_, especially silly mistakes or more obvious 
ones like 0 (zero) versus O (capital letter “oh”), l (small “L”) versus I (capital letter “i”) 
or | (special character “vertical bar”) etc.
* _Look for added or missing spaces_: leading spaces, trailing spaces or spaces within your master 
password – either accidentally (or intentionally) added while creating the master password (but now missing when 
you try to type the master password for logging in), or the other way round: accidentally added when 
you now try to type the master password for logging in.

> For the email address, it doesn’t make a difference whether you use lower case letters or upper-case letters, 
> so whether you try to login with example@example.com or EXAMPLE@EXAMPLE.COM – both should work exactly the 
> same. This is not true for the master password!

* Do you have _problematic special characters_ in your master password? 
Non-ASCII / Unicode characters may work on one system, but not on other systems.

We recommend only to use the 95-character ASCII set (or “less”) for master passwords to stay on the safe side, 
or rather to guarantee “cross-system-wide” compatibility:

* A-Z
* a-z
* 0-9
* The following special characters: `!"#$%&'()*+,-./:;<=>?@\`[~]^_{}|` and the "space" character

If you can login to your web vault, but not to another one of the Bitwarden apps - you
may have a problematic special character in your master password. Consider changing your master password
to one that only has 95-character ASCII characters just described.
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;">
Start by exporting your vault 
before you change your master password! – see [First Steps](#1]2-first-steps).

* While you're changing your master password, consider using a 4-word passphrase, generated by Bitwarden itself, for
your master password.  For instance, `polka-fame-curled-either-passover`.

* Watch out for auto-corrections by your keyboard(s)/app/device – you may not even notice it, especially 
when the input is obscured! Even if you stick to the 95-character ASCII set, as recommended above, 
some characters may get auto-corrected by your keyboard/app/device):

  * For example, replacing straight-quotes with curly-quotes (i.e., “smart-quotes”), or inserting a . 
(period/full stop) and/or invisible spaces after pressing the “space-bar”,  or automatically changing a 
typed lower-case letter into an upper-case letter (or vice versa)…

  * In general, all kinds of apostrophes and quotation marks (', ", `, ´, ‘, ’, ‛, “, ”, ‟) may be auto-corrected into a different form preferred by the device you are typing on.

  * Ideas: _turn off auto-correct_ if possible. Try to _change your (virtual or physical) keyboard_. 
  Make your _keyboard input visible_ if possible. Make sure you input the exact character. Use the _on-screen visible
  keyboard_. If those things don’t help, change your master password in the web vault to one that contains only 
  the 95-character ASCII set, or better yet a 4 word random passphrase without any special characters at all.
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> Again, 
  make an export/backup before changing your master password; see [First Steps](#2-first-steps).
  * On iOS: _deactivate smart punctuation_, since that can “auto-correct” characters you type in

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


7. An Ounce of Prevention...

* Create one (or more) emergency sheet(s) with all login information for your Bitwarden account - 
and store that in (a) secure location(s)… also make sure to keep the emergency sheet(s) up-to-date when you 
change something. – Here is one template for an emergency sheet and what it should contain:
[Emergency Sheet](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md).

* Schedule regular exports of your vault. That won’t prevent a “lockout scenario” _per se_ – but if you ever 
have a login problem / a “lockout” from your Bitwarden account, then you still have most or all of your 
important data, to be able to restore them.

* Set a timer / task / reminder to at least every three, six, or even twelve months to make an export of the vault.
More info to exports: see [First Steps](#2-first-steps).

* In addition to being a smart cybersecurity measure, if you set up 2FA it will bypass potential problems with
the Bitwarden "new device verification".

* Bitwarden [Emergency Access](https://bitwarden.com/help/emergency-access/) is also a good idea. Note this requires
a paying Bitwarden subscription.

* An additional login-“backup-method” for the Bitwarden account/vault can be to set up 
“login-with-passkey”-passkeys, ideally “with encryption” which makes it possible to login without entering 
the master password and without your 2FA or “new device verification”-OTP code. 
Those login-passkeys with encryption depend on PRF, and the browser, the “passkey-wallet” 
(i.e. where you store that passkey) and the OS must support the creation of those. And currently 
“login-with-passkey” is still in Beta and only possible for login to the web vault.
<img src="https://community.bitwarden.com/images/emoji/twitter/warning.png?v=14" title=":warning:" class="emoji" alt=":warning:" loading="lazy" width="20" height="20" style="aspect-ratio: 20 / 20;"> But, 
as nice as additional login-passkeys to your Bitwarden account/vault are: currently, those 
* Bitwarden-login-passkeys don’t replace your master password, as some critical actions still need a 
* master password confirmation (like changing the master password and exporting the vault). So don’t rely 
* solely on Bitwarden-login-passkeys (for now).

## Credits

Thanks to @grb, @DenBesten, @Neuron5569 and @dh024 whose contributions on the forum have served as inspirations for this post!

 