
# The Stuxnet worm

<p align = "justify">
Stuxnet is a computer worm used to monitor and control large-scale industrial facilities. It was first discovered in June 2010 by the Belarusian company VirusBlokAda at an Iranian nuclear plant. It was the first type of malware that was able to interact with the physical world and not just damage the infected equipment.<sup><a href = https://uk.norton.com/stuxnet>[1]</a></sup>
</p>

### How it works

<p align = "justify">
This worm spreads mostly by pen drives, allowing it to easily infect devices and networks that are not connected to the Internet. The malware exploited some vulnerabilities (also called zero-days) of a method how the Windows operating system used to deal with shortcut files (.lnk files). Typically, this type of file is harmless unless a user runs it. However, the Belarusian company found that the files containing the malicious worm were able to run automatically if they were saved on a pen drive that was later opened by Windows Explorer.<sup><a href = https://www.forbes.com/2010/10/06/iran-nuclear-computer-technology-security-stuxnet-worm.html>[2]</a></sup><b> Sergey Ulasen</b>, chief of the team who discovered the existence of this malware <a href=http://anti-virus.by/en/tempo.shtml> stated</a>:
</p>

> “[...] You just have to open infected USB storage device using (Windows) Explorer or any other file manager which can display icons (for i.e. Total Commander) to infect your Operating System and allow execution of the malware. [...]”

<p align = "justify">
Stuxnet also installs two drivers (mrxnet.sys and mrxcls.sys). These files, also called rootkits, were used to make the malware invisible to the user. Ulasen's team also found that these files had <a href=http://www.realtek.com/> Realtek</a>'s digital signature.
</p>

<p align = "justify">
However, the worm does not actually affect the infected computers. What this does is look for a particular model of a Programmable Logic Controller (PLC), manufactured by <a href=https://www.siemens.com/global/en/home.html> Siemens</a>.
</p>

These PLCs are small industrial control systems that perform all kind of automated processes.<sup><a href=https://krebsonsecurity.com/2010/07/experts-warn-of-new-windows-shortcut-flaw/#more-4045>[3]</a></sup>

### Affected systems and consequences

<p align = "justify">
The worm was initially used to damage and stop the production of Iranian nuclear plants responsible for uranium enrichment. Stuxnet, when accessing the PLC's, was able to control the centrifuges of the plant and, by increasing its speed of rotation, destroy them, making it impossible to use them again.
 </p>
  
<p align="center">
 <img src="http://www.extremetech.com/wp-content/uploads/2015/03/Stuxnet.jpg"  alt = "scheme" height = "415" width = "650">
  <br>
  Img. 1 - How the worm worked
  <sup><a href = http://www.extremetech.com/wp-content/uploads/2015/03/Stuxnet.jpg>[4]</a></sup>
</p>  

<p align="center">
It is estimated that about 1000 centrifuges were affected by Stuxnet. However, the Iranian government has not released any information about the damage caused or the cost of it, and it is impossible to estimate values with certainty.
</p>

<p align="center">
 <img src="https://media.wired.com/photos/593238c69be5e55af6c2398e/master/w_532,c_limit/Ahmadinejad-at-Natanz.jpg"  alt = "visit" height = "415" width = "650">
  <br>
  Img. 2 - Iranian President, Mahmoud Ahmadinejad, during a visit to the centrifuges at Natanz (2008)
  <sup><a href = https://media.wired.com/photos/593238c69be5e55af6c2398e/master/w_532,c_limit/Ahmadinejad-at-Natanz.jpg>[5]</a></sup>
</p>

<p align="justify">
The worm was still able to affect other countries. However, since Stuxnet needs very specific conditions to function, in many devices it has had no effect and has become inert. Still, over the course of several months, thousands of other infected computers were being discovered, as the chart below illustrates.
</p>

<p align="center">
 <img src="http://www.symantec.com/content/en/us/global/images/threat_writeups/2010-071400-3123-99.1.jpg"  alt = "infected" height = "415" width = "650">
  <br>
  Img. 3 - Percentage of computers affected by Stuxnet globally
  <sup><a href = http://www.symantec.com/content/en/us/global/images/threat_writeups/2010-071400-3123-99.1.jpg>[6]</a></sup>
</p>

### Who created Stuxnet?

At the time of the attack there was no clue of who had created the malware or how it managed to infect Iran's biggest nuclear power plant. However, there was some suspicion that the United States of America cooperated with Israel in the creation of this "weapon". The suspicions were confirmed when, in 2013, Edward Snowden leaked this information. 

### Conclusão

<p align = "justify">
Although all of these flaws, both Microsoft and Siemens, have already been fixed in subsequent updates, Stuxnet can not be ignored. There are several versions of this worm online, so anyone (with sufficient funds and knowledge) can change this virus and use it on a much larger scale, and the consequences of this could be devastating. The video below briefly summarizes the attack on the nuclear power plant and what it may have triggered.
</p>

<p align = "center">
<a href="http://www.youtube.com/watch?feature=player_embedded&v=7g0pi4J8auQ" target="_blank">
<img src="http://img.youtube.com/vi/7g0pi4J8auQ/0.jpg" alt="stuxnetvideo"/></a>
 <br>
  STUXNET: The Virus that Almost Started WW3
</p>

