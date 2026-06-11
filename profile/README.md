# ZTIP · TIBET — identity-rooted trust primitives

> Prove you're a trustworthy actor without revealing who you are — and let anyone
> re-implement it from the spec, with no vendor in the loop.

This is the **whole tree**, not just one app. Two roots — **identity (JIS)** and
**provenance (TIBET)** — everything composes on them.

```
L6  apps                  ID-Drop · KIT · cmail · Humotica        (out of scope)
L5  conformance vectors   ztip-conformance · tibet-conformance-vectors
L4  enforcement           SNAFT · NullRouteMux · Cortex   → allow / deny / quarantine / null-route
L3  composition           ZTIP / VINK / offer · IDDrop
L2  control / transfer    RVP · TAT
L1  branch                AINS │ continuity-envelope · causal-time · SSM · .tza · UPIP
L0  root pair             JIS · TIBET   ── on trust-kernel (Rust runtime)
```

## Start here

- 🌳 **The full primitive atlas** → [INTEROP.md](https://github.com/Jtel-ZTIP-w3c/Jtel-ZTIP-w3c.github.io/blob/main/INTEROP.md) — every primitive, its IETF draft, and what depends on what.
- ▶️ **Run the proof (30 s)** → [ztip-conformance](https://github.com/Jtel-ZTIP-w3c/ztip-conformance): `git clone … && ./run.sh` → green means a stranger interoperates, no vendor needed.
- 📱 **Try the demo** → [jtel-ztip-w3c.github.io](https://jtel-ztip-w3c.github.io) · [⬇ Android APK](https://github.com/Jtel-ZTIP-w3c/Jtel-ZTIP-w3c.github.io/releases/latest) (Android 12+, sideload) — tap two phones, watch an anonymous attestation cross the air.
- 🔎 **Or just a terminal — no app** → resolve any `.aint` over the public name service:
  ```sh
  curl -s -H "User-Agent: ztip" https://api.ainternet.org/api/ains/resolve/root_idd | jq .record
  ```
  Claim your own, revoke it, resolve again — it doesn't vanish, it shows a signed `revoked`
  tombstone. No helpdesk, no admin, no delete.
- 📄 **The specs** → ten active IETF Internet-Drafts: [`draft-vandemeent-*`](https://datatracker.ietf.org/doc/search/?name=vandemeent&activedrafts=on) (jis-identity, tibet-provenance, ains-discovery, iddrop, upip-process-integrity, …). Work-in-progress — IETF presence is openness of the tech, not a stamp of approval.

## The idea

One resolver, many actors — **human · AI · IoT**, each proving it's trustworthy in its own
terms. **Runnable, not readable:** don't read a wall of text — run a JSON and watch it go
green; the same artifact proves interop *and* respects a reviewer's time. And it all revolves
around **identity**: every layer answers *who may do this, is it still true, and can anyone
prove it later — without a vendor in the loop.*

Identity is `jis:`, not `did:` — the function DID aimed at, working today, with VC-shape interop.

*computo et comprobo, ergo fui · attestor, ergo nunc sum*
