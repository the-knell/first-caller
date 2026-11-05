# First Caller: The Odoo Database Manager Ships Open

**knell**

Timestamp of record (archive.org): https://archive.org/details/knell-first-caller

Odoo ships with a master password of `admin` — documented, printed in its own source. The first request that reaches the database manager naming any other password *becomes* the master password. Nothing ships that tells the owner it happened. Proven end to end on the official container image: enumerate the databases unauthenticated, set the master password as a stranger, take the backup — a zip holding the full database dump and the entire filestore — restore it elsewhere as a complete clone, drop the original. Capability is the same one scripted attackers are already sweeping for.

## Verify

```
gpg --import knell-public.asc
gpg --verify paper-odoo-FINAL-2026-11-04.md.asc
```

Expect: `Good signature from "knell"`, key 133883AB9F6EDE5B9BA6B82E27BEDAF0CE152F25
Fingerprint: 1338 83AB 9F6E DE5B 9BA6 B82E 27BE DAF0 CE15 2F25
