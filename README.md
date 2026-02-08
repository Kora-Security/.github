# Kora Security

A security suite of mostly stuff I think is missing or could be done better on linux. Or just making my own versions of things. (This readme is a WIP)
__ __
> Eventually a windows version too.

<br> 
<br>

## What I'm working on currently.

Right now I'm working on **KoraAV**. It's an antivirus for Linux that also uses behavioral detection on top of the standard signature database stuff, etc. The idea is to catch most of the more modern threats like info stealers and ransomware by watching what programs do and intercepting certain behaviors, rather than trying to **only** match them against a list of known malware. (which can take some time depending on the sise of the list).
> TLDR: It will basically be a modern AV but built for linux instead of ONLY windows. And it won't be locked behind an enterpise subscription. (like some currently are.)

It's in a VERY early developmental stage. There's still a ton to build out and create. This isn't something that will be done in a few weeks.
__ __

<br>
<br>

## Why am I doing this?

I got tired of having to use clamAV and I don't want to have to pay for an enterpise subscription JUST to get a linux variant of their AV software to use. Or be locked into subscriptions just to feel a bit more safe. I wanted to try my hand at making my own tooling and software, learn more as I go, and have a good time. Eventually the things I make could be used by more people, but for now it's a personal hobby/project thing that I would use myself on my own systems.
__ __

<br>
<br>

## Current project: KoraAV

**Status:** WIP

**What I want it to do:**
- Monitor file/dir access to sensitive folders and detect if data is being read from there from software/executeables/scripts that shouldn't be soing so.
  > (browser profiles, .ssh, Documents, crypto wallets, etc. Basically anti info stealer enumeration.)
- Track file modifications before the data gets saved and stop malicious acts before they finish.
  > (Ransomware encrypting a file and before the file data gets saved after writting to the file, check to see if it has been encrypted. If yes then don't save the file modifications and quarantine the threat.)
- Analyze commands before they execute/run. Like looking for obfuscation, high entropy, known malicious patterns, etc.
  > (I want to know what's being pasted into terminals or consoles first before allowing it to run/execute. Basically anti clickfix.)
- Track network connections and correlates them with file access.
  > (catching exfiltration attempts and stopping it before data gets sent. Or trying to minimize how much data can be sent before being stopped.)
- Can automatically kill processes, block network, or lock the filesystem into read only when threats are detected. 
- And more. (TBD)
__ __
> I am looking into using eBPF to hook into kernel syscalls for now. Doing this can give more visibility into everything happening on your system without a hit to performance.

<br>
<br>

## Other tooling I'd like to make at some point.
> These are things that may or may not happen, but are ideas and are basically just hopes and dreams.

Once KoraAV is stable and useable, My next ideas are:

- **Windows version** - Same behavioral approach but perhaps using minifilter drivers and ETW. And making it work on windows systems. (no plans for Mac/Apple devices)

- **SIEM Tooling** - I feel like this could be a neat project to make and shouldn't be too hard to do since it's basically just collect **ALL** of the data and events happening at all times and check for anomalies.

- **Memory forensics tooling** - Analyzing running processes and detecting in-memory malware and suspiscious things could be prety neat to make.

- **HIPS/mini-EDR system** - I mean....this would just be cool to do and you can't go wrong with more detection systems.
__ __

<br>
<br>

## FAQ
Feel free to ask more questions, I'll add to the list here if need be. But I appreciate all of your questions!
__ __

**Q: Can I contribute?**  
Sure. If you want to help I won't say no to most. Feel free to open an issue or a PR.

**Q: Will this work on my distro?**  
If you're using kernels 5.15+ with BTF support, probably. I am developing for Debian13 & I haven't picked an arch based distro yet but it should work on most modern linux distros. Although I can't promise anything without further distro testing.

**Q: Why Linux first instead of Windows?**  
Everything now days is made on windows first as linux gets neglected so I fugured, giving linux some more love couldn't hurt. Also with more users leaving windows and jumping ship, it'd be nice to have some software like an AV that isn't going to be locked behind an enterpise paypall or subscription. Also personally, It's easier for me to develop for. Plus I use Linux daily and want to make something I'd actually use.
> A windows port will come later. (no plans for MacOS)

**Q: Will your software products replace my traditional antivirus or security solutions?**  
Eventually, maybe..if you want to. Right now? **No**. This is **experimental** and for personal use. I'd reccomend you keep using whatever you're using until anything I make is actually stable, audited, and peer reviewd.

**Q: What about false positives?**  
That's something that can't quickly or easily be handled without your help giving feedback on what is or should be good, etc. Alternatively a program whitelist that you can add to/update like most modern software has (as sudo/root) can help with false positives.
> I do want to minimize false positives.

**Q: Why make it open source?**  
I think security tools should be transparent and not locked behind paywalls. And you only make people's systems more secure if everyone can use it and not just those who have money. Additionally, having code be closed source, means it can take longer to find and patch bugs, vulnerabilities, and bypasses, etc.  Plus, more eyes on the code means things can get done faster, more trust, and it can only get better from there as the code gets audited, verified, etc.

**Q: Do you work for a company?**  
Currently, No. So far, it's just me in my spare time tinkering with things. (I am open for employment if you're intersted <3)

**Q: Can I buy this?**  
I am not interested in commercializing my software. I just want to build good tools/things and make them available to everyone. I don't like subscriptions, paywalls, etc. You don't make people more secure doing that. You tend to care more about profits and people with money than making something good.
> I am a fan of uBlockOrigin's model of staying away of donations, greed, etc.
__ __

<br>
<br>


## Updates

They'll happen when they're ready (you can help). The stuff I work on and make here isn't stuff I'll be working on 24/7, etc. Just when I can here and there.
__ __
