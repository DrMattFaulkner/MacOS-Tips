# MacOS Tips

Some useful tips I've discovered whilst using MacOS
## DNS Resolution

### Problem
Can dig a host, but can NOT ping / ssh etc. 

### Solution

sudo launchctl unload /System/Library/LaunchDaemons/com.apple.mDNSResponder.plist
sudo defaults write /Library/Preferences/com.apple.mDNSResponder.plist AlwaysAppendSearchDomains -bool YES
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.mDNSResponder.plist

### Long story:

http://apple.stackexchange.com/questions/24018/dns-lookups-fail-with-e-g-ping-but-work-with-host
