# The Senior System Design Whiteboard Deck

High-density reference cards covering back-of-the-envelope capacity math, distributed systems trade-offs, caching failure modes, and whiteboard walkthroughs for L5, L6, and Staff technical interviews.

## Complete Download Package
The full deck includes 32 double-sided cards (64 sides total) delivered in three distinct formats:
- Printable Desk Sheets: A4 PDF with cut guides for standard 4x6 inch cards.
- Digital Swipe Deck: Mobile and tablet-optimized PDF for quick review.
- Spaced Repetition Deck: Pre-formatted Anki CSV ready for instant import.
- Quick Start Guide & Index: Single-sheet PDF table of contents.

[Download the Complete 32-Card Package on Gumroad](https://kiranfeather.gumroad.com/l/system-design-deck)

---

## Free Sample: Card 01 - Latency Numbers Every Engineer Must Know

### Latency Hierarchy (Front)
- L1 cache reference: 0.5 ns
- L2 cache reference: 7 ns
- RAM access: 100 ns
- SSD (NVMe) random read: 10,000 - 50,000 ns (10 - 50 us)
- Round trip within same data center: 500,000 ns (0.5 ms)
- Disk seek (HDD): 10,000,000 ns (10 ms)
- Cross-Atlantic packet (US to Europe): 150,000,000 ns (150 ms)

### Worked Scenario (Back)
Interviewer: "Walk me through where the latency goes in a single API request."

1. App server logic: Sub-millisecond (CPU and memory bound).
2. Cache hit (Redis, same data center): ~0.5 - 1 ms round trip (dominated by network hop).
3. Cache miss to DB query: Add 1 - 10 ms for an indexed read, or 10+ ms if it hits disk.
4. Cross-region network hop: Add 100 - 150 ms one-way.

Key takeaway: A single unnecessary cross-region network hop costs more time than the rest of the entire request combined.

---

## Complete 32-Card Table of Contents

### Part 1: Numbers to Know Cold
- 01: Latency Numbers Every Engineer Must Know
- 02: Throughput & Capacity Math (RPS / Peak Multipliers)
- 03: Storage & Bandwidth Sizing Formulas
- 04: Vector Embedding Memory Sizing (RAM & HNSW Overhead)
- 05: Read:Write Ratios & Cache Hit Targets
- 06: Availability & the Nines (Allowed Downtime Calculations)

### Part 2: Distributed Systems Foundations
- 07: CAP Theorem & PACELC Trade-Off Extensions
- 08: Quorum Consensus & Split-Brain Math
- 09: Consistent Hashing & Ring Rebalancing
- 10: Vector Clocks & Causality Tracking
- 11: Raft Leader Election & Term Numbers
- 12: Two-Phase Commit (2PC) vs Saga Pattern
- 13: Idempotency Keys & API Deduplication
- 14: Backpressure, Priority Load Shedding & Circuit Breakers

### Part 3: Caching & Storage Performance
- 15: Cache Strategy Selection (Cache-Aside vs Write-Through vs Write-Back)
- 16: Cache Stampede Defense (Single-Flight, Jitter, XFetch)
- 17: CDN Architecture & Multi-Layer Caching
- 18: Rate Limiting Algorithms (Token Bucket vs Leaky Bucket vs Sliding Window)
- 19: Composite Index & Leftmost Prefix Rules
- 20: B+ Trees vs BSTs on Disk Physics
- 21: SQL Transaction Isolation Levels & Anomalies
- 22: Database Sharding Strategies & Hot-Spot Isolation
- 23: Message Queue Delivery Guarantees

### Part 4: Whiteboard Trade-Off Defenses
- 24: gRPC vs REST
- 25: WebSockets vs Long-Polling vs Server-Sent Events
- 26: Kafka vs RabbitMQ vs SQS
- 27: SQL vs NoSQL Architectural Decision Tree
- 28: Redis vs Memcached
- 29: Monolith vs Microservices

### Part 5: Full Whiteboard Walkthroughs
- 30: Design a URL Shortener (100M Writes, 1B Reads)
- 31: 50M Document RAG Pipeline (HNSW & Product Quantization Sizing)
- 32: 10M DAU Chat App (WebSocket Concurrency & DB Storage)

---

## Get the Complete Deck
Download the high-resolution printable cards, digital swipe deck, and Anki CSV:  
[Instant Access on Gumroad](https://kiranfeather.gumroad.com/l/system-design-deck)
