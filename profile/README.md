<p align="center">
  <img src="https://raw.githubusercontent.com/caravelhq/caravel/master/images/caravel-banner.svg" alt="Caravel" width="480">
</p>

<p align="center"><b>A self-hosted, provider-agnostic staff of named agents — running on your existing AI subscription.</b></p>

# Your own crew of AI agents.
### Running on your machine, on the subscription you already pay for.

Caravel is a self-hosted staff of named agents — a coordinator and her specialists — that runs in the background, takes work over chat, and shows you everything in a live dashboard. On your own infrastructure. No new API bill, no cloud, no third-party chat app required.

[![GitHub stars](https://img.shields.io/github/stars/caravelhq/caravel?style=flat-square)](https://github.com/caravelhq/caravel/stargazers)
[![License](https://img.shields.io/github/license/caravelhq/caravel?style=flat-square)](https://github.com/caravelhq/caravel/blob/master/LICENSE)

---

## A team, not a workflow

Most agent tools give you a graph to configure — nodes, edges, state machines, a Python SDK to babysit. Caravel gives you a roster of named people. Alice coordinates. Bob builds. Ray researches. Each one has its own identity, its own memory, its own rules — so each brings a different perspective and stays focused on its lane, exactly like a real team. You're not splitting one assistant's attention six ways. You're handing the right job to the right specialist.

## It runs on what you already pay for

No separate API subscription, no per-token meter ticking in the background. Caravel runs on your existing coding-agent CLI — the one you're already subscribed to. Point it, start the daemon, and your crew is live. Nothing new to buy.

## Your chat, your infrastructure

Talk to your crew through Caravel's own web dashboard, running on your machine. Want it on your phone from the café? Run a tailscale vpn (we show you how) and the dashboard is securely accessible from any of your devices — still your box, still your network, no cloud in the middle. Nothing about how you talk to your agents has to route through someone else's servers.

## Context that compounds

Your agents get sharper the more you organise your work. Group things into project folders and your crew reads them as context — they learn how you work, not just what you asked. Session logs give them memory of what came before. And when you're juggling several streams at once, each task runs in its own session thread: focused context during rework, no bloat, no cross-pollination between unrelated jobs.

## One limit hits, it keeps going

Caravel is provider-agnostic. If your primary provider hits a wall, it routes to another — Claude Code, GLM, OpenRouter, whatever you've wired up. Your team doesn't stop because one door closed.

## Everything is a file you own

No database. No proprietary cloud. Every agent is a folder on your disk — its identity, its memory, its task queue, all plain files you can read, edit, and back up. Add `agents/bob/agent.json` and Bob shows up everywhere. Delete the folder and he's gone. Nothing about your team lives on someone else's server.

---

## How it works

Say it's Tuesday and you're heads-down on something else.

You open your Caravel dashboard — running on your own machine, or via your VPN — and ask Alice: *"Pull the competitor pricing for the three tools we talked about, and draft a summary I can send the board."* Alice is your coordinator. She already knows the context — the project's in a folder she reads from — so she doesn't ask you to explain the three tools again. She triages the job: research goes to Ray, the write-up goes to Bob. Then she gets back to listening.

The fleet lights up. Ray's queue picks up a task and moves it from *open* to *claimed*. Bob's does the same a moment later. Each runs in its own session thread, so Ray digging through pricing pages doesn't muddy Bob's drafting. You didn't open a terminal. You didn't configure a pipeline. You asked, and the work started.

Ray finishes the research and drops his findings where Bob can pick them up. Bob writes the summary. When the family of tasks is done, Alice consolidates the results and pings you back — *"Here's the draft, Ray's sources are linked at the bottom."*

That's the whole loop. A background daemon, a coordinator who dispatches, named specialists who each work their own thread, and a dashboard so you can see it happen. You run it once and it's just... there, on call, using the subscription you already have — and every project you organise makes the next request land faster.

---

## Who it's for

Caravel is for the solo operator and the small team who want a *staff*, not a *framework*.

If you're one person doing the work of several — running a project, a product, a small business — and you've wished you could hand things off without hiring, this is that. You already pay for a coding-agent subscription. Caravel turns it into a crew that runs in the background: takes requests over chat, works while you're doing something else, and reports back when it's done. The more you organise your work into projects, the more context your crew carries — so it gets better at your work the longer you run it.

It's deliberately *not* built for engineering teams assembling AI pipelines in production. If you want a graph framework with a Python SDK and a state machine, there are excellent ones — LangGraph, CrewAI, the OpenAI Agents SDK — and you should use them. Caravel is the other thing: a personal staff you run yourself, on your own machine and your own network, with everything folder-isolated and nothing proprietary in the loop.

If that sounds like you — you'll know within the first five minutes of running it.

---

## Float your boat in five minutes

Clone, install, ask Alice. That's the whole setup.

```bash
git clone https://github.com/caravelhq/caravel.git
cd caravel
bun install
bash scripts/caravel install    # set up your workspace (one-time, interactive)
```

The installer asks where you want your workspace, seeds your crew there, and generates a `restart-caravel.sh` at the workspace root. Then:

```bash
cd ~/caravel-workspace       # wherever you chose
bash restart-caravel.sh      # daemon + dashboard on http://127.0.0.1:4632
```

> **Requires the [Claude Code CLI](https://claude.ai/download)** installed and authenticated (`claude login`). Caravel spawns workers via the `claude` command — it runs on the subscription you already have.

**[⭐ Star on GitHub](https://github.com/caravelhq/caravel)** · **[🌐 caravel.run](https://caravel.run)**

---

<sub>Built by <a href="https://github.com/kelnorris82">@kelnorris82</a>. Everything is a file. Nothing is proprietary.</sub>
