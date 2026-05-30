## name projects when start
* start new session via: claude -n "my-project" in your terminal.
* To rename: /rename my-project while you are currently chatting.
* resume a session: claude -r "my-project" from your terminal.
* resume through /resume and select interactive menu

## When to useL Skill, Slash Command, Sub-Agent
Skills are specialized instructions you may want to provide to Claude in certain circumstances, but may not always be relevant. 
Slash commands are specialized commands you may want to invoke manually in certain circumstances. 
Sub-agents are specialized ppl that you want to offload specific types work to fresh contexts backed by a full agent instance.

use subagents
* to keep your context clean
* when you want an actual full agent instance to perform something w/o poisoning your main context
* For example: code reviewer, skeptic, testing specialist, language/framework specialist, architect, etc).

Use skills 
* when you want to sometimes provide instructions to your primary agent with a relevant skillset.

Use slash commands 
* when there are things you specifically know you’ll want to invoke at certain points.
