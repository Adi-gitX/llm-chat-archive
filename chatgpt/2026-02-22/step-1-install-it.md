# 🔥 Step 1 — Install It

> **Platform:** CHATGPT | **Date:** 22/02/2026, 22:32:38 | **Turns:** 2
> **Source:** [Open Original](https://chatgpt.com/c/699b36a3-5fe8-8321-a14a-00344559d3e3)

---

## USER

Skip to content
Navigation Menu
Platform
Solutions
Resources
Open Source
Enterprise
Pricing

Search or jump to...
Sign in
Sign up
projectdiscovery
/
subfinder
Public
Code
Issues
7
Pull requests
8
Discussions
Actions
Projects
Security
Insights
projectdiscovery/subfinder
Go to file
Name		
dogancanbakir
dogancanbakir
Merge pull request #1723 from recepgunes1/fix/timeout-flag-not-working
2d4f804
 · 
2 weeks ago
.github
Merge pull request #1710 from projectdiscovery/add-urlscan-source
3 weeks ago
cmd/subfinder
refactor: move v2 module code to root directory for cleaner structure
7 months ago
examples
refactor: move v2 module code to root directory for cleaner structure
7 months ago
pkg
Merge pull request #1723 from recepgunes1/fix/timeout-flag-not-working
2 weeks ago
static
include images
7 years ago
.gitignore
Add wildcard certificate detection in JSON output (#1665)
3 months ago
.goreleaser.yml
Add wildcard certificate detection in JSON output (#1665)
3 months ago
DISCLAIMER.md
omnisint from Sonar Labs is dead, is not working anymore (#701)
4 years ago
Dockerfile
refactor: change Dockerfile paths
7 months ago
LICENSE.md
Update LICENSE.md
5 years ago
Makefile
refactor: move v2 module code to root directory for cleaner structure
7 months ago
README.md
update README
5 months ago
THANKS.md
chore: fix some typos in comments (#1221)
2 years ago
go.mod
chore(deps): bump the modules group with 10 updates (#1714)
last month
go.sum
chore(deps): bump the modules group with 10 updates (#1714)
last month
Repository files navigation
README
Code of conduct
Contributing
MIT license
Security
subfinder
Fast passive subdomain enumeration tool.
    

Features • Install • Usage • API Setup • Library • Join Discord

subfinder is a subdomain discovery tool that returns valid subdomains for websites, using passive online sources. It has a simple, modular architecture and is optimized for speed. subfinder is built for doing one thing only - passive subdomain enumeration, and it does that very well.

We have made it to comply with all the used passive source licenses and usage restrictions. The passive model guarantees speed and stealthiness that can be leveraged by both penetration testers and bug bounty hunters alike.

Features
subfinder
Fast and powerful resolution and wildcard elimination modules
Curated passive sources to maximize results
Multiple output formats supported (JSON, file, stdout)
Optimized for speed and lightweight on resources
STDIN/OUT support enables easy integration into workflows
Usage
subfinder -h
This will display help for the tool. Here are all the switches it supports.

Usage:
  ./subfinder [flags]

Flags:
INPUT:
  -d, -domain string[]  domains to find subdomains for
  -dL, -list string     file containing list of domains for subdomain discovery

SOURCE:
  -s, -sources string[]           specific sources to use for discovery (-s crtsh,github). Use -ls to display all available sources.
  -recursive                      use only sources that can handle subdomains recursively (e.g. subdomain.domain.tld vs domain.tld)
  -all                            use all sources for enumeration (slow)
  -es, -exclude-sources string[]  sources to exclude from enumeration (-es alienvault,zoomeyeapi)

FILTER:
  -m, -match string[]   subdomain or list of subdomain to match (file or comma separated)
  -f, -filter string[]   subdomain or list of subdomain to filter (file or comma separated)

RATE-LIMIT:
  -rl, -rate-limit int  maximum number of http requests to send per second
  -rls value            maximum number of http requests to send per second for providers in key=value format (-rls "hackertarget=10/s,shodan=15/s")
  -t int                number of concurrent goroutines for resolving (-active only) (default 10)

UPDATE:
  -up, -update                 update subfinder to latest version
  -duc, -disable-update-check  disable automatic subfinder update check

OUTPUT:
  -o, -output string       file to write output to
  -oJ, -json               write output in JSONL(ines) format
  -oD, -output-dir string  directory to write output (-dL only)
  -cs, -collect-sources    include all sources in the output (-json only)
  -oI, -ip                 include host IP in output (-active only)

CONFIGURATION:
  -config string                flag config file (default "$CONFIG/subfinder/config.yaml")
  -pc, -provider-config string  provider config file (default "$CONFIG/subfinder/provider-config.yaml")
  -r string[]                   comma separated list of resolvers to use
  -rL, -rlist string            file containing list of resolvers to use
  -nW, -active                  display active subdomains only
  -proxy string                 http proxy to use with subfinder
  -ei, -exclude-ip              exclude IPs from the list of domains

DEBUG:
  -silent             show only subdomains in output
  -version            show version of subfinder
  -v                  show verbose output
  -nc, -no-color      disable color in output
  -ls, -list-sources  list all available sources

OPTIMIZATION:
  -timeout int   seconds to wait before timing out (default 30)
  -max-time int  minutes to wait for enumeration results (default 10)
Environment Variables
Subfinder supports environment variables to specify custom paths for configuration files:

SUBFINDER_CONFIG - Path to config.yaml file (overrides default $CONFIG/subfinder/config.yaml)
SUBFINDER_PROVIDER_CONFIG - Path to provider-config.yaml file (overrides default $CONFIG/subfinder/provider-config.yaml)
Installation
subfinder requires go1.24 to install successfully. Run the following command to install the latest version:

go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
Learn about more ways to install subfinder here: https://docs.projectdiscovery.io/tools/subfinder/install.

Post Installation Instructions
subfinder can be used right after the installation, however many sources required API keys to work. Learn more here: https://docs.projectdiscovery.io/tools/subfinder/install#post-install-configuration.

Running Subfinder
Learn about how to run Subfinder here: https://docs.projectdiscovery.io/tools/subfinder/running.

Subfinder Go library
Subfinder can also be used as library and a minimal examples of using subfinder SDK is available here

Resources
Recon with Me !!!
License
subfinder is made with 🖤 by the projectdiscovery team. Community contributions have made the project what it is. See the THANKS.md file for more details.

Read the usage disclaimer at DISCLAIMER.md and contact us for any API removal.

About
Fast passive subdomain enumeration tool.

projectdiscovery.io
Topics
osint hacking bugbounty hacktoberfest subdomains reconnaissance subdomain-enumeration
Resources
 Readme
License
 MIT license
Code of conduct
 Code of conduct
Contributing
 Contributing
Security policy
 Security policy
 Activity
 Custom properties
Stars
 13.1k stars
Watchers
 160 watching
Forks
 1.5k forks
Report repository
Releases 58
v2.12.0
Latest
on Jan 12
+ 57 releases
Packages
No packages published
Used by 165
@ontu404
@exploopio
@h0tak88r
@harekrishnarai
@CodeMonkeyCybersecurity
@theopenlane
@DavidLanz239
@allsafeASM
+ 157
Contributors
107
@dependabot[bot]
@Ice3man543
@ehsandeep
@Mzack9999
@dogancanbakir
@vzamanillo
@codingo
@forgedhallpass
@picatz
@LuitelSamikshya
@tarunKoyalwar
@0x4500
@mikelolasagasti
@akhil-reni
+ 93 contributors
Languages
Go
99.8%
 
Other
0.2%
Footer
© 2026 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Community
Docs
Contact
Manage cookies
Do not share my personal information how do i use thi s

---

## ASSISTANT

ProjectDiscovery – Subfinder
4
You’re looking at **Subfinder**, a fast **passive subdomain enumeration tool**.
It finds subdomains like:

```
Codeapi.example.comdev.example.commail.example.com
```

using OSINT sources (crt.sh, GitHub, etc.) without directly attacking the target.

🔥 Step 1 — Install It
You need **Go 1.24+**.

```
Bashgo install -v github.com/projectdiscovery/subfinder/v2/c
```


---
*Archived by [StoreChat](https://github.com/Adi-gitX/StoreChat) on 2026-02-22*
