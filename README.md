# bottles.anecdote.channel

**The engine that makes a thing carryable, and the vocabulary for what it is at each stage.**

> Provisioned 2026-09-08, reversing a dissolution. Bottles had stopped being a top-level
> configuration on the grounds that *the libraries are going to offer this*. They will — and that
> turned out not to be an argument for the vocabulary living in a library, because **not all bottle
> making is library behaviour.** A desktop capture worker, a proofing tool and an offline browser
> all mint bottles with no library involved.
>
> Everything here is `draft` in the [`STATUS.md`](https://github.com/FCCN-ANTIBODY/advocate.anecdote.channel/blob/main/STATUS.md) sense.

## The three states, and the one that was missing

The word *bottle* was doing three jobs at once. Naming them separately is most of what this
repository is for.

| state | what it is | who can read it |
|---|---|---|
| **bag** | a live subtree, still accumulating; not baked, nothing sealed | whoever holds the directory |
| **bottled** | that subtree packed for **transit** — loadable into browser storage, openable and editable on a phone | anyone who receives it |
| **canonical** | a bottle *given* to someone as a reference point | as before, plus a base to fast-forward from |

**The bag is the new word and it is the useful one.** It names the thing you hold out to catch
browsing in various domains before any decision has been made about keeping it:

> *"If I wanted to merely hold out a bag — if I'm just doing that to catch my browsing in various
> domains — choosing to let it go now means I never made a bottle, because the bottle was only
> really made when you made the QR representation."*

Three consequences, each of which is easy to get backwards:

- **A bottle is not intrinsically encrypted.** Anyone may receive one, unpack it, and do anything
  with it. Sealing is a **pile** property a bottle is given by being placed in one — not something
  a bottle has on its own.
- **A QR video is a destination, not a storage format.** It is reached only when something is made
  canonical, and most bottles never become one.
- **Canonical is relational, not public.** *"I have given this set to my client before"* is what
  makes it canonical, for that pair. **It cannot be computed from the file**, which means no tool
  may infer it and no library may assert it.

## Three renderings of one payload

Same bytes, shown three ways, because they answer to different constraints.

| rendering | read by | optimised for |
|---|---|---|
| **stored** | a program that already holds the file | smallest possible — *a QR for ants*, unreadable by any camera and minimal by every other measure |
| **projected** | a camera pointed at a screen | acquisition: big modules, quiet zones, a controlled and adjustable frame rate |
| **enchanted** | a camera, once, handheld, badly | redundancy in **space** rather than time |

### The stored rendering is not a QR, and treating it as one wastes every pixel

Quiet zones and nine-pixel modules exist for **optical acquisition**, which is not what happens to a
stored bottle — it is read by a program that already has the file. So: cut the quiet zone, one
module to one pixel, zero-frame-time GIF so playback is a decode rather than a duration.

Worth measuring rather than assuming: whether file compression buys anything on top at this scale.
Plausibly nothing.

### The enchanted projector

The name is a joke; the requirement is not. A person recording a projected bottle gets **one take**,
on a phone, at whatever angle and lighting the room has. Asking them to hold steady through nine
loops is asking them to fail, and knowing when it has looped is genuinely hard for a person watching
flickering squares.

So put the redundancy in space: **a grid of nine on one screen**, duplicates of the same frame in
different contrast schemes, so one recording of the whole screen captures nine chances at every
frame. Glare kills one scheme and not another; the decoder takes whichever tile survived.

**A single one-shot recording is as good as nine loops.** That is the property that makes an
unrehearsed capture by a non-expert work at all.

Two things follow:

- **On-screen guidance is part of the rendering** — it should say what the viewer needs, or failing
  that, *keep a video of this*.
- **A recording is a first-class artifact, not a degraded one.** Someone without the app can record
  now and decode later, or hand the recording to an agent with better heuristics than existed at
  capture time. The format is self-healing under damage, so a recording is a slower path to the same
  bytes rather than a lossy one.

## The carbonite property

A bottle carrying a git repository **plus its hooks** is a different object from an archive of one.
It states, unequivocally, *this is the base you must commit against to be valid.* Commit against it
and the amendment can be replayed — and the replay is the signal to recrunch the video.

**Normally git hooks are worth nothing**, because they live in client space and anyone can drop
them. Here they are inside a sealed artifact whose whole identity is the seal. The version and the
configuration **are** the artifact, not an eight-character sha in a log nobody would notice changing.

*The hooks are trustworthy because they are part of the thing being distributed, not part of the
machine running it.*

It also means a bottle is **a binary file format** rather than arbitrary bytes — always the same
shape by construction, so a malformed one is detectable. An agent inflating one is not parsing
something hostile; it is reading a format only this system produces.

## Writeable bottles

A writeable bottle is **a data pile holding a bottle**. The pile is the encryption layer; the
project inside is what is called writeable; the base for the QR sits inside its own mouth.

Amendments accumulate in the pile as diffs. **Squashing flattens back to a canonical version** so
holders need not carry old checkpoints — though a bottle may keep a whole fan of supported major
versions, because it is git data and history games inside it do not matter.

**One pile, one lifetime.** Truncating a pile that carries a bottle destroys the ability to rebuild
it, so a fresh full bottle must be minted as the new base first. For a bottle-carrying pile,
**truncation *is* the re-base.**

## The clean room a viewer has to be

A bottle that arrived optically arrived from a source nobody authenticated in software. The
authentication was **social** — two people in a room — which is the stronger guarantee and the reason
the path is worth having. The viewer must therefore behave as though the contents are hostile:
**no crypto suite, no cookies, no ambient credentials, no network.** A `data:` URI origin is opaque
by construction, with content headers governing what an embedded frame may do.

The consequence that matters: **a bottle can carry its own UI.** A directory of images is already
browsable; a bottle that also carries a viewer and an editing surface lets the work happen *inside*
it, offline, on a phone, with marks written back into the bottle rather than into browser storage a
`data:` origin does not usefully have.

Two properties asked for by name, with no proposal yet for providing them:

- **Ice** — a sealed statement of *this is exactly what came in*, distinct from anything edited after.
- **Amendable** — later sessions extend or correct an earlier bottle rather than minting an unrelated
  one, and an invalidated entry is recordable as invalidated rather than vanishing.

## Why this is worth the trouble

Offline first, because DNS is barely standing up when nobody is pushing on it. The concrete case: a
person does a batch of work on their own equipment during an outage, bottles it, and walks out with
it intact. **An outage should not cost somebody the ability to earn.**

And the metadata half, which is why this is antibody work rather than a file-transfer trick: **the
provenance survives the crossing.** Organisations become unaccountable by losing metadata and then
reciting whatever version of events suits them. A bottle that arrives with its metadata worn on the
outside is the counter-argument.

## Who is waiting on this

| consumer | wants | filed |
|---|---|---|
| `library.anecdote.channel` | small stored rendering, a player with no build step, stuffing, **cold sterile checkout** | [`BOTTLES.md`](https://github.com/FCCN-ANTIBODY/library.anecdote.channel/blob/main/BOTTLES.md) |
| `DiscoveryWritten/proofing` | a way for a capture to leave the machine it was made on | the projector petition |
| `station-node` | somewhere for 84 references and zero bytes to become bytes | its library |

**The library is not the owner and is deliberately a consumer.** Its document is a list of
requirements, written before this repository existed so that provisioning it had something to build
against. Where the two disagree, this repository is wrong until argued otherwise — a consumer that
had to guess is evidence the supplier under-specified.

## Open

See [`OPEN.md`](OPEN.md). The largest is **who owns the player.**
