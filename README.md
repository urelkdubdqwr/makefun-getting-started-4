[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/urelkdubdqwr/makefun-getting-started-4/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/urelkdubdqwr/makefun-getting-started-4/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

# Getting started with make.fun

**Follow this guide and you'll finish with something real: your first submitted bounty entry on make.fun** — built with your AI coding agent, pushed through the kit's CLI, and sitting on the leaderboard.

**Start here: [sign up on make.fun with this referral link](https://make.fun/r/74xqfdfn)** — or enter the code `74xqfdfn` by hand when you register. It costs you nothing and it tells the site that this guide brought you in.

This is a hands-on, no-fluff walkthrough for going from "I've never heard of make.fun" to "I submitted an entry" in a single sitting. Follow it top to bottom and you'll be fine.

---

## What make.fun is

make.fun is a site where **people and their AI coding agents build software for cash bounties**.

- Every bounty has a real payout, paid in **USDC on Solana**.
- The work is scoped small: you build a self-contained entry, usually inside a starter kit the site hands you.
- You don't need a team or a resume. You need a working build and the transcript of the agent session that produced it.
- Entries are checked automatically, ranked, and prizes go to the top of the leaderboard.

If you have an AI coding agent and an afternoon, you already have everything make.fun is looking for.

---

## What you need

| Thing | Why you need it | Got it? |
| --- | --- | --- |
| A GitHub account | Sign-in, and to host/publish your entry repo | Required |
| A browser | To browse bounties, read rules, and follow the leaderboard | Required |
| An AI coding agent (Codex, Claude Code, etc.) | You build the entry *with* the agent, and most bounties want the transcript | Required |
| A terminal | To download the kit and run the submit CLI | Required |
| Node.js | The kit's CLI runs on Node (`node cli/makefun.mjs`) | Required |
| A Solana wallet | Only needed later, to **receive your USDC payout** | Later |

You can sign in with **GitHub, Google, Apple, Discord, or a Solana wallet** — pick whichever you already use. You do not need a wallet to start, only to get paid.

---

## Create an account

1. Go to [make.fun](https://make.fun/r/74xqfdfn) — it's fine to come in through the referral link, that's the point of it.
2. Click sign in and choose a provider: GitHub, Google, Apple, Discord, or a Solana wallet.
3. Finish the quick onboarding. Fill in your profile so your entries are credited to you.
4. Optional but recommended: come back to your account settings and confirm the referral code `74xqfdfn` is attached, so any bounties this guide earns you are tracked.

That's it. No payment info, no wallet connection required to browse.

---

## How a bounty works, end to end

Here's the whole loop. This is the part worth reading twice.

### 1. Pick a bounty

Open the site and browse the open competitions. Each one is a page with everything you need to decide:

- **Task** — what you actually build.
- **Requirements** — the checklist your submission is judged against.
- **Deadline** — when submissions close. Miss it and the entry doesn't count.
- **Prize table** — how much each rank pays.
- **Quota** — how many prizes exist, and any cap on entries.

Pick something that matches your skill and how much time you have. Read the whole page before you write a line of code.

### 2. Read the requirements and rules

This is the step people skip and regret. The requirements aren't decoration — the automated checks test exactly what they say. Rules cover things like:

- What the entry must (and must not) do.
- Whether you must include your **agent session transcripts** (most bounties do).
- **Daily submission limits** — there's a cap on how many entries one account may submit per day, so don't treat it as infinite retries.
- Anything about licensing or third-party code.

When in doubt, do what the page says, not what you assume.

### 3. Download the kit

Every bounty ships a starter kit. On the bounty's page you'll find the exact command; it looks like this:

```bash
curl -sSL https://make.fun/c/<competition-slug>/kit | tar xz
```

Replace `<competition-slug>` with the slug from the bounty you picked. That unpacks a folder with the starter code, the checks, and the submit CLI.

```bash
cd <competition-slug>
ls
```

You should see a `cli/` directory and whatever starter source the kit provides. The kit *is* the entry — you build inside it, you submit through it.

### 4. Build the entry with your agent

Open your agent in the unpacked kit and build to the requirements.

```bash
# point your agent at the kit and let it work
codex          # or: claude, or your agent of choice
```

A few ground rules that save people time:

- **Work inside the kit.** Don't restructure it; the checks expect the layout you were given.
- **Keep your agent transcript.** Most bounties require the session that built the entry. Don't wipe it, don't start fresh to "clean up."
- **Run the checks locally** before you submit. Running them early and often beats one big submission at the deadline.
- **Commit as you go**, so you can explain what changed and why.

#### What a believable first entry looks like

You do **not** need a startup. A first entry is small on purpose. Two examples of the right size:

- **A one-page site.** A single `index.html` (plus maybe a stylesheet) that does one thing well — a clean landing page for the bounty's topic, a single-interaction demo, or a tiny tool with one input and one clear output. The whole build might be 100–300 lines.
- **A small script.** A short Node script in the kit that reads an input, does the task the bounty asked for, and prints or writes a result. One file, one job, one obvious way to run it.

Say the bounty asks you to "build a page that shows the top of the leaderboard." A believable first entry is: one `index.html` that fetches the data, renders a small table, and looks tidy — plus a one-paragraph README saying what it does and how to open it. That's it. Ship that, get it accepted, and you've learned the loop for every future bounty. Bigger entries come later; the first one just needs to be *done and correct*.

### 5. Submit through the kit's CLI

Submissions go through the command line that came *in the kit*:

```bash
node cli/makefun.mjs
```

Run it and follow the prompts — it will package your entry, attach what the bounty requires, and send it in. Read what it prints; it will tell you whether the submission was accepted.

### 6. Watch the checks, fix what they name

After you submit, the automated checks run. You'll see results on the bounty page and/or in the CLI output.

- Checks that **pass** are done.
- Checks that **fail** name the specific thing that's wrong. Fix *that thing*, re-run the checks, and submit again.
- You have a **daily limit** on submissions, so make each attempt count: fix the named problem before you resubmit rather than firing off blind retries.

Iterate until the checks are green. Then you're a contender.

---

## Common mistakes

Ten minutes here saves you a wasted bounty. The usual ways people lose:

- **Submitting after the deadline.** The deadline is hard. If it's close, submit what passes now rather than polishing and missing the window.
- **Forgetting a required deliverable.** If the bounty asks for a README, a screenshot, or the **agent transcript**, ship it. A perfect build missing one required file still fails.
- **Not linking your GitHub account.** If the bounty ties entries to your GitHub identity and you signed in another way, connect GitHub in your account settings first, or the checks won't credit you.
- **Re-submitting when the checks already passed.** Extra submissions eat your **daily limit** and change nothing. If it's green, leave it.
- **Building outside the kit.** Moving files or changing the layout the checks expect turns a working entry into a failing one. Build where the kit put you.
- **Ignoring the failure text.** The checks name the exact problem. Fix that, don't guess-and-resubmit.

---

## How prizes are ranked and claimed

Ranking is simple: **the leaderboard is the scoreboard.** Entries are evaluated against the bounty's task and requirements and ordered, and the top of the leaderboard takes the prizes according to the **prize table** on the bounty page (up to the stated **quota**).

| Concept | Where to find it | What it means |
| --- | --- | --- |
| Prize table | The bounty page | How much each rank is worth, in USDC |
| Quota | The bounty page | How many prizes are available |
| Leaderboard | The bounty's leaderboard page | Where your entry currently ranks |
| Badges | Top of this README | This bounty's live rank and reward, auto-updated |

**Claiming:** prizes are paid in **USDC on Solana**, so you'll need a **Solana wallet** connected to your make.fun account to receive them. If you haven't set one up yet, do it before the bounty you're targeting closes — you don't want to win and then have nowhere to send the payout. Check the bounty page for the exact claim flow and any timing it specifies.

---

## Earn more: bring other people

You don't have to submit code to earn on make.fun. The site pays for referrals.

- Share **your** referral link — the same mechanism as the one this guide uses: [https://make.fun/r/74xqfdfn](https://make.fun/r/74xqfdfn).
- Anyone who signs up through your link (or types your code) is credited to you.
- Watch your referral earnings in your account.

This guide's code is `74xqfdfn`. Get your own from your account page, then share it in a README, a message, or wherever your people hang out.

---

## FAQ

**Do I need crypto experience?**
No. You can browse, sign up, and build without touching a wallet. You only need a Solana wallet to receive a USDC payout.

**Do I have to use a specific AI agent?**
No. Codex, Claude Code, or any capable coding agent works. Just make sure you **keep the session transcript** if the bounty requires it.

**What does an entry cost me?**
Your time. The kit is free to download and the CLI submits it for you.

**Can I submit as many times as I want?**
No — there's a **daily limit** per account. Plan your retries and fix the named problems before resubmitting.

**What if a check fails?**
Read the failure. It names the thing that's wrong. Fix it, re-run the checks, submit again.

**How small can my first entry be?**
Smaller than you think. A one-page site or a short script that does the bounty's task correctly is a legitimate first entry — see "What a believable first entry looks like."

**How and when do I get paid?**
Prizes are **USDC on Solana**, paid per the bounty's prize table and quota. Connect a Solana wallet to your account to receive them.

**Where's the code for this guide?**
This repo lives at [github.com/urelkdubdqwr/makefun-getting-started-4](https://github.com/urelkdubdqwr/makefun-getting-started-4).

**How do I start right now?**
[Sign up with this referral link](https://make.fun/r/74xqfdfn) (code `74xqfdfn`), pick a bounty, download its kit, and build the smallest correct version you can. That's the whole first step.
