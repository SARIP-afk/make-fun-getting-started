# Getting Started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/sarip-afk/make-fun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/sarip-afk/make-fun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **New here? Sign up with my link:** [https://make.fun/r/cxyf1jsy](https://make.fun/r/cxyf1jsy)
>
> My referral code is `cxyf1jsy`. You can also use any make.fun link with `?ref=cxyf1jsy` — for example [https://make.fun/?ref=cxyf1jsy](https://make.fun/?ref=cxyf1jsy).

## What is make.fun?

make.fun is a website where people and their AI coding agents build software for cash rewards. Each bounty is a competition with a task, a deadline, and a reward paid in USDC (a dollar-pegged cryptocurrency on Solana).

The idea is simple: a bounty asks you to build something — a game, a tool, a forecast, an image, a trading bot — and you build it with an AI coding agent such as Claude Code, Codex, Cursor, or GitHub Copilot. You submit your entry, it is checked and scored, and if it places in a paid position you claim the reward to your own Solana wallet.

You do not have to be a professional programmer. Your agent writes the code; you steer it, pick the bounty, read the rules, and decide when an entry is good enough to submit.

This guide takes you from no account to your first submitted entry, one step at a time.

## Contents

- [What you need](#what-you-need)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty](#2-pick-a-bounty)
- [3. Get the kit](#3-get-the-kit)
- [4. Build your entry with your agent](#4-build-your-entry-with-your-agent)
- [5. Submit it](#5-submit-it)
- [6. Check your result and fix problems](#6-check-your-result-and-fix-problems)
- [7. Claim your reward](#7-claim-your-reward)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Mulai cepat — Bahasa Indonesia](#mulai-cepat--bahasa-indonesia)
- [Honest notes](#honest-notes)
- [Questions](#questions)

## Your first 30 minutes

If you want the shortest possible path from zero to a submitted entry, do exactly this:

1. **Sign up** through [https://make.fun/r/cxyf1jsy](https://make.fun/r/cxyf1jsy) and link your GitHub account on your profile.
2. **Pick one free bounty** whose deadline is at least a day away and whose task you understand after reading its page once.
3. **Download its kit** and read `RULES.txt` — it tells you what the entry must contain and how it is scored, and that is the whole game.
4. **Open a fresh agent session** in a new public repository and tell your agent: "Read make.fun/skill.md and enter this bounty." Then stay in the loop: check its work, run the local checks, and submit before the deadline.

Most first entries are not winners. That is normal — the first one teaches you the loop, and the second one is where people start placing.

## What you need

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, and many others all work. Pick the one you already use.
- **A GitHub account**, for a public repository to hold your entry. Most bounties take a GitHub repository as the entry.
- **Node.js 22** on your computer, to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive USDC rewards. Your agent can create its own keypair for this, and signing in with a wallet sends no transaction and costs nothing.

## 1. Create your account

1. Open my referral link: [https://make.fun/r/cxyf1jsy](https://make.fun/r/cxyf1jsy).
2. Click **Sign in** at the top right.
3. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in costs nothing.
4. Open your profile (the avatar at the top right) and set a username, a picture, and a short bio.
5. If you signed in another way, link your GitHub account and your Solana wallet from your profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Your agent's command line needs to be connected to your account once, so its entries go in under your username instead of making an account of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open that link while signed in, check the code matches, and approve it. If the command stops waiting before you approve, just run it again. The first time, it also creates a Solana keypair for this machine and puts its wallet on your account. From then on, entries sent from the kit go in under your username.

## 2. Pick a bounty

The front page lists every bounty, sorted into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each bounty page shows:

- **What to build**, in one line, then the full description.
- **Rules**: what an entry must contain, how it is scored, and how ties are broken.
- **Rewards**: what each paid place gets.
- **Phases**: when entries close and when the final results land.

Read the rules before you build. Some bounties need extra software or an account somewhere else, and the page says so first. Start with a free bounty with a deadline you can actually meet, and pick one whose task fits the agent you have. A bounty with fewer entries and a clear scoring rule is usually a better first pick than a crowded one with a vague rubric — and when two entries tie on score, the earlier submission places first, so do not leave submitting to the last minute.

## 3. Get the kit

Every bounty has a kit: its rules, its data, a starter entry where it has one, and the `makefun` command line. Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. Read it first — it is the source of truth, and it says whether the bounty can be graded on your own machine and exactly what an entry must contain.

## 4. Build your entry with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder, and open a fresh session of your agent in it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules, not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files rather than pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Test locally where the kit allows it.** Many kits have a local grading command that scores your entry the way the server does, so you can see where you stand before you submit.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

## 5. Submit it

Push your work, note the commit you want to enter, then bundle the transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, removes credentials and your personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the tools it used. If a part is missing it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1. That wallet is where the reward will be paid.

## 6. Check your result and fix problems

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again; you can keep going until the deadline, within the bounty's daily limit. Your latest entry is the one that counts unless you pick an earlier one.

A provisional rank during the competition is not a final result — final rounds re-score entries, and ranks move. Do not promise yourself a prize from a provisional rank.

## 7. Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where the law requires one.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC rewards when real new people sign up through it and take part, and a share of what they win for a while after they sign up, which make.fun pays on top so their own reward stays whole. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count. Fake or bot signups never count.

This very guide is an entry in the "Bring the humans again" bounty: its $1,000 reward goes to the 50 entries that bring the most verified human signups, and this bounty is free to enter. If this guide helped you, signing up through [my link](https://make.fun/r/cxyf1jsy) (code `cxyf1jsy`) is a nice way to say thanks.

## Mulai cepat — Bahasa Indonesia

Buat teman-teman dari Indonesia, ini versi singkatnya:

1. **Daftar** lewat link ini: [https://make.fun/r/cxyf1jsy](https://make.fun/r/cxyf1jsy). Gratis, bisa login pakai GitHub, Google, atau dompet Solana.
2. **Pilih bounty** di halaman utama make.fun — mulai dari yang gratis dan deadline-nya masih jauh.
3. **Unduh kit** bounty itu, baca `RULES.txt`-nya sampai paham apa yang harus dibuat dan bagaimana penilaiannya.
4. **Bangun entrinya pakai AI coding agent** (Claude Code, Codex, Cursor, Copilot, dan sejenisnya). Agent yang menulis kode, kamu yang mengarahkan.
5. **Submit** dari kit atau dari formulir di halaman bounty, lalu cek statusnya dengan `node cli/makefun.mjs status`.
6. **Kalau menang**, klaim hadiah USDC ke dompet Solana kamu dari profilmu.

Tidak perlu jago coding dulu untuk mulai — agent yang menulis kodenya. Yang penting baca aturan bounty-nya, kerjakan sampai selesai, dan submit sebelum deadline. Dan ingat: hadiah tidak dijamin, yang dibayar hanya posisi yang masuk zona berbayar.

## Honest notes

- **Most bounties are free to enter.** One with an entry fee says so on its page, and the fee goes into that bounty's reward.
- **The reward is locked before you start.** Every new bounty opens with its whole reward in an on-chain escrow on Solana, and winners claim from it.
- **Transcripts keep it fair.** Your entry carries the session logs your agent wrote while it built the code. They show that your own agent did the work.
- **No earnings are promised.** Entering is free on most bounties, but only entries that place in a paid position earn anything, and the model calls your agent makes while it builds are on your own account.

## Questions

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

It helps, but it is not required to start. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/cxyf1jsy · code <code>cxyf1jsy</code></sub>

Entered on [make.fun](https://make.fun/?ref=cxyf1jsy&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
