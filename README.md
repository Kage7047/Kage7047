### Hi, I'm Ilya 👋

Backend, full-stack and DevOps engineer based in Warsaw. I'm the CTO and sole engineer at
**[NudgeLink](https://nudgelink.co)**, an AI SDR for LinkedIn outreach. I designed and built it end to end,
from the job queue and lead-scoring pipeline to Stripe billing, and I run it in production:
CI, deploys, monitoring, backups and incident fixes.
I'm finishing a B.Eng. in Cybersecurity (AEH Warsaw, 2027), so security is part of how I build
from the start. I like building systems and then trying to break them, and I write about what
breaks at **[kage7047.github.io](https://kage7047.github.io)**.

- **Backend:** Python · Go · FastAPI · Celery · PostgreSQL / pgvector · Redis · REST APIs & webhooks
- **Full-stack:** TypeScript · Next.js · Astro · React · Supabase
- **DevOps & security:** Docker · GitHub Actions · Railway · Vercel · Linux · Sentry · gitleaks · Postgres RLS
- **Testing:** deterministic simulation · `kill -9` chaos tests · linearizability checking (Porcupine) · pytest · Playwright
- **AI:** Claude API & Agent SDK · prompt caching · model routing · cost metering

### Selected work

- **[NudgeLink](https://nudgelink.co)** (private, in production): a multi-tenant SaaS. Durable
  multi-week agent workflows on Postgres + Celery (`FOR UPDATE SKIP LOCKED` claiming, leases for
  crash recovery, idempotent writes, a Redis kill switch), Stripe subscriptions with idempotent
  webhooks, envelope-encrypted third-party credentials, per-call LLM cost metering, and
  4,400+ unit and 460+ integration tests behind a gitleaks-guarded pipeline.
- **[faultline](https://github.com/Kage7047/faultline)**: Raft consensus and a replicated
  key-value store in Go. A deterministic simulator replays any hostile run (crashes, partitions,
  loss, reordering) from its seed, and a chaos test `kill -9`s and freezes real processes; both
  check every client history for linearizability. Seven deliberately broken builds prove the
  checks can fail. Write-ahead log with torn-tail repair, ReadIndex reads, snapshots.
- **[supply-chain-fortress](https://github.com/Kage7047/supply-chain-fortress)**: a software
  supply chain where every defence has an attack that proves it. Images signed keyless by one
  workflow, SBOM and SLSA provenance, Kyverno and built-in admission policies; 14 cluster attacks
  and 5 workflow attacks run in CI, each with a control that shows it gets in without that
  defence. The tests found that scaling Kyverno to zero makes it delete its own webhooks.
- **[pg-lease-queue](https://github.com/Kage7047/pg-lease-queue)**: a crash-safe job queue on
  plain Postgres: `SKIP LOCKED` claims, leases with fencing tokens and exactly-once effects, proven
  by a `kill -9` chaos test on Postgres 14 to 17. 2,700 jobs/s on a laptop after
  [finding why more workers made it 5× slower](https://kage7047.github.io/writing/more-workers-slower/).
- **[kioku-assistant](https://github.com/Kage7047/kioku-assistant)**: a self-hosted agentic
  personal assistant. FastAPI + Celery + Postgres/pgvector, the Claude Agent SDK over a git-backed
  markdown vault, and a default-deny approval gate on every outbound action, backed by a written
  threat model. Hybrid retrieval measured on a labelled set (recall@5 0.97), 220+ tests with a
  scripted model, a one-command demo, and a signed container image.
- **[Sidequest](https://github.com/Kage7047/Sidequest)**: a full-stack shared planner (Astro +
  Supabase). PostgreSQL row-level security is the authorization boundary, sign-up is invite-only
  through an auth hook, Web Push reminders run from an Edge Function on `pg_cron`, and GitHub
  Actions builds and deploys it.
- **[edgefeed](https://github.com/Kage7047/edgefeed)**: detects cross-venue arbitrage on
  prediction markets (Kalshi / Polymarket), net of real fees and order-book depth. A validation
  spike: test whether the edge exists before building the product.

### Writing

- [My admission policy said Fail. Kyverno let everything in.](https://kage7047.github.io/writing/kyverno-fails-open/)
- [Every feature I added to my Raft hid a bug from my tests](https://kage7047.github.io/writing/features-hide-bugs/)
- [Adding workers made my Postgres queue 5× slower](https://kage7047.github.io/writing/more-workers-slower/)

<sub>Frontend side work: [a concept homepage](https://github.com/Kage7047/acl-landscaping-mockup)
built with React, GSAP and Lenis.</sub>

### Contact

📫 ilya.nesterenok.work@gmail.com · [LinkedIn](https://www.linkedin.com/in/nesterenokilya)
