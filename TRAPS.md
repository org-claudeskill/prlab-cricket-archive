# Traps for single-repo review

## `trap/reexport-leaks`

**The PR:** keep `raw_ball` and `match` on stored snapshots so on-call can replay the original delivery. Comment them as debug-only.

**What a hop-2 review usually says:** additive persistence, documented as internal, tests updated, LGTM.

**1 hop up (scoring):** no compile break. Archive becomes a second copy of the leak.

**2+ hops down:** any later reader of `/history` can walk `match.innings.latest_over.latest_delivery.wicket.umpire_confirmed`.

**Functional truth:** the archive is a firewall, not a protocol museum.
