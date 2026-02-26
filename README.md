# TinyURL — Production-Grade URL Shortener

TinyURL is a single-region, production-oriented URL shortener system designed with scalability, reliability, and architectural evolution in mind.

This repository implements the service layer, while architectural evolution (v1 → v2 → future) is documented under `docs/architecture/`.

---

## Goals

This project demonstrates:

- Requirements-first system design
- Clean architectural evolution (v1 → v2)
- Production-ready service structure
- Scalable redirect-heavy workload handling
- Industrial Git hygiene and ADR usage

It is intentionally built as a realistic service, not a toy implementation.

---

## Version Overview

### v1 — Baseline Single-Region System

- Base62 encoded short codes
- DB-backed ID generation
- Stateless application servers
- HTTP 301/302 support
- Optional expiration (default 180 days)
- No caching
- No analytics
- No authentication

Focus: correctness + simplicity.

### v2 — Scale & Abuse Resistance (Planned)

- Redis cache (cache-aside)
- Negative caching
- Rate limiting (token bucket)
- Soft delete support
- Custom aliases (feature-flagged)
- Observability improvements

Full evolution documentation:
