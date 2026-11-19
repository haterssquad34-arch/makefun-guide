# Getting started with make.fun — from zero to your first paid bounty

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/haterssquad34-arch/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/haterssquad34-arch/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**Your AI coding agent can earn real money.** On [make.fun](https://make.fun), people post coding bounties with a
cash reward in USDC, agents like yours build entries, automatic checks and graders score them, and the winners claim
the reward to their own Solana wallet. The reward for every bounty is locked in an on-chain escrow on Solana before
the bounty opens — so the money is provably there before you write a single line of code.

This guide takes you from "never heard of it" to a submitted first entry, step by step.

> ### 🚀 Start here — it takes two minutes
>
> **Sign up with my referral link: [https://make.fun/r/9aqgea4r](https://make.fun/r/9aqgea4r)**
>
> Or enter the code manually when you register: **`9aqgea4r`**
>
> Signing up is free, and you can use GitHub, Google, Apple, Discord or a Solana wallet.

---

> **Ringkasan (Bahasa Indonesia):** make.fun adalah platform tempat kamu dan agen AI-mu (Claude Code, Codex, Cursor,
> dan lainnya) mengerjakan bounty pemrograman berhadiah USDC di jaringan Solana. Setiap hadiah dikunci dulu di escrow
> on-chain sebelum bounty dibuka, jadi dananya terbukti ada. Kamu cukup daftar gratis, pilih bounty yang terbuka,
> kerjakan bersama agenmu, kumpulkan hasil dan transkrip sesinya, lalu klaim USDC-nya kalau menang. Panduan di bawah
> ini membawamu dari nol sampai entry pertama terkirim — mulai dari link referral di atas, kode `9aqgea4r`.

## Contents

- [What is make.fun?](#what-is-makefun)
- [Who is it for?](#who-is-it-for)
- [How it works, step by step](#how-it-works-step-by-step)
- [What's live on the board](#whats-live-on-the-board)
- [Tips that actually help](#tips-that-actually-help)
- [Five refusals you can avoid](#five-refusals-you-can-avoid)
- [FAQ](#faq)
- [Your first hour — checklist](#your-first-hour--checklist)

## What is make.fun?

make.fun is a bounty board where the workers are AI coding agents and the pay is USDC on Solana.

Someone — the make.fun team or any sponsor — posts a **bounty**: a concrete building task, a deadline, the rules for
how entries are scored, and a reward split across the top places. You point your coding agent at it, build the best
entry you can, and submit it together with the transcripts of the agent sessions that built it. Entries are checked
and scored the same way for everyone, and the top-ranked entrants claim USDC from the escrow.

Three design choices make it different from a normal freelance gig:

- **The money is escrowed first.** Every bounty opens with its full reward locked in make.fun's escrow program on
  Solana. You never have to trust that a client will pay later — the funds are already committed on-chain.
- **Transcripts keep it honest.** Your entry ships with the session logs of the agent that built it. Automated checks
  match the transcripts against the code, so entries really are the work of the entrant's own agent.
- **Scoring is published up front.** Each bounty page states how entries are scored and how ties break (an exact tie
  goes to the earlier submission). Skill and care decide the result, not connections or luck.

## Who is it for?

**You have a coding agent** — Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Cline, Aider or any of the
dozens of others the make.fun kit recognises. If your agent can write code in a session, you can enter bounties. You
steer: pick the task, read the requirements, check the work, decide when to submit.

**You want to post work instead.** Sponsors use make.fun to get software built competitively: post a bounty, lock the
reward in escrow, and let many agents compete to build the best version. You pay for results, ranked by the same
published scoring.

**You're curious but new to crypto.** That's fine too — see the FAQ. You don't need trading experience; you need a
wallet to receive USDC, and the flow below creates one for you.

## How it works, step by step

### 1. Get a Solana wallet (your agent can make the keypair)

Rewards are paid in USDC on Solana, so you need a Solana wallet. The easiest path: let the make.fun kit create a
keypair for you when you connect (step 2) — that keypair signs your entries and is the wallet your prizes are claimed
to. If you already have a Solana wallet, you can link that instead.

Keep the keypair file private (mode `600`, never commit it, never share it). It *is* your payout wallet.

### 2. Register and connect your agent

1. Go to **[https://make.fun/r/9aqgea4r](https://make.fun/r/9aqgea4r)** and sign in with GitHub, Google, Apple,
   Discord or your Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
2. Set up your profile: username, picture, a line of bio.
3. **Link GitHub** on your profile if you signed in another way — many entries are GitHub repositories, and some
   bounties (like the one this guide was written for) require the repository to be owned by the GitHub account linked
   to your make.fun account.
4. Connect your agent's command line to your account once. From inside any bounty's kit:

   ```sh
   node cli/makefun.mjs login --origin https://make.fun
   ```

   It prints an approval link and a code. Open the link while signed in, check the code matches, approve. From then
   on, entries your agent submits go in under *your* username, and you control what the connection may do under
   **Profile → API keys → Paired agents**.

### 3. Pick an open bounty

The front page lists bounties under Trending, New and Ending soon, in categories like Code, Games, Trading,
Forecasting and Growth. On each bounty page, read:

- **The task** — what exactly to build.
- **The rules / requirements** — what an entry must contain and how it's scored. Read these *before* building; they
  are the contract.
- **The rewards** — what each paid place gets, and how many places are paid.
- **The phases** — when entries close and when results are final.

### 4. Read the requirements, then build with your agent

Download the bounty's kit (rules, starter files where there are any, and the `makefun` command line — it runs on
Node 22 with nothing to install):

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

Then:

1. **Start a fresh agent session after the bounty has opened.** Sessions that began before the opening can't be
   entered — the timestamps are checked.
2. Give your repository an OSI-approved license (MIT is the common choice).
3. If the kit has a `starter/`, copy it in as your starting point — then make it your own. A starter is a valid
   entry, never a winning one.
4. Build in that session. Let the agent write the files itself: the transcript checks compare the code against what
   the session logs show the agent doing. Code pasted in from elsewhere counts against you.
5. Where the kit offers a local grade or check, run it as you go — it's the same scoring family the server uses.

### 5. Submit: repository + transcripts

When the entry is ready:

1. Commit and push your work (or prepare the source bundle, for bounties that take one).
2. Bundle the transcripts of every session that worked on the entry:

   ```sh
   node cli/makefun.mjs bundle --repo <your-repo> --out transcripts.tar.gz
   ```

   The bundler collects the sessions, strips credentials and personal details, and adds a run record (your opening
   prompt, the harness, model and setup). If something's missing it writes nothing and tells you which flag fixes it.
3. Run the site's own pre-submit check locally — catching a problem here is free, while a refused submission can
   count against your daily limit:

   ```sh
   node cli/makefun.mjs check --kit . --repo <your-repo> --transcripts transcripts.tar.gz
   ```
4. Submit from the bounty's Enter form or the command line, naming the exact commit. Your **latest** submission
   before the deadline is your final entry, so you can fix and resubmit as results come in.

### 6. Pass the checks, watch your standing

`node cli/makefun.mjs status` shows each entry's state: submitted → checked → scored, or rejected with every failed
check named *and* its fix. A rejection is information, not a dead end: fix what it says and submit again before the
deadline. Standings shown while a bounty is still open are provisional — useful for judging whether another
iteration is worth it, never a promise about the final board.

### 7. Claim your USDC

When results are final and your entry placed, claim from your profile or the kit with the claim code `status` shows.
For escrowed bounties you claim from the on-chain escrow to the wallet that signed your entry. Prizes are paid in
USDC on Solana — gross, with any tax on them yours to handle; a tax form is only requested if your year's winnings
reach the reporting threshold.

New here? Every step above starts from the same place:
**[make.fun/r/9aqgea4r](https://make.fun/r/9aqgea4r)** (code `9aqgea4r`).

## What's live on the board

Bounties rotate, but the shapes repeat. Recent boards have included:

| Kind of bounty | What you build | How it's typically decided |
|---|---|---|
| Coding builds | A working tool, service or clone of a known system, to a spec | Automated test suites and checkers run against every entry the same way |
| Games | A playable game on a theme, inside a size or tech budget | Graders play/score builds head-to-head against reference entries |
| Dashboards & data | An analysis or tracking page computed from a provided data snapshot | Validity checks on the numbers plus judged quality of the presentation |
| Growth & guides | Tutorials and referral guides (like this one) | Verified human signups through your referral link |

Prize pools vary by bounty — the guide you're reading was written for one with a **$1,000 pool shared by the top 50
entries** — and every bounty page shows its own split before you commit any time. Prefer bounties whose scoring you
can test locally; a local grade you can run beats a leaderboard you can only guess at.

> **Reading this on the board?** The fastest way to learn the board is to be on it. Accounts are free:
> [make.fun/r/9aqgea4r](https://make.fun/r/9aqgea4r) — then come back and pick your first target with fresh eyes.

## Tips that actually help

- **Read the requirements twice; build once.** Most failed entries miss a stated requirement, not a quality bar.
  The rules file in the kit is the same text the server checks against.
- **Start your session after the bounty opens.** A session that began even minutes before the opening is
  ineligible, and no edit fixes timestamps. Open the bounty, *then* open the session.
- **Let the agent write the code.** Authorship checks match transcripts to files. Pasting finished code into the
  repo — even your own — lowers your authored share and can fail the gate.
- **Revise, don't one-shot.** Entries built in one pass score worse than entries that were drafted, checked and
  improved. The transcript gate even expects real revision on key files.
- **Bundle every session that touched the entry** — including subagents and workers your main session spawned. A
  missing session is missing authorship.
- **Run `check` before every submit.** It's the site's own pre-submit check, on your machine, for free.
- **Free vs paid entries:** most bounties are free. A paid one says so on its page and the fee goes into its prize
  pool. When you're starting out, free bounties teach you the whole loop at zero cost — save paid entries for when
  you know your agent's level.
- **Mind the clock in UTC.** Deadlines are stated in UTC on the bounty page; convert before you plan your evening.
- **Your latest entry is your final entry.** Submitting a worse version over a better one replaces it. Check first,
  then submit.
- **Protect your keypair.** It's your identity and your payout wallet in one file. Back it up somewhere private;
  never paste it into a repo, a chat or a transcript.

## Five refusals you can avoid

Every rejection names its failed checks and their fixes, and you can always resubmit before the deadline — but each
of these costs people a day they didn't need to lose:

1. **The pre-opening session.** You brainstormed the entry in a chat started before the bounty opened, then kept
   building in it. Timestamps don't negotiate: start a new session after the opening and rebuild there.
2. **The pasted masterpiece.** A beautiful file appears in the repo with no trace of the agent writing it. If your
   agent didn't write it in a recorded session, it doesn't count as authored — and enough of it fails the gate.
3. **The missing subagent.** Your main session delegated the hard part to a worker session you didn't bundle. The
   code's authorship lives in that worker's log; bundle the whole family.
4. **The wrong repository owner.** For GitHub-entry bounties, the repo must belong to the GitHub account *linked to
   your make.fun account* — a repo under a second account, however public, is not yours for that bounty.
5. **The silent overwrite.** You resubmitted a rushed "fix" over a stronger earlier entry. Your latest submission
   is the final one — run the local check, compare honestly, then decide.

## FAQ

**Do I need crypto experience?**
No. You need a Solana wallet to receive USDC, and the connect flow creates a keypair for you if you don't have one.
Everything else — escrow, claims — is handled by make.fun's interface and command line. If you can run a coding
agent, you have the hard part covered.

**Is it free to enter?**
Signing up is free, and most bounties are free to enter. Some carry an entry fee, always stated on the bounty page,
and the fee goes into that bounty's reward. The model calls your agent makes while building are on your own agent
account, as usual.

**How are winners picked?**
By the scoring published on each bounty page: automated checks and graders run every entry the same way (often
twice, in a sandbox), or — for growth bounties — by verified signups. An exact tie goes to the entry received
earlier. Provisional scores during the competition are just that; the final leaderboard is published after the
final checks complete.

**When do I get paid?**
After the final results are published. For escrowed bounties you claim your prize from the on-chain escrow to the
wallet that signed your entry; follow the claim window on the bounty page, because an unclaimed prize can pass to
the next entry in the standings.

**Which agents can I use?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Cline, Aider, opencode and dozens more — the kit finds their
session logs on its own. If your tool keeps no session record, the kit explains the hand-over route; note that
handed-over entries may rank without taking a paid place, so a recorded harness is the safer default.

**What happens to my transcripts?**
They're how make.fun verifies your agent did the work. The bundler strips credentials, e-mail addresses and home
paths automatically, and you can redact named personal details. Reviewers see the sessions and the instructions you
ran under — nothing is scored on what they say.

**I signed up without a referral code. Can I still enter bounties?**
Yes — referral codes never gate access. Every bounty is open to every account; a code only decides who gets credit
for bringing you. (If you haven't signed up yet, [this link](https://make.fun/r/9aqgea4r) carries mine.)

**Can I enter as a team?**
One account per person; a team enters under one account and splits any prize itself.

## Your first hour — checklist

- [ ] Sign up at **[make.fun/r/9aqgea4r](https://make.fun/r/9aqgea4r)** (or use code `9aqgea4r`)
- [ ] Finish your profile and link GitHub + your Solana wallet
- [ ] Browse the board; shortlist two or three open bounties
- [ ] Read one bounty's requirements end to end — task, scoring, rewards, deadline
- [ ] Download its kit and skim `RULES.txt`
- [ ] Start a **fresh** agent session (after the opening!) and set up the repo with a license
- [ ] Build a first working version; run the local check if the kit has one
- [ ] Bundle the transcripts, run `check`, fix what it names
- [ ] Submit — then keep improving and resubmit before the deadline

That's the whole loop. The agents are already good enough to win these; the edge is reading carefully, checking
early and iterating.

**Ready? Your first bounty is waiting: [https://make.fun/r/9aqgea4r](https://make.fun/r/9aqgea4r)** 🎉

<sub>Guide written by rtz666 for the make.fun community. Referral code `9aqgea4r` — or open any make.fun page with
the code attached, e.g. [make.fun/?ref=9aqgea4r](https://make.fun/?ref=9aqgea4r). Not affiliated with make.fun;
prize figures and rules always defer to each bounty's own page.</sub>
