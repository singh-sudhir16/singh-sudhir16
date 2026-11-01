# Sudhir Singh

**Software Engineer at Juspay** · UPI payments · Bengaluru, India & Lima, Peru

I build backend systems for payments. At Juspay I'm on the UPI team, currently on-site in Lima helping launch UPI payments in a new market. Outside work, I build infrastructure from scratch to see how it behaves under load and when things fail: a job queue, an object store, a real-time chat server.

[LinkedIn](https://www.linkedin.com/in/sudhir-singh-241983286/) · [LeetCode](https://leetcode.com/u/sudhirsingh16/) · [CodeChef](https://www.codechef.com/users/sudhirsingh92)

## At Juspay

- Secure REST APIs in **Haskell** on Juspay's in-house framework, with multiple authentication schemes and encrypted request and response payloads
- **Kubernetes** services for new stack setups: load balancers, application, Redis and database tiers
- Read-through and write-through **Redis** caching in a PSP stack to take load off the database
- Integrations with multiple **SMS providers**, with automatic retry and failover between them

## Featured projects

### [RedisFlow](https://github.com/singh-sudhir16/redisflows) · distributed job queue

**Java 21 · Spring Boot 4 · Redis Streams · Lua · Docker**

A Sidekiq/BullMQ-style job queue where every job state change is one atomic Lua script, so the system stays consistent when a process crashes at any point.

- At-least-once delivery with consumer groups and visibility-timeout reclaim: a simulated worker crash with 1,000 unacknowledged jobs loses 0 of 5,000
- Retries with exponential backoff and jitter, dead-letter queues, idempotent enqueue, leased priority lanes, leader-elected scheduling, and distributed locks with fencing tokens
- ~50K jobs/s enqueue and ~28K jobs/s processed by 2 workers, with p99 end-to-end latency under 3 ms at 10K jobs/s (measured on a laptop); 44 tests against real Redis via Testcontainers

### [ObjectVault](https://github.com/singh-sudhir16/objectvault) · S3-style object storage (in progress)

**Java 21 · Spring Boot 3 · PostgreSQL · Testcontainers**

- Metadata in PostgreSQL and bytes on disk under content-addressed paths, so user-supplied keys never touch the filesystem
- SHA-256 ETags computed in a single streaming pass (constant memory for any file size); uploads are written to a temp file and moved atomically, so readers never see partial content
- Built in phases, with each design decision recorded as an ADR (architecture decision record)

### [Rust WebSocket Chat](https://github.com/singh-sudhir16/rust-websocket-chat) · real-time chat

**Rust · axum · tokio**

- Multi-room chat with direct messages and typing indicators: rooms fan out over tokio broadcast channels, and DMs go through per-client channels
- Clients reconnect with exponential backoff, and the server replays missed messages from a per-room history buffer using monotonic message IDs

### [Payments Wallet](https://github.com/singh-sudhir16/payments-wallet-app) · full-stack wallet

**Node.js · Express · MongoDB · React**

- Sign-up and sign-in with JWT and bcrypt, wallet top-ups, transfers between users, and transaction history, with request validation in Zod

Earlier work: [SolarGIS](https://github.com/singh-sudhir16/SolarGIS) (estimating rooftop solar potential with deep learning) · [English→Kashmiri translation](https://github.com/singh-sudhir16/IndicMT-Kashmiri) (IndicTrans2) · [SLR parse-table generator](https://github.com/singh-sudhir16/SLR-parse-table-generator)

## Tech

- **Languages:** Java, Haskell, C++, JavaScript, Python, Bash
- **Backend:** Spring Boot, Node.js, Express, REST APIs, webhooks, event-driven systems
- **Data:** PostgreSQL, Redis, MongoDB
- **Infrastructure:** AWS (Lambda, ALB/NLB), Kubernetes, Docker, GitHub Actions, Linux
- **Frontend:** React
- **Learning:** Rust

## Problem solving

[LeetCode](https://leetcode.com/u/sudhirsingh16/) rating 1660+ with 980+ problems solved · [CodeChef](https://www.codechef.com/users/sudhirsingh92) 3★
