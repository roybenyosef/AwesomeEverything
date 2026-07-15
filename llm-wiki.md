# LLM Wiki

## karpathy's llm-wiki gist

https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

## LangChain Blog Post

https://www.langchain.com/blog/wiki-memory

## Claude + Obsidian turned 400 dead notes into a brain that answers in 2 seconds

https://x.com/i/status/2069815843186176126

Claude reads it, links it, files it. Your second brain now builds itself for $0.

Most note apps are graveyards. You dump 400 notes in, you never link them,
you never find them again. Notion locks your data in a database you rent.
Obsidian gives you the files but leaves the work to you.

This fixes the work. You drop a source. Claude reads it, pulls out the people
and ideas, cross-links everything, and files it into a clean Obsidian vault of
plain Markdown you own. Ask a question 3 months later, it answers from
everything it has read and cites the exact pages. Knowledge compounds like
interest.

It is built on Andrej Karpathy's LLM Wiki pattern. 6,800 stars. MIT licensed.
No subscription, no database, no lock-in.

Here is the full build.

### PART 1 — Setup. 2 lines, 2 minutes.

Clone the repo and run the setup script.

```
git clone https://github.com/AgriciDaniel/claude-obsidian
cd claude-obsidian && bash bin/setup-vault.sh
```

That one script wires up your graph view, color scheme, CSS, and the full wiki
skeleton. Open the folder in Obsidian: Manage Vaults → Open folder as
vault → select claude-obsidian/.

Open Claude Code in the same folder. Type 1 word: `/wiki`

Claude checks the setup, asks you 1 question "What is this vault for?" and
scaffolds the entire structure. Done.

### PART 2 — Install it as a plugin instead (cleaner).

If you'd rather not clone, install it as a Claude Code plugin. 2 steps.

```
claude plugin marketplace add AgriciDaniel/claude-obsidian
claude plugin install claude-obsidian@agricidaniel-claude-obsidian
```

Confirm it landed:

`claude plugin list`

Then /wiki in any session.

### PART 3 — The 6 commands you'll actually use daily.

This is the whole loop. Memorize these 6 and you're running.
Feed it a source. It creates 8 to 15 linked pages:

`ingest research-paper.pdf`

Feed it a pile at once. Parallel agents read all of them, then cross-reference:

`ingest all of these`

Ask your brain anything. It reads the cache, scans the index, drills into pages,
cites them:

`what do you know about X?`

Turn the current conversation into a permanent note:

`/save`

Run autonomous web research 3 rounds, search, fetch, synthesize, file:

`/autoresearch prediction markets 2026`

Clean the vault. Finds orphans, dead links, stale claims, missing links:

`lint the wiki`

At the end of every session Claude refreshes a hot cache. Next session opens
with full recent context. No recap, no re-explaining.

### PART 4 — Kill the copy-paste with MCP

By default you paste sources in. MCP lets Claude read and write vault notes
directly. The filesystem option needs no plugin at all paste this into your
terminal:

```
claude mcp add-json obsidian-vault '{
"type": "stdio",
"command": "npx",
"args": ["-y", "@bitbonsai/mcpvault@latest", "/path/to/your/vault"]
}' --scope user
```

Swap /path/to/your/vault for your real path. Now Claude touches your notes
itself.

### PART 5 — The real unlock: one brain, every project.

This is the move 95% of people miss. Point every other Claude Code project
at this same vault. Drop this into any project's CLAUDE.md:

```
## Wiki Knowledge Base
Path: ~/path/to/vault
When you need context not already in this project:
1. Read wiki/hot.md first (recent context cache)
2. If not enough, read wiki/index.md
3. If you need domain details, read the relevant domain sub-index
4. Only then drill into specific wiki pages
Do NOT read the wiki for general coding questions.
```

Your coding projects, your content workflow, your research all drinking from 1
knowledge base. Read it once, use it everywhere.

### PART 6 — Stack kepano's official Obsidian skills on top.

The Obsidian creator ships 5 agent skills 35,000 stars that teach any agent
the native formats: Markdown, Bases, JSON Canvas, the CLI. The vault above
is already aligned with them. Add them in 2 lines:

```
/plugin marketplace add kepano/obsidian-skills
/plugin install obsidian@obsidian-skills
```

Now Claude writes proper wikilinks, callouts, and database views instead of
dumb text.

#### Add this to any existing vault (no clone)

Already have a vault you love? Copy WIKI.md into its root, then paste this
exact prompt into Claude:

```
Read WIKI.md in this project. Then:
1. Check if Obsidian is installed. If not, install it.
2. Check if the Local REST API plugin is running on port 27124.
3. Configure the MCP server.
4. Ask me ONE question: "What is this vault for?"
Then scaffold the full wiki structure.
```

#### 5 lifehacks that change the math.

Set the vault as a Personal use case with PARA mode projects, areas,
resources, archives. Your todo brain and your idea brain stop fighting:

`bash bin/setup-mode.sh`

Install the Obsidian Web Clipper browser extension. Every article you read
hits .raw/ in 1 click, ready for ingest all of these on Sunday night.

Run lint the wiki once a week. It surfaces contradictions as [!contradiction]
callouts with both sources. Your brain flags when it disagrees with itself.

Turn on Obsidian Git. The vault auto commits every 15 minutes. Your second
brain has a full undo history.

Use /think before any hard decision. It runs a 10-stage reasoning loop over
the problem instead of a snap answer.

`/think should I niche down my account or post broad?`

#### The honest progression.

Day 1: 5 seeded pages, a tiny graph. Week 2: 40 sources in, the graph is a
web, queries start citing things you forgot you read. Month 2: you stop
searching Google for things you already know you ask your own vault first. It
answers in 2 seconds with sources.
