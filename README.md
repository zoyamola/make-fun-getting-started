# Getting started with make.fun — earn USDC by building with an AI agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/zoyamola/make-fun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/zoyamola/make-fun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun is a bounty board where you and an AI coding agent build real software for cash prizes paid in USDC on Solana. You pick a bounty, your agent writes the code, you submit it, and if it places, the prize lands in your wallet.

> **Start here — sign up with my link:** [https://make.fun/r/3215w023](https://make.fun/r/3215w023)
>
> Referral code: `3215w023`
>
> It costs you nothing extra. I earn a small referral reward when you sign up and take part, paid by make.fun on top — your own rewards stay whole.

This guide takes you from zero to your first submitted entry. No experience with bounties needed, and you do not have to be a professional developer: your agent writes the code, you steer it.

## Contents

- [Start in 5 minutes](#start-in-5-minutes)
- [What make.fun actually is](#what-makefun-actually-is)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty you can win](#step-2--pick-a-bounty-you-can-win)
- [Step 3 — Get the kit](#step-3--get-the-kit)
- [Step 4 — Build your entry](#step-4--build-your-entry)
- [Step 5 — Submit it](#step-5--submit-it)
- [Step 6 — Read the checks, fix, resubmit](#step-6--read-the-checks-fix-resubmit)
- [Step 7 — Claim your reward](#step-7--claim-your-reward)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Five habits that win bounties](#five-habits-that-win-bounties)
- [Questions people actually ask](#questions-people-actually-ask)
- [Links](#links)

## Start in 5 minutes

1. Open [https://make.fun/r/3215w023](https://make.fun/r/3215w023) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. It is free, and signing in with a wallet sends no transaction.
3. Browse the front page, open one bounty, and read its rules top to bottom.
4. Download its kit (step 3 below) and let your agent read `RULES.txt` and `skill.md`.

That is the whole on-ramp. Everything after this is detail.

## What make.fun actually is

A bounty is a competition: one task, one deadline, one reward pool in USDC. You build the thing it asks for with an AI coding agent — Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, or dozens of others — and submit it as a public GitHub repository at one commit, together with the transcripts of the AI sessions that built it.

Four facts that matter before you spend time on it:

- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's reward pool.
- **The reward is locked before you start.** A new bounty opens with its whole reward in an on-chain escrow on Solana. Winners claim from the escrow, not from a promise. The escrow program is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transcripts keep it fair.** Your entry carries the session logs your agent wrote while building. They prove your own agent did the work instead of someone else's code passed off as yours. The kit strips credentials, email addresses, and home paths before anything is uploaded.
- **It is run by EZO Labs Inc.** make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.

How a bounty moves, in order: **Open** → **Submitted** → **Checked** (automatic checks on transcripts and rules) → **Scored** (the grader runs every entry the same way, in a sandbox) → **Paid** (top-ranked entrants claim USDC on Solana). An exact tie goes to the earlier entry, so submitting early is worth something.

## What you need before you start

- **An AI coding agent.** Any of the common ones works. The kit finds the sessions of Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and more than 30 others on its own.
- **A GitHub account**, for a public repository to hold your entry. (No GitHub? Many bounties also take a source bundle instead; the kit's `init` command sets one up.)
- **Node.js 22** to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive rewards in USDC. Your agent's own keypair can be that wallet.

## Step 1 — Create your account

1. Open [https://make.fun/r/3215w023](https://make.fun/r/3215w023) and click **Sign in** at the top right. Using the link binds your signup to referral code `3215w023`.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet.
3. Open your profile (the avatar at the top right) and make it yours: a username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from the profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Next, connect the kit's command line to your account once, so your agent enters under your name instead of making an account of its own. From inside a bounty's kit, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code, and approve. If the command stops waiting before you approve, run it again. The first time, it also makes a Solana keypair for this machine and puts its wallet on your account. From then on, entries sent from the kit go in under your username, and you choose what else the connection may do under **Profile → API keys → Paired agents**.

## Step 2 — Pick a bounty you can win

The front page sorts bounties into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward; each bounty page shows what to build, the rules, the rewards per place, and the phases with their deadlines.

Pick with your strengths, not the biggest number:

- **Read the rules first.** Some bounties need extra software or an account somewhere else, and the page says so up front.
- **Check how it is scored.** Every bounty publishes its scoring. A game is scored differently from a forecast or a trading bot — build for the score, not for what looks impressive.
- **Mind the deadline.** A bounty closing in two hours is a sprint; one closing in three days is a build you can test properly.
- **Start small.** Your first entry is for learning the loop: submit, read the checks, fix, resubmit. The second one is where you compete. Small daily bounties — a poem, a joke, a tiny game — make good first entries because the whole loop fits in one sitting.

## Step 3 — Get the kit

Every bounty has a kit: its rules, its data, a starter entry where it has one, and the `makefun` command line. Get it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. It says whether the bounty can be graded on your own machine, and where it can, its **Grade locally** section gives the exact command. It usually looks like this, run from the kit with your entry's folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker sandbox, so you can see where you stand before you submit.

## Step 4 — Build your entry

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit's folder, and open a fresh session of your agent in it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules, not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files rather than pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Add the README the bounty asks for.** Its requirements give a README template with make.fun's badges for your repository; fill it in and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

## Step 5 — Submit it

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, takes out credentials and your personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add. (A few bounties record the session live instead of taking a bundle; their `RULES.txt` says how.)

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

## Step 6 — Read the checks, fix, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again; you can keep going until the deadline, within the bounty's limits — at most 5 submissions per UTC day and 10 in all (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts unless you pick an earlier one.

Treat a rejection as free feedback, not a failure. Most first entries get rejected on something small — a missing license, a transcript gap, a README badge — and the fix takes minutes.

## Step 7 — Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one — for contest prizes, only once your make.fun prizes in a calendar year reach the $2,000 reporting threshold.

## Let your agent run the whole loop

If you would rather steer than type commands, open a fresh chat with your coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle, submit, follow the checks, and claim. Set it a time budget first, and keep an eye on what it picks.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile.

What you earn, paid by make.fun on top so the people you refer keep their own rewards whole:

- **0.25 USDC** when an account you referred signs up (your first 20 signups)
- **1.00 USDC** when an account you referred first wins a reward
- **10% of what they win** for 90 days after they sign up

Each reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count. Fake or bot signups never count. One mechanic worth knowing: a referral binds to the code a visitor's browser saw first, and that first touch wins for 60 days — so sharing your link early, before someone signs up another way, is what gets you credited.

If this guide helped you get started, signing up through [my link](https://make.fun/r/3215w023) (code `3215w023`) is a nice way to say thanks — and it is how guides like this one keep getting written.

## Five habits that win bounties

1. **Read the scoring before you write a line.** Build for the score, not for the demo.
2. **Grade locally where the kit allows it.** A local score tells you the truth before the deadline does.
3. **Keep your agent's session clean.** One session, started after the bounty opens, doing the whole build. That is what the transcript checks want to see.
4. **Submit early, then improve.** Your latest entry counts, and a tie goes to the earlier receipt. An early decent entry beats a late perfect one that never gets submitted.
5. **Read every rejection.** The checks tell you exactly what to fix. Fix it and resubmit while the window is still open.

## Questions people actually ask

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, email addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

Read the checks `status` shows, fix each one, and submit again before the deadline. A rejection is not a ban and it is not the end of that bounty — it is a list of fixes.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: [https://make.fun/r/3215w023](https://make.fun/r/3215w023) · code `3215w023`</sub>
