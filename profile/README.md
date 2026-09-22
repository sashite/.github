# Sashité

**Three chess traditions — one board.** Chess, ōgi (shogi-inspired) and
xiongqi (xiangqi-inspired) play *each other* on a shared 8×8 board: nine
pairings, each side under its own rules, one formal system.

🎮 **Play now: [sanki.app](https://sanki.app)** — in the browser, no
account. Your identity is a keypair you hold; a game is a chain of signed
public events on Nostr, portable and independently verifiable. If nobody is
around, three bots will play you, one per game: Julee (chess),
王棋ちゃん (ōgi) and 竹影 (xiongqi).

## How it fits together

| Layer | Where |
| --- | --- |
| **Protocol** — the Nostr extensions (NIPs): challenges, sessions, moves, ratings, puzzles. Public domain. | [`nostr`](https://github.com/sashite/nostr) |
| **Rules** — the reference rule system, one deterministic interface for engines and clients | [`sashite-sanki-kernel-wasm.rs`](https://github.com/sashite/sashite-sanki-kernel-wasm.rs) |
| **Engine** — move legality for chess, ōgi and xiongqi on 8×8 | [`sanki-engine.rs`](https://github.com/sashite/sanki-engine.rs) · crates.io `sashite-sanki-engine` |
| **Session kernel** — the verdict a session's public events yield | [`sanki-session.rs`](https://github.com/sashite/sanki-session.rs) · crates.io `sashite-sanki-session` |
| **Player** — move search; the balance study per pairing is reproducible from its `examples/` | [`sanki-player.rs`](https://github.com/sashite/sanki-player.rs) |
| **Notations** — FEEN (positions), PIN/EPIN (pieces), SIN (styles), QI (position model) | [`feen.rs`](https://github.com/sashite/feen.rs) · [`pin.rs`](https://github.com/sashite/pin.rs) · [`epin.rs`](https://github.com/sashite/epin.rs) · [`sin.rs`](https://github.com/sashite/sin.rs) · [`qi.rs`](https://github.com/sashite/qi.rs) — with Ruby and Elixir ports |
| **Specs** | [sashite.dev](https://sashite.dev) |

Any conforming client can replay a game's events and reach the same
verdict, bit for bit. Ours is currently the only client; the protocol,
event format, rule modules and reference implementation above are public.

## Contributing

Rule edge cases are the most valuable contribution: if you find a position
where the kernel is wrong, open an issue on the repository concerned. The
rules of each game are published at
[chess.page](https://chess.page) · [ogi.page](https://ogi.page) ·
[xiongqi.page](https://xiongqi.page), in five languages.

📫 contact@sashite.com · 🦋 [@sashite.com](https://bsky.app/profile/sashite.com) · 𝕏 [@sashite](https://x.com/sashite)
