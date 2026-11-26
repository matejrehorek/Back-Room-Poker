# Back Room Poker (Hold'em)

Free play-money No-Limit Texas Hold'em in the browser, against up to five bots, with live equity and an exact odds calculator. It is part of [601101.org](https://601101.org), where it is linked from the footer.

**Play money only.** There is no real-money gambling, no purchases and no prizes. Chips have no cash value. 18+.

## Features

### Table
- One human against 1 to 5 bots. You choose which bots sit at the table, plus the starting stack (500 to 5,000), blinds (5/10 to 50/100) and bot skill (easy, normal, hard).
- Full No-Limit rules: positions (BTN, SB, BB, UTG, HJ, CO), minimum raises, short all-ins that don't reopen the betting, uncalled bets returned, and split and side pots.
- While you play it shows your hand, your chance to win against the players still in, the effective stack, the stack-to-pot ratio (SPR), and the equity a call needs.
- Table options: dealing speed, show your win chance, show every player's cards and equity, deal the next hand automatically, and let a bot play your seat.
- Session stats, standings and a hand history.
- Player stats in the standings, shown after five hands: **VPIP** (how often a player puts money in before the flop), **PFR** (how often they raise before the flop) and **AGG** (share of bets and raises after the flop).
- A **Light / Dark** switch in the header. Until you choose, it follows your system theme.
- Keyboard shortcuts: **F** fold, **C** check or call, **R** bet or raise, **Space** deal the next hand.

### Bots
Each bot has its own style. Before the flop, it plays and raises a set share of the 169 starting hands, ranked by strength, and it tightens up when facing raises and loosens up at a short table. After the flop it decides by simulating its chances against the players still in.

| Bot  | Style            | Plays (VPIP) | Raises (PFR) |
|------|------------------|-------------:|-------------:|
| Rook | Tight-aggressive | 22%          | 18%          |
| Vex  | Loose-aggressive | 42%          | 32%          |
| Dot  | Calling station  | 64%          | 5%           |
| Pell | Rock             | 17%          | 11%          |
| Juno | Balanced         | 27%          | 18%          |

The percentages are each style's target at a full six-handed table.

### Odds Lab
- Set up to six hands and any board cards, and see each hand's chance to win or tie, plus how often it ends up as each type of hand by the river.
- Leave a card blank and it is dealt at random on every run.
- When all hole cards are known, it counts every possible board exactly. Otherwise it samples 200,000 deals, which lands within about 0.2% of the true figure.
- "Check these odds in the Odds Lab" on the table copies the current hand into the lab.

## How it's built

The whole game is a single self-contained file, `index.html`. HTML, CSS, JavaScript and the IBM Plex fonts are all inline, so there is no build step, no dependencies and nothing is loaded from other servers.

To play it locally, open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Privacy

The game uses no cookies, analytics, ads or tracking. Your table options and theme choice are saved only in your own browser's local storage, so they are still set on your next visit. Nothing you do in the game leaves your device.

## License

- **Code**: [MIT](LICENSE).
- **Fonts** embedded in `index.html` (IBM Plex Sans, IBM Plex Sans Condensed, IBM Plex Mono): Copyright 2017 IBM Corp., SIL Open Font License 1.1.
