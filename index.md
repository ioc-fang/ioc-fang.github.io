# IOC Fang: Indicator of Compromise (De)Fanging Project

## TL;DR

This project standardizes fanging and defanging of indicators of compromise:

**Fanging**:

- `example[.]com => example.com`
- `hXXps://example[.]com => https://example.com`
- `fooATexample[.]com => foo@example.com`

**Defanging**:

- `example.com => example[.]com`
- `https://example.com => hXXps://example[.]com`
- `foo@example.com => foo@example[.]com`

You can use this project online at [http://ioc-fanger.hightower.space/](http://ioc-fanger.hightower.space/).

## Why Does this Project Exist?

We're standardizing the way [indicators of compromise](https://en.wikipedia.org/wiki/Indicator_of_compromise) are fanged (and defanged) to make the internet a safer place by:

1. Making sure indicators are properly and fully defanged so malicious links are not accidentally distributed.
2. Making it easy for automated scripts to fang indicators so that security professionals can collect and investigate data easily.

## What is an Indicator of Compromise?

> Indicators of compromise (IOCs) are "pieces of forensic data, such as data found in system log entries or files, that identify potentially malicious activity on a system or network." Indicators of compromise aid information security and IT professionals in detecting data breaches, malware infections, or other threat activity. By monitoring for indicators of compromise, organizations can detect attacks and act quickly to prevent breaches from occurring or limit damages by stopping attacks in earlier stages.[1]

[1] [https://digitalguardian.com/blog/what-are-indicators-compromise](https://digitalguardian.com/blog/what-are-indicators-compromise)

For more information, visit [https://en.wikipedia.org/wiki/Indicator_of_compromise](https://en.wikipedia.org/wiki/Indicator_of_compromise).

## What is "Fanging" and "Defanging"?

**Fanging**: *Restoring an indicator of compromise to its original form, with no artifacts from defanging.*

e.g. `example[.]com => example.com`

**Defanging**: *Adding text to an indicator of compromise so that it does not become a link when presented in any medium (in an email, on a website, in a pdf, etc).*

e.g. `example.com => example[.]com`

### Fanging and Defanging: A Short Tale

So let's understand what is means to "fang" and "defang" an IOC. Let's pretend you and I are computer security researchers and I want to send you information about a malicious host-name I found. Let's also pretend that this malicious host-name is example.com. If I simply paste the text "example.com" into an email, it will become a live link which, if you're not careful, will take you to the malicious host (no bueno). Thus, an IOC that can become a live link is "fanged" and I want to "defang" it so that there is no chance of it becoming a link and you accidentally clicking on it. To defang a host-name, I would change `example.com` to `example[.]com` in my email so that it will not become a link.

Once you get the email, however, you want to investigate the malicious host-name (example[.]com), but you first need to "fang" the host-name to take it back to its original form so you can search for it (I recommend searching in [VirusTotal](https://virustotal.com) and [ThreatConnect](https://app.threatconnect.com)). To fang the host-name, you will take `example[.]com` and convert it to `example.com`.

That's it! Pretty simple, right?

## Next Steps

If you would like to use the python package, you can find instructions for installing and using it [here](https://github.com/ioc-fang/ioc_fanger). If you have ideas/feedback, don't hesitate to [raise an issue](https://github.com/ioc-fang/ioc_fanger/issues).

You can use the IOC Fang system online here: [http://ioc-fanger.hightower.space/](http://ioc-fanger.hightower.space/).
