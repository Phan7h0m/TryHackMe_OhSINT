---
title: Writeup for TryHackMe room - OhSINT
author: Phan7h0m
date: 2021-03-29 02:00 AM PST
categories: [CTF, TryHackMe]
tags: [TryHackMe, Writeup, CTF, OhSINT]
---

## [OHSINT](https://tryhackme.com/room/ohsint)

Download the image and read the embedded information in it.
user@user:~$ exiftool WindowsXP.jpg
ExifTool Version Number         : 11.16
File Name                       : WindowsXP.jpg
Directory                       : /data
File Size                       : 229 kB
File Modification Date/Time     : 2020:12:22 02:27:01+05:30
File Access Date/Time           : 2020:12:22 02:27:22+05:30
File Inode Change Date/Time     : 2020:12:26 03:45:44+05:30
File Permissions                : rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
XMP Toolkit                     : Image::ExifTool 11.27
GPS Latitude                    : 54 deg 17' 41.27" N
GPS Longitude                   : 2 deg 15' 1.33" W
Copyright                       : OWoodflint
Image Width                     : 1920
Image Height                    : 1080
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
GPS Latitude Ref                : North
GPS Longitude Ref               : West
Image Size                      : 1920x1080
Megapixels                      : 2.1
GPS Position                    : 54 deg 17' 41.27" N, 2 deg 15' 1.33" W

From the information given via the exiftool, their is a user that we can lookup and find information about. Either with
google or a terminal tool called "sherlock". After a google search we find these three sites:
  -[Twitter] https://twitter.com/OWoodflint
  -[Github] https://github.com/OWoodfl1nt/people_finder
  -[Wordpress] https://oliverwoodflint.wordpress.com/category/uncategorised/
 
![Sherlock!](/home/kali/THM/OhSINT/Sherlock_Screenshot.png "Sherlock search for OWoodFlint")
 
![Google search!](/home/kali/THM/OhSINT/Google.png "Google search for OWoodFlint")

For the first flag, the Twitter account gives us the answer.

![Twitter!](/home/kali/THM/OhSINT/Twitter.png "Twitter search for OWoodFlint")

For a more in-depth approach on a location search, you can use the BSSID that was given on the Twitter account and use
a website such as 'WiGLE' , which was given to us as a hint on a Twitter reply written in Base64, to find the SSID resulting in a loaction result.

![BSSID Tweet](/home/kali/THM/OhSINT/BSSID_Tweet.png "BSSID Tweet")

![Base64 text!](/home/kali/THM/OhSINT/Base64_Text.png "Base64 Decoded")

![WiGLE result for BSSID search!](/home/kali/THM/OhSINT/SSID_Location.png "WiGLE search for BSSID")

Github gives us a location and email address that will be used for the second, fourth and fifth flags.

![Github!](/home/kali/THM/OhSINT/Github.png "Github search for OWoodFl1nt") 

Going through the chain of our Google search, wordpress offers us a location on their trip. Which gives the sixth flag.

![Wordpress!](/home/kali/THM/OhSINT/Wordpress.png "Wordpress search for OWoodFlint")

Flag seven is a difficult one to find even going through developer tools on each site. So out of luck and rapid clicks
of the mouse, it was found.

![Wordpress password flag!](/home/kali/THM/OhSINT/Password.png)
