# Limit Burst Crystals, End to End

*How a hit turns into a crystal, who gets it, and what it's worth — traced from the 9.0.0 client.*

If you've played Final Fantasy Brave Exvius, you know the rhythm: you hit something, a little crystal pops
out, and it drifts over to one of your characters, nudging their Limit Burst bar a bit closer to full. It
looks like a simple sprinkle of generosity. It isn't. Underneath, it's a small economy: your characters set
the *price of a ticket*, the enemy owns a *finite wallet*, and the crystal itself is a token that has to be
caught by someone.

This is what we found when we went looking — in plain English, with the actual numbers where we have them.

## The short version

- **The rate is yours, not the enemy's.** Every crystal drop is rolled at the *attacker's* rate: a base of
  **35%**, plus whatever the action and the attacker's passives add, capped at 100%.
- **The enemy has a budget.** Each enemy can only ever drop `min(lb_drop_limit, 20)` LB crystals per battle —
  the limit coming from the monster's data, with a separate value while it's broken.
- **One hit can roll several times**, because the skill itself says how many "drop checks" it makes.
- **Overkill pays.** If the blow kills with overkill, the rate is multiplied by 1.5.
- **The recipient is random** — uniformly among your living party members, with no preference for who needs
  the gauge more.
- **A crystal is worth 100 gauge points plus your percentage bonuses**, and it's clamped by that character's
  bar size, which grows with their Limit Burst level.

## Meet the cast

There are four moving parts, and confusing any two of them is where most explanations go wrong.

| Piece | Who owns it | What it decides |
|---|---|---|
| **The rate** $p$ | the attacker | the chance a drop check succeeds |
| **The drop checks** $n$ | the skill | how many times one damage instance rolls |
| **The budget** $B$ | the enemy (per monster part) | how many crystals it can lose, ever |
| **The gauge** $g$ | the receiving character | how close their Limit Burst is to ready |

Everything else — the animation, the little arch of light, the sound cue — is decoration.

## The roll

For a single drop check, the rate is

$$p = \min\!\left(100,\ 35 + r + \sum_{i \in L_{90}} v_i\right)$$

where $r$ is the action's own revision (`getReviseLbCrystal`, set by the skill's arm) and the sum runs over
the attacker's passives in list 90 — the "crystal drop rate up" family. So a character with a +50% passive
sits at 85%; there is no way past 100.

Then the game rolls a uniform number in $[1, 100)$ and asks whether it landed at or below $p$. Because the
range has 99 possible values between 1 and 100, the actual probability is a hair under the nominal rate:

$$P(\text{drop}) = \frac{p - 1}{99}\quad \text{for } 1 \le p \le 100.$$

An 85% rate is really an 84.8% chance. A 35% rate is 34.3%. Close enough that players will never notice, but
it's the kind of detail that matters when you're rebuilding the game.

**Overkill changes the maths.** If the attacker's overkill flag is set, the rate is multiplied by 1.5 — *after*
the 100 cap. So a 70% rate becomes 105%, and since the roll can never exceed 100, an overkill on a rate of
67% or more is a guaranteed crystal.

**How many rolls?** This is the part players usually describe as "more hits, more crystals," and they're half
right. The loop is per *damage instance*, and its length comes from the skill's own `drop_check_count` field.
A multi-check skill rolls the rate several times; some damage types are forced to a single check; a few
(non-damaging types) skip the crystal logic entirely. Hits and checks usually move together, but they are not
the same number.

## Your luck, their wallet

Here's the counterintuitive part: **the enemy you're hitting doesn't have a drop rate at all.** It has a
budget.

Each enemy — specifically, each monster *part*, since multi-part bosses keep separate books — starts the
battle with a number of LB crystals it is allowed to shed, read from its data (`lb_drop_limit`). While broken,
it uses a *different* limit, as if breaking opens a second wallet. And regardless of what the data says, there
is a hard cap of **20** drops per enemy per battle.

So the number of crystals one enemy will ever produce is

$$N = \min(\mathrm{lb\\_drop\\_limit},\ 20).$$

Two enemies with identical stats can behave completely differently here, purely because their data says so.
And your +crystal-drop passives can't make a stingy enemy generous — they only help you *empty its wallet
faster*, not enlarge it.

