# rapp-doorman

Make a **fresh Claude session the sealed "doorman" to a machine** — so authorized peers (another
browser, another machine, another Claude) can reach and operate that machine's local brainstem,
end‑to‑end encrypted, with the browser tab as the access control.

## Use it (the whole thing)

On the machine you want to open, start a fresh Claude (Code) session and say:

> Read https://raw.githubusercontent.com/kody-w/rapp-doorman/main/doorman.skill.md and set me up as the doorman to this machine.

That Claude will: **run the self‑test** (proves a sealed peer can reach the local brainstem before
claiming anything), check prerequisites, **open a sealed door** (peer‑id + token), and **guard it**
(CDP stays local, token = the AES‑256‑GCM key, operating requires the seal, closing the tab ends
access). One command to prove it:

```bash
curl -fsSL https://raw.githubusercontent.com/kody-w/rapp-doorman/main/doorman_selftest.sh | bash
# → PASS ✅  (a separate sealed peer reached the local brainstem)
```

## Files
| File | Role |
|------|------|
| `doorman.skill.md` | the machine‑readable skill a fresh Claude reads to become the doorman |
| `doorman_selftest.sh` | OS‑portable proof that this machine can be a sealed doorman |

## Where it fits
Implements the **Doorman** role of the
[rapp-neighborhood-protocol](https://github.com/kody-w/rapp-neighborhood-protocol) (§11), over the
[rapp-sealed](https://github.com/kody-w/rapp-sealed) channel, using the
[vBrainstem](https://github.com/kody-w/vbrainstem) runtime and the
[rapp-kite](https://github.com/kody-w/rapp-kite) string tools.

MIT © Kody Wildfeuer.
