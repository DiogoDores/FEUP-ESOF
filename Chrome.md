# Chrome Crash Link

### Introduction
In September 2015, Andris Atteka, a security investigator, reported a vulnerability on the popular browser Google Chrome, capable of instantly crashing it. For that, simply adding a null character to the URL string would be enough.  
This is the story of http://a/%%30%30.

### The causes
To be fair, Tom Scott, web developer and previous Sky One host, does a wonderful job detailing on [his YouTube channel](https://www.youtube.com/watch?v=0fw5Cyh21TE) exactly what went wrong. Here's a quick explanation, either way:  

Firstly, it is necessary to have the notion that, in essence, a computer is simply an endless chain of zeros and ones. At a certain point, the computer notices that a particular memory zone corresponds, for example, to the start of the URL that the user wishes to access. The reading and stopping condition resides in two main techniques. One is to store the number of characters to read and other in continuous reading until it lands in a `NULL` character, an empty byte.
The percentages in our malicious URL mean a coded character. However, `%30` means 0 - the number, not the null character. Let's decode the resulting URL now. In `http://a/%00`,`%00` is converted to `NULL`. The decoding function marks the link as safe to use and the inevitable happens.  

Atteka, [on his blog](https://andrisatteka.blogspot.pt/2015/09/a-simple-string-to-crash-google-chrome.html), admits he wasn't rewarded given that his finding had been considered a DoS vulnerability (denial-of-service):

> Unfortunately no reward was awarded as this was deemed to be only a denial-of-service vulnerability. Anyway, making secure software is much harder than finding issues in it. Thanks Google.

The vulnerability is marked as resolved 5 days after its discovery, its path from detection to resolution available to follow on the [official Project Chromium bug forum](https://bugs.chromium.org/p/chromium/issues/detail?id=533361#c14).

### The consequences
Note that this bug not only affected Google Chrome, but all Chromium-based applications, including other browsers like Opera and apps like Atom and Slack.  

Paulo Castro (pkasting), one of the developers, sighes:
> There are going to be crashes all over as a result of this. This is a mess.  

This vulnerability would have been quickly reported by news websites such as WIRED, The Guardian and Daily Mail, only expanding the scale of the incident.  

As reported by TheHackerNews:
> The issue appears to be small but is actually serious, as it is possible for any of your friends to tweet out the link in question, and crash all Chrome users whose Twitter timeline will load that link.  

### Similar incidents

This incident is similar to that of June 2015, which plagued Skype, the popular platform specialized in voice and video connections. In this case, it would suffice for a user to receive a message with a `http://:` link to trigger an endless loop of uncontrollable crashes.

Additionally, the parallelism with the unicode sequence of 75 bytes that despaired Apple users on May 2015 is evident. Affecting from iPhones to the Apple Watch, this lethal string would cause the CoreText library to access invalid memory, forcing the operating system to terminate the current process. Thus, receiving a message with this content would result in the instant reboot of the device.

All these three vulnerabilities have in common an oversight of character handling by multinational technology companies. But the consequences weren't so much monetary, as social. These weaknesses handicap the user experience and generate frustration when exploited by malicious individuals.

### 3030
Meanwhile, Sean Zhu developed [3030](https://github.com/szhu/3030), taking advantage of the infamous bug. The game aims to go through a maze of emojis, in which walls are hyperlinks to the problematic URL. This proves that even from an inconvenient vulnerability some creativity always arises.

<img src="https://i.imgur.com/0jp53AO.png" alt="alt text" width="500">

### References
https://www.youtube.com/watch?v=0fw5Cyh21TE - Tom Scott's explanation  
https://www.theguardian.com/technology/2015/sep/22/crash-google-chrome-browser-link - The Guardian article  
https://www.wired.co.uk/article/google-chrome-crash - WIRED article  
https://bugs.chromium.org/p/chromium/issues/detail?id=533361#c14 - Official Project Chromium developer discussion  
https://www.theregister.co.uk/2015/09/20/chrome_url_crash/ - The Register article on Chrome issue
https://www.theregister.co.uk/2015/06/03/mistyped_url_will_kill_skype/ - The Register article on Skype issue
https://www.theregister.co.uk/2015/05/27/text_message_unicode_ios_osx_vulnerability/ - The Register article on iOS issue  
https://github.com/szhu/3030 - 3030 game  
https://andrisatteka.blogspot.pt/2015/09/a-simple-string-to-crash-google-chrome.html - Andris Atteka's blog


