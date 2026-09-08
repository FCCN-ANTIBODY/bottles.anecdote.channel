# Onboarding, and where the boundary with the library is

`status: draft` — 2026-09-08. **The boundary is not settled.** This document exists because the
onboarding surface has now been described as three different things, and the re-deriving is the cost.

## The migration, so nobody repeats it

The surface was described as **the bottles'**, then as **the library's**, and is now being split
between them. Each move was reasonable and none of them was written down, which is why it has been
worked out from scratch more than once.

## What is settled

**The library onboards people generally.** That is its job and this repository does not want it.

**A bottle found in the wild, carrying a control code, onboards you with the bottle.** You do not
have to already be on anything.

### Why the library cannot be the only door

**The library may become constituency-based** — bounded by geoJSON, later. A constituency-bounded
onboarder is the wrong and only door for exactly the person who most needs one: somebody who found
a bottle and is, by definition, outside every constituency. There is no constituency that contains
*a stranger holding an artifact*.

### Why the bottle is the right one

**The bottle is the free transit object.** It moves; nothing else in the picture does. That makes it
**a natural onboarding magnet — it is how people are going to find this at all.** The onboarding job
lands on it not because it is well suited to governing anything, but because it is the thing that
travels, and travelling is what puts it in a stranger's hands.

## The asymmetry that actually defines the boundary

**A bottle can put a control code in. It has no control after that.**

Authority is exercised **at minting time and never at runtime.** The bottle is the only thing able to
place the code, and once made, it is out of its hands.

That is the whole shape, and three things fall out of it that a design will otherwise get wrong:

**1. A control code cannot be revoked by what minted it.** It is a capability sealed into an artifact
that travels. Anything assuming a revocation path is assuming a channel that does not exist. Whatever
scoping, expiry or narrowing a code needs has to be **decided at mint and carried inside it.**

**2. The bottle cannot know who used it.** No callback, no phone-home — and not merely as a privacy
preference. `AGENTS.md` already forbids it: whatever opens a bottle is a clean room with **no
network**, because a bottle that arrived optically was authenticated socially and by nothing else.
**A control code has to be self-sufficient offline or it is not a control code**, it is a login.

**3. So the code is an assertion, not a permission check.** It says *the holder of this may be
admitted*, to whoever is later in a position to admit them. It cannot itself admit anybody. The party
that acts on it is not this repository and is not necessarily the library either.

## What is open

**Where the boundary actually sits.** The two doors are agreed; the seam is not. Specifically:

- **What a control code grants.** Admission to what — the node the bottle came from, any node, or a
  named one? A code that names its origin is a pointer home; a code that does not is a bearer token
  with no issuer, and those are very different objects.
- **Who honours it.** A civic node, a station node, and a pure communications node are all places a
  library gets stacked. Any of them could be the thing that acts on a code, and they have different
  postures about strangers.
- **Whether a stranger onboarded by bottle is onboarded to anything durable**, or is simply able to
  read the thing they are holding. The second is much smaller and might be the whole requirement.

**The relationship is co-mounting, not dependency.** The library consumes bottles **by being stacked
with them on a node repository** — civic, station, or a pure communications node. Neither repository
is downstream of the other; they meet on a node. Worth stating because "the library is a consumer"
reads like a dependency, and a dependency would put the boundary in the wrong place.

## Not seated, on purpose

This is a domain of concerns rather than one concern, and the operator is working it out directly
with `library.anecdote.channel` until its obligations are discovered. **A seat drafted now would be
guessing a constituency**, which is worse than an empty chair. See [`OPEN.md`](OPEN.md) §3.
