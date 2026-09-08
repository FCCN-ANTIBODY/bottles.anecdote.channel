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

**Deliberately not yet, and there is now a reason rather than an absence of one.**

It declares no `advocate.yml`, which is a legitimate state — the runner names such a repository and
skips it.

The operator is **working this repository directly, alongside `library.anecdote.channel`, until its
obligations are discovered.** The concerns below are the first sketch of what those are, and they do
not yet group into constituencies anyone could speak for. A seat drafted now would be guessing one,
which is worse than an empty chair.

The plausible eventual seat guards **`canonical` is relational, not public** — the property most
likely to be lost by a well-meaning feature that infers canonicity from a file. Same shape as
`library.anecdote.channel`'s `no-card`, which exists for exactly that reason. **Not proposing it.**

## 5. The vanity QR eats redundancy, and somebody has to own the trade

A rendering can carry **a vanity QR laid over part of it** — a real want, and a cosmetic one.

Overlaying destroys modules. Past what basic redundancy already absorbs, the compensation is
**lengthening the fountain**: more encoded symbols, so the decoder still converges from what survives.

So the trade is real and quantifiable, and it is the kind of thing that gets decided by accident if
nobody writes it down:

> **Every pixel of vanity is paid for in fountain length**, which is paid for in frames, which is
> paid for in how long a person has to hold a phone steady.

What needs deciding is **who owns the budget** — whether an overlay is a parameter with a computed
cost the encoder reports, or a fixed allowance a design may spend within.

Note it applies to the **camera-read renderings only.** A vanity overlay on the `stored` rendering
would be decoration nothing ever looks at — it is *a QR for ants*, read by a program that already
holds the file. Vanity is for the renderings a human is pointed at.

## 6. How bottles read, and how bottles write

Named by the operator as their own domain and not yet designed. Recorded so they are not mistaken
for solved.

**Reading** is closest to settled: the clean room in the README says what a viewer may not do, and
`library.anecdote.channel`'s `BOTTLES.md` §1.2 asks for a player that needs no build step. Neither
says what the reading *surface* is.

**Writing** is barely started. What exists: amendments accumulate as diffs in a pile, squashing
flattens to a canonical version, and an amendment that bases cleanly onto the cold copy works. What
does not exist is any account of how a person **does** that — particularly the phone case, where the
README already promises a bottle is "openable and editable on a phone."

The two are likely to have different answers about the same object, which is the thing to watch.

## 7. Onboarding — see [`ONBOARDING.md`](ONBOARDING.md)

A whole domain rather than a question. The two doors are agreed (the library generally; a bottle in
the wild with a control code) and **the seam is not.**

The load-bearing part, kept here because it constrains everything else: **a bottle exercises
authority at minting time and never at runtime.** It can place a control code; it cannot revoke one,
cannot know who used it, and cannot be online to check.

## 4. The legal question, named and not answered

Redistributing captured websites — the library's caching role — raises questions nobody in this
chain is qualified to answer. Recorded here so the silence is not mistaken for a finding.

It is not this repository's to resolve either. It is noted because **the mechanism this repository
builds is what makes the question arise**, and a format that makes redistribution trivial should
not pretend it did not.
