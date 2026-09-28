---
name: Rapid chess playbook
description: >-
  Use this when playing or coaching a 10-minute (or similar rapid) chess.com
  game: openings, thinking routine, and strict clock/tempo rules so you don't
  flag.
---
# Rapid chess playbook (10+0 focus)

## Sources (principles distilled from)
- Chess.com opening principles (IM Danny Rensch)
- JD Chess: how strong players manage the clock
- ChessMind AI / GM Mauricio Flores Rios on rapid thinking & clock budget
- ChessWorld rapid time / openings guides
- Post-mortems from training games (flagged vs a 1000-rated bot by move 14)

## Hard tempo rules (priority #1 — beat flagging)
These override deep thinking. Finishing with time left beats a “better” move that costs the flag.

**Per-move caps (10+0):**
- Book / developing opening moves (first ~10–12): **≤5 seconds** think + click. Pre-decide the Italian line.
- Quiet middlegame improving moves: **≤15 seconds**
- Critical moments only (check, capture fight, mate threat, queen trade, pawn break): **≤45 seconds**, then play the safest candidate
- Clock **under 1:00**: **≤8 seconds**, safety moves only
- Clock **under 0:40**: pick any **legal safe** move instantly; never retry illegal king walks; if click fails once, try a different legal piece immediately

**Phase cushions (must hit):**
| Checkpoint | Minimum clock |
|---|---|
| After castling / ~move 5–6 | ≥9:00 |
| After ~move 12 | ≥8:00 |
| Entering last third | ≥2:00 |
| Never | 0:00 while opponent has minutes |

If behind budget, **only** play fast developing/safe moves until back on track. No “one more long think.”

**UI execution:** click-drag firmly once; don’t hover-analyze on the board for 30s. Pre-visualize the move, then execute. On failed/illegal click, abort that idea in <2s.

## Opening repertoire (simple plans, not theory dumps)
**As White:** Italian — `1.e4 e5 2.Nf3 Nc6 3.Bc4`, then `d3`/`O-O`/`Nc3`/`Bg5` or `Be3` as fits. Castle early.
**Vs 1.e4 as Black:** solid `...e5` Italian/Ruy structures.
**Vs 1.d4 as Black:** Slav ideas (`...d5` + `...c6`).

Rules: develop minors to center; don’t move same piece twice early; no early queen; castle by 10; connect rooks.

## Thinking routine (only when tempo budget allows)
1. CCT scan — checks, captures, threats
2. 2–3 candidates
3. Short calc (2–3 ply + best reply)
4. Blunder-check landing square (can they take it for free?)

Under low time: skip to blunder-check + move.

## Middlegame / endgame
King safety, improve worst piece, open files. Don’t relax after winning material. In endings: activate king, push passers; with low time simplify, don’t invent.

## Fair play
No engine vs live humans.

## After each game
1. Did we flag? If yes, where did the cushion die (move number + clock)?
2. First hanging piece / missed CCT
3. Adjust next game’s opening tempo if still slow off the blocks
