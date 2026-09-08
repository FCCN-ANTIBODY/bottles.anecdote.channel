# Working in this repository

**It is a stub.** Read `README.md`, then `OPEN.md`. The consumer that specified it first is
`library.anecdote.channel`'s [`BOTTLES.md`](https://github.com/FCCN-ANTIBODY/library.anecdote.channel/blob/main/BOTTLES.md);
read that before designing anything, because it is a list of needs written by somebody who had to
guess, and every guess is a place this repository under-specified.

## The rules most likely to be broken here

1. **`canonical` is relational, not public.** It cannot be computed from a file. Nothing here may
   infer it, and no consumer may assert it on someone else's behalf.
2. **A bottle is not intrinsically encrypted.** Sealing is a *pile* property. Do not build a bottle
   that is secret by default; that is a different object and it belongs to the pile.
3. **The stored rendering is not a QR.** Anything that adds a quiet zone or upscales a module is
   optimising for a camera that is not there.
4. **Do not decide who owns the player** (`OPEN.md` §1) from this side alone. It is a boundary with
   `anecdote.channel` and this repository is an interested party.
5. **Not all bottle making is library behaviour.** That is why this repository exists. Do not
   reintroduce a library dependency into the format — the library is **co-mounted on a node**, not
   downstream of this.
6. **A bottle's authority is at minting time only.** It can place a control code; it cannot revoke
   one, learn who used it, or check anything online — the README's clean room forbids the network that
   would take. Any design with a revocation path, a callback, or a phone-home has assumed a channel
   that does not exist. See `ONBOARDING.md`.

## Conventions

Branch from an up-to-date `origin/main`, never commit to `main`, open a PR. Keep a `.pr` file at the
repo root holding what the PR would say — and **empty it in the same act that opens the PR**,
because it is a slot and not an archive.
