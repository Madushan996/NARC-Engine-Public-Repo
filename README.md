<div align="center">

<img src="assets/logo.png" alt="NARC Engine logo" width="180">

# NARC Engine 

Please note that this is the old NARC engine repo and new releases with source code will be published in the new repo :- 
https://github.com/Madushan996/NARC




### ♞ *Not All Real Computations* ♞

**A grandmaster-strength UCI chess engine — written from scratch, with a neural
network trained entirely on its own self-play.**

![Version: 2.5](https://img.shields.io/badge/version-4.1-blue.svg)
![CCRL Rating : 3323](https://img.shields.io/badge/CCRL%20perf%20rating-3323-gold.svg)
![Protocol: UCI](https://img.shields.io/badge/protocol-UCI-success.svg)
![Platform: Windows](https://img.shields.io/badge/platform-Windows%20x64-0078D6.svg)




</div>

---

## About

NARC is an original UCI chess engine built entirely from scratch. It pairs a
classical alpha-beta search (magic bitboards, the full modern pruning suite, and
Lazy SMP multithreading) with an **NNUE neural-network evaluation that was
trained from zero on the engine's own games** — no human game data, no borrowed
code, and no borrowed network.


## Strength

The version 4.1 has a rating of 3323 according to the  CCRL 40/15 list. 

## Highlights

- **Self-trained NNUE evaluation** — a neural network bootstrapped from a
  hand-crafted eval, then improved by generational self-play, where each network
  learns from the previous one's search.
- **Magic-bitboard move generation** — perft-verified exact, ~25M nodes/sec.
- **Modern alpha-beta search** — PVS, iterative deepening, aspiration windows,
  null-move/late-move/futility/SEE pruning, late move reductions, singular
  extensions, ProbCut, and a full history stack.
- **Lazy SMP multithreading** — scales across CPU cores (set the `Threads`
  option to your core count).
- **Single self-contained executable** — the network is embedded; no extra files.

## Download & use

1. Download **`NARC-Engine.exe`** from this repository (or the Releases page).
2. In your UCI chess GUI (Arena, Cute Chess, BanksiaGUI, ChessBase, …):
   **Install New Engine → select `NARC-Engine.exe` → protocol UCI.**
3. For full strength, set the **`Threads`** option to your CPU core count.

### UCI options

| Option        | Default   | Meaning                                   |
|---------------|-----------|-------------------------------------------|
| Threads       | 1         | Search threads — set to your core count   |
| Hash          | 128       | Transposition table size (MB)             |
| Move Overhead | 30        | ms reserved per move for GUI/network lag  |
| Use NNUE      | true      | Neural-net evaluation (false = classical) |

## Documentation

| Document | Contents |
|----------|----------|
| [**TECHNICAL_REPORT.pdf**](TECHNICAL_REPORT.pdf) | Full technical report: architecture, training methodology, empirical results, and what distinguishes the engine |
| [**HOW_IT_WORKS.pdf**](HOW_IT_WORKS.pdf) | A conceptual tour of how the engine works, for any reader |

These describe the engineering and methodology in depth — without source code.

## Play it online

NARC also runs as a bot on Lichess (when online): **https://lichess.org/@/NARC_ENGINE**

## License

Freeware, **closed source** — free to download, use, and play against, and to
use for rating lists and tournaments. Reverse engineering, modification, and
redistribution of modified versions are not permitted. See [LICENSE](LICENSE).

## Credits

- Engine design, implementation, and neural network: **Developed by Madushan Dissanayake with AI assistance**.
- Piece-square table values: the public **PeSTO** tables by **Ronald Friederich**
  (RofChade).
