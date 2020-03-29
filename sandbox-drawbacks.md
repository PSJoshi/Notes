
### Why Sandboxing is not enough
* It's hard to have a generic sandbox configuration that can work with all kinds of malware. e.g. it's possible that a malware can sleep for 6 hours after infection. In sandbox, you are running most samples for
uoto 5 minutes only and as a result, all the samples may not get caught. So, using sandbox is not a silver bullet. It is to be remembered that each tool has a purpose and you have see the solution
as a means of achieving your aim.

* Some malwares make heavy use of techniques that allow them to track the environment they are running.So, these malwares have built-in anti-VM techniques embedded in malware itself and as a result, malware will not run when it encounters a sandbox.
This again emphasizes the fact that usage of sandbox for malware analysis can not gurantee 100% results.

* It is to be remembered that Hackers often submit samples to public sandboxes to test their detection rate. A very low detection rate is a good sign for the hacker and gives him confidence that a variant of actual sample can be used for attack.

So, it is recommended to supplement sandbox investigation along with other options. This includes going through static analysis using IDA or usage of another round of 
dynamic analysis using a debugger.

In summary, you have to use the available information and resources intelligently to do malware analysis efficiently using a combination of open source and/or commercial tools.
