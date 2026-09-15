# Robots.txt AI Visibility Audit

Reads a robots.txt file and shows, for every LLM, whether its training, search and user crawlers are allowed or blocked, what that does to your AI visibility and which line is costing you.

Built from [Can Publishers Block AI Training Without Losing AI Visibility? Robots.txt Best Practices for AI Search](https://www.oritmutznik.com/ai-search-optimisation/robots-txt-ai-search-best-practices-free-audit-tool/) by [Orit Mutznik](https://www.oritmutznik.com/). The article explains what each crawler does, why blocking training can cost you citations and what a subscription-based publisher found when it audited its own file. This is the tool the article uses.

**Use it in the browser:** https://www.oritmutznik.com/wp-content/uploads/2026/09/robots-txt-ai-visibility-audit.html

## Use it

1. Try the 4 example buttons first: **Publisher example** (the file the article is built on), **Multiple blocked folders example** (an anonymised B2B research publisher that blocks everything, then opens named folders), **Fully open example** (an anonymised UK gaming site) and **Fallback example** (illustrative, not a real site: what to do if you must protect specific folders, the site open and two folders closed to training crawlers only. The recommendation is still to open everything).
2. Open `yoursite.com/robots.txt`, copy the contents, paste them in and press **Check**. Browsers cannot read another site's robots.txt directly, so there is no URL fetch. Hit **Clear** to paste a new file, or simply paste over it and hit Check again.
3. Read "Worth checking" last. Every line ends with a call: Almost certainly not intended, worth confirming or for information.

Nothing you paste is retained or shared, not even for learning purposes. There is no server and no tracking: The file is read in your browser and goes nowhere else.

## What it checks

- The 5 LLMs that carry 92.9% of AI product web traffic ([Similarweb, August 2026](https://the-decoder.com/chatgpt-claws-back-web-traffic-share-to-55-5-percent-as-geminis-brief-comeback-fades/)): ChatGPT, Gemini, Claude, Copilot and Perplexity
- Every training, search and user crawler each one documents, evaluated per [RFC 9309](https://www.rfc-editor.org/rfc/rfc9309) (exact user-agent match, several groups for one agent merged, then `*`, longest rule wins, Allow wins a tie)
- A headline that names the shape of the file (allowlist, blocklist, middle path, open, shut) and a one-line judgement on it
- A verdict in bullets: Which LLMs can train on and cite your pages, which can only cite them and which are blocked, folder by folder when the file treats folders differently, then what that costs you in plain words
- One card per LLM with a pill per folder group and a green or red letter for each crawler it runs (train, search, user)
- A "Worth checking" list: Conflicting rules for the same crawler and path with line numbers, crawlers listed more than once, named crawlers that skip the wildcard housekeeping, one LLM split by role inside a folder, only some AI companies on the list, legacy agents
- A "Languages and regions" line when the file names at least two language or region folders (or one with a region code): Which languages are open to which LLMs, plus a check when only some languages are opened
- A table of every path the file treats differently from the site default, most restrictive first
- Every other crawler worth knowing, search engines first, then DeepSeek, Grok, Common Crawl and the LLM-first crawlers most people have never heard of

## Export

Copy as markdown, download `.md`, `.csv` or `.json`, or print to PDF.

## Host it yourself

It is one HTML file with no dependencies beyond Google Fonts. Drop `index.html` anywhere, including GitHub Pages.

## What it cannot tell you

- Robots.txt is a set of directives. The big companies say their crawlers follow it, but a crawler can ignore it and newer or less careful ones sometimes do. The tool reads what your file asks for, not who actually turns up.
- It reads only what you paste. It does not fetch your pages, so it cannot tell whether an allowed folder is behind a paywall, redirects somewhere else or has been taken down.
- It does not see other blocks. A firewall, a CDN rule or a meta tag can stop a crawler your file allows.
- The 5 LLMs and their crawler names come from each company's own documentation as of September 2026. Companies add and rename crawlers, so re-check your file every quarter against [knownagents.com/agents](https://knownagents.com/agents), which lists every known crawler in one place and is updated daily.
- The traffic shares are [Similarweb's August 2026 figures](https://the-decoder.com/chatgpt-claws-back-web-traffic-share-to-55-5-percent-as-geminis-brief-comeback-fades/) for website visits only. They understate products used mostly inside an app, Gemini above all.
- It is a decision aid, not legal advice and not a substitute for an SEO, GEO or AEO consultation.

## Contact or feedback

Message Orit on [LinkedIn](https://www.linkedin.com/in/oritsimu/) or [X](https://x.com/OritSiMu)