There's one more gate: a drop is zeroed if the target fails its own "may drop" check. For a normal enemy that
means "still has budget and hasn't hit 20." For your own units it means "don't drop against your own side."
The arena's stand-in rival always says yes.

## Who catches it

Once a crystal exists, it has to go somewhere. The game picks a recipient **uniformly at random among your
living party members** — everyone at 1 HP or more is equally likely, and nobody is weighted by how empty their
gauge is or how much they'd like the crystal. The choice is made as the crystal is launched, and the little flight
animation is just carrying it to the winner.

If you've ever watched a crystal sail past the character who was one tick from a Limit Burst and land on the
one who was already full, that wasn't bad luck with a hidden weight. It was a fair coin among survivors.

## What the crystal is worth

A crystal is not "one unit of gauge." It's worth

$$\Delta g = 100 + b_{47} + a_{31}$$

gauge points — a flat 100, plus the percentage bonuses from the LB-gauge-up buff (id 47) and the matching
passive. A +50% gauge-up effect therefore turns one crystal into 150 points.

The catch is the bar itself. Each character's Limit Burst bar has a size determined by their Limit Burst
*level* — the cost of the next burst, straight out of the data. A crystal always adds the same 100-plus-bonus,
but against a bigger bar it's a smaller fraction of the way there. And using a Limit Burst empties the bar
completely: there's no partial carry-over.

So the per-character differences come down to three things: **how big the bar is** (LB level), **how high the
LB level can go** (a per-unit maximum), and **how much the buffs and passives sweeten each crystal**. The
crystal itself is identical for everyone.

## A worked example

Your attacker has a passive worth **+50%** crystal drop, and the skill makes **two** drop checks. No overkill.

- Rate: $p = 35 + 50 = 85$.
- Per check: $P = (85-1)/99 \approx 84.8\%$.
- Expected crystals from that damage instance: $2 \times 0.848 \approx 1.7$ — subject, of course, to the
  enemy's wallet.
- Each crystal that lands gives 100 gauge points (plus any gauge-up bonuses on the receiver).
- If the blow had been an overkill: $p' = 85 \times 1.5 = 127.5$, so both checks are guaranteed.

Now put that next to a character with a 200-point bar at their current LB level: one crystal is half the bar.
At 400 points, it's a quarter. Same crystal, different felt value — which is exactly why "crystal drop rate"
and "LB gauge fill rate" get talked about as if they were the same thing when they're not.

## Why this matters

Three reasons, in ascending order of nerdiness.

1. **It explains the felt experience.** The wallet explains why some fights shower you and others don't, and
   why breaking a boss sometimes changes the flow of crystals.
2. **It separates two stats players conflate.** Drop rate (yours) and gauge fill (the receiver's) are different
   multipliers on different sides of the same event.
3. **It's a clean little system to rebuild.** For anyone reconstructing the game, the whole pipeline is four
   numbers and three comparisons — and every one of them is now written down, rather than guessed.

## What we're still not sure about

Honesty is part of the method here, so: a few pieces are still open.

- The *numeric* budgets and bar sizes live in data tables, and one of the two monster tables isn't in the set
  we've decoded yet — so we know the formula but not every enemy's wallet size.
- We haven't found anything that resets the "already dropped" counter mid-battle, so it looks like a per-battle
  budget, but "looks like" isn't "proven."
- There's a per-turn passive gauge-recovery function that may or may not feed this same bar; we haven't traced
  whether it's wired.
- And the in-game display of "how full" a bar is uses an obfuscated encoding, which we've decoded but not
  audited against every UI path.

None of those change the shape of the system. They're the difference between knowing how the economy works and
knowing every price in it.

---

*For the technically curious: the full trace, with function addresses and the instruction that decides each
step, is in `battle_lb_crystals.md` in the reverse-engineering notes, and the claims are indexed as DMG-046 and
DMG-047 in the project's rule ledger. The short form: `DamageData::update` runs the drop loop, the skill's
`getDropCheckCnt` sets its length, the enemy's `MonsterPartsMst` row sets its budget, and the crystal's flight
ends in `addLimitBurstCrystal`.*
