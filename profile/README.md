# ZTIP — Zero-Trust Identification Protocol

**Prove you're a trustworthy actor — without revealing who you are.**

> Where IAM remembers, ZTIP forgets. No identity database — a short, signed attestation
> that a *fact* holds ("18 or older"), verified point-of-use, then gone.

Two Android phones tap. One **offers** an identity claim, the other **verifies** it. The
verifier shows `✅ 18 or older`, `signature verified ✓`, and a line listing exactly what did
**not** cross the wire — name, document number, date of birth, photo.

### Start here
- 🌐 **One-page landing:** https://jtel-ztip-w3c.github.io
- 📱 **Grab the APK:** [Releases »](https://github.com/Jtel-ZTIP-w3c/Jtel-ZTIP-w3c.github.io/releases/latest) (Android 12+, sideload)
- 📖 **Verify it line by line:** [the repo & cookbook »](https://github.com/Jtel-ZTIP-w3c/Jtel-ZTIP-w3c.github.io)
- 🔎 **Or just a terminal — no app:** resolve any `.aint` over the public name service:
  ```sh
  curl -s -H "User-Agent: ztip" https://api.ainternet.org/api/ains/resolve/root_idd | jq .record
  ```
  Claim your own, then revoke it and resolve again — it doesn't vanish, it shows a signed
  `revoked` tombstone. No helpdesk, no admin, no delete.

### The idea
One resolver, many actors — **human · AI · IoT**, each proving it's trustworthy in its own
terms. Identity is `jis:`, not `did:` — the function DID aimed at, working today, with VC-shape
interop. Internet-Drafts, work in progress. The app is the artifact: tap it.

*computo et comprobo, ergo fui · attestor, ergo nunc sum*
