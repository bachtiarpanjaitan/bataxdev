---
title: "Bypass Trial Navicat Premium 16 and 15 on Mac"
excerpt: "Sometimes macbook users feel disappointed because almost all the applications in the AppStore are paid or subscribed so they can use the desired application."
share: true
comments: true
header:
  image: /assets/images/navicate.png
  teaser: /assets/images/navicate.png
  overlay_image: /assets/images/unsplash-image-2.jpg
  og_image: /assets/images/navicate.png
categories:
  - Tips & Tricks
tags:
  - Macbook
  - M1
---

Sometimes macbook users feel disappointed because almost all the applications in the AppStore are paid or subscribed so they can use the desired application. Like my experience where I had to subscribe to the Navicat application by paying more than 1 million per month so I could use the tool I really needed. After several methods that I did, I finally found a way to bypass the Navicat trial where previously I had used the trial version but had reached the trial time that had been determined for 2 weeks. Here are the steps you have to take to bypass the Navicat trial version.

- Download navicat veri 16.x.x or 15.x.x from an unofficial source ( _do not download navicat from appstore_ )
- Install the application as usual
- Copy and paste the following script then save it with the file name `navicat.sh`.


```
#!/bin/bash
set -e
file=$(defaults read /Applications/Navicat\ Premium.app/Contents/Info.plist)
regex="CFBundleShortVersionString = \"([^\.]+)"
[[ $file =~ $regex ]]
version=${BASH_REMATCH[1]}
echo "Detected Navicat Premium version $version"
case $version in
    "16")
        file=~/Library/Preferences/com.navicat.NavicatPremium.plist
        ;;
    "15")
        file=~/Library/Preferences/com.prect.NavicatPremium15.plist
        ;;
    *)
        echo "Version '$version' not handled"
        exit 1
       ;;
esac
echo -n "Reseting trial time..."
regex="([0-9A-Z]{32}) = "
[[ $(defaults read $file) =~ $regex ]]
hash=${BASH_REMATCH[1]}
if [ ! -z $hash ]; then
    defaults delete $file $hash
fi
regex="\.([0-9A-Z]{32})"
[[ $(ls -a ~/Library/Application\ Support/PremiumSoft\ CyberTech/Navicat\ CC/Navicat\ Premium/ | grep '^\.') =~ $regex ]]
hash2=${BASH_REMATCH[1]}
if [ ! -z $hash2 ]; then
    rm ~/Library/Application\ Support/PremiumSoft\ CyberTech/Navicat\ CC/Navicat\ Premium/.$hash2
fi
echo " Done"
```


- Then open a terminal in the saved `navicat.sh` folder and run the command : <mark>`sh navicat.sh` </mark>
- Then open the navicat application and click **trial**.
