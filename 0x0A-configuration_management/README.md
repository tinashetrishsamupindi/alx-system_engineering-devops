0x0A-configuration_management

You have a captain's log due before 2023-09-24 (in 2 days)! Log it now!
We're moving to Discord!
In a few days, we will be leaving Slack in favor of Discord 🎉
Click here for more information
0x0A. Configuration management
DevOps
SysAdmin
Scripting
CI/CD
 By: Sylvain Kalache
 Weight: 1
 Project will start Sep 22, 2023 5:00 AM, must end by Sep 23, 2023 5:00 AM
 Checker will be released at Sep 22, 2023 11:00 AM
 An auto review will be launched at the deadline
Background Context


When I was working for SlideShare, I worked on an auto-remediation tool called Skynet that monitored, scaled and fixed Cloud infrastructure. I was using a parallel job-execution system called MCollective that allowed me to execute commands to one or multiple servers at the same time. I could apply an action to a selected set of servers by applying a filter such as the server’s hostname or any other metadata we had (server type, server environment…). At some point, a bug was present in my code that sent nil to the filter method.

There were 2 pieces of bad news:

When MCollective receives nil as an argument for its filter method, it takes this to mean ‘all servers’
The action I sent was to terminate the selected servers
I started the parallel job-execution and after some time, I realized that it was taking longer than expected. Looking at logs I realized that I was shutting down SlideShare’s entire document conversion environment. Actually, 75% of all our conversion infrastructure servers had been shut down, resulting in users not able to convert their PDFs, powerpoints, and videos… Pretty bad!

Thanks to Puppet, we were able to restore our infrastructure to normal operation in under 1H, pretty impressive. Imagine if we had to do everything manually: launching the servers, configuring and linking them, importing application code, starting every process, and obviously, fixing all the bugs (you should know by now that complicated infrastructure always goes sideways)…

Obviously writing Puppet code for your infrastructure requires an investment of time and energy, but in the long term, it is for sure a must-have.
