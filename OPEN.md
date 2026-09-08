# Open questions

`status: draft` — written 2026-09-08 while provisioning this repository. None of these is decided.

## 1. Who owns the player?

**The largest, and it blocks a consumer that cannot proceed without it.**

Both petitions that led to this repository flagged the player as their own weakest boundary, and
neither resolved it.

- **The wire format is clearly ours.** It wants to be a spec somebody can implement twice, which is
  the whole reason it could not stay a section of `library.anecdote.channel`.
- **The clean-room viewer may not be.** A `data:` origin with no network, no cookies and no ambient
  credentials, capable of hosting a bottle's own UI, looks equally like `anecdote.channel`'s work as
  the static-system owner.

`library.anecdote.channel` has no stake in which, and one real stake in it being **answered**: the
player is the piece it depends on and cannot build. Recorded in its `BOTTLES.md` §1.2 as a
requirement with no owner.

**Do not resolve this here alone.** It is a boundary between two repositories, so it wants a
decision record, not a unilateral claim from the side that would benefit.

## 2. Are there three renderings, or two with a parameter?

The projector petition flagged its own likeliest error: *"Three renderings may be two with a
parameter, or four once somebody tries printing one."*

`stored` and `projected` differ in every parameter that matters (quiet zone, module size, frame
timing) and it is not obvious they are separate *kinds* rather than one encoder with a profile.
`enchanted` is more plausibly its own thing, because spatial redundancy changes the payload layout
rather than a setting.

Deciding early costs nothing and deciding wrong is cheap to reverse; **naming them wrong in a spec
somebody implements twice is not.**

## 3. Does this repository declare seats?

It declares none today, which is a legitimate state — the runner names a repository with no
`advocate.yml` and skips it.

The plausible seat is the one guarding **`canonical` is relational, not public**, since that is the
property most likely to be lost by a well-meaning feature that infers canonicity from a file. It is
the same shape as `library.anecdote.channel`'s `no-card` seat, which exists for exactly that reason.

**Not proposing one.** Seating is the operator's act, and a seat whose constituency was guessed is
worse than an empty chair.

## 4. The legal question, named and not answered

Redistributing captured websites — the library's caching role — raises questions nobody in this
chain is qualified to answer. Recorded here so the silence is not mistaken for a finding.

It is not this repository's to resolve either. It is noted because **the mechanism this repository
builds is what makes the question arise**, and a format that makes redistribution trivial should
not pretend it did not.
