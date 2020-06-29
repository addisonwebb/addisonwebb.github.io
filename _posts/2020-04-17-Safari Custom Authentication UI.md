---
layout: post
title: Safari Custom Authentication UI
published: true
date: 2020-06-29 13:00
tags: Apple, radar, Safari
excerpt_separator: <!--more-->
---

A new feature was added in Catalina that lets the user use their local user account password (or Touch ID) to log into Apple websites when that local user account is logged in to iCloud. There are a few problems with this feature.

<!--more-->

First, this feature creates a worse experience for users who use third-party password managers. Safari takes several seconds to load the custom authentication UI (why? 🤷🏼‍♂️) and then the user has to click "Cancel" to display the normal username and password fields on the website. This makes the process of logging in significantly longer than it would be if Safari showed normal username/email and password fields from the start.

Second, this assumes that a user only ever wants to log into Apple services with one Apple ID. Admittedly this is a problem that most people don't have, but as someone who needs to use several different Apple IDs this is super frustrating.

The other issue I have with this feature is more conceptual. This feature completely mucks up the concept of what a local user account password is used for. Apple devices are constantly asking for passwords and normal people have a tough time determining when to use thier Apple ID password and when to use their local user account password.

Even though it can be confusing to many users, the boundaries generally make sense. Unlocking your device or changing device settings require your local user account password. Interacting with Apple's services like the App Store and iTunes use your Apple ID and thus require your Apple ID password. (I know there are some edge cases and that's generally where people get confused.) 

But with this change, Apple is introducing a situation where you need to enter your local device password to log into a website with your Apple ID. Can you see how this is super confusing? As far as I am aware, there is no other situation where you would be prompted for your local user account password to log into a website.

Below is the Radar that I filed suggesting that Apple at least add a preference in Safari to disable this behavior. **Please dupe this Radar if you feel that this Safari "feature" should be removed or a setting added to allow users to disable it!**

## Radar

### Please provide a descriptive title for your feedback:
Add Setting to Disable Custom Authentication UI on Apple Websites

### Which area are you seeing an issue with?
Safari

### What type of issue are you reporting?
Suggestion


### What does the Safari issue you are seeing involve?
Something else not on this list

### Please provide the URL to one or more websites where you are seeing this problem:
https://appleid.apple.com/#!&page=signin, idmsa.apple.com

### What extensions or content blockers do you have enabled? Example: Ghostery, Ublock origin
{ Insert your extensions here. Ultimately, it doesn't matter what extensions you have. }

### Are you able to capture a screen recording of the issue occurring? If so, please attach it to this report.
Yes

### What time was it when this last occurred? (Example: 12:00 pm EST 02/14/2018)
{ Enter today's date. }

### Please describe the issue and what steps we can take to reproduce it:

A new feature was added in Catalina that lets the user use their local user account password (or Touch ID) to log into Apple websites when that local user account is logged in with iCloud. 

This is undesired behavior for users who use third-party password managers. Safari takes several seconds to load the custom authentication UI and then the user has to click "Cancel" to display the normal username and password fields on the website. This makes the process of logging in much longer than it would be if Safari didn't show custom authentication UI.

It is highly annoying that Safari treats Apple websites differently than any other website.

Steps to Reproduce
1. Navigate to an Apple website where you can log in with your Apple ID. (appleid.apple.com, developer.apple.com, etc.)
2. Wait for Safari to present custom login UI.
3. Click "Cancel".
4. Wait for webpage to load username/password text fields.
5. Use third-party password manager to fill form.

Suggestion
Add a setting to Safari to disable this behavior. The desired behavior is that Safari does not treat Apple websites differently than other websites. When navigating to a log in page, Safari should show the standard username and password fields.