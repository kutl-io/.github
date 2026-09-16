# kutl

A sync protocol for teams of humans and AI agents.

Syncing files across machines is a distributed systems problem. Syncing
the coordination around them is the same problem, so kutl solves both
with the same machinery: document edits and signals (flags, replies,
decisions) are operations that merge deterministically whatever order
the network delivers them, every participant works from real files on
their own disk, and going offline is just a longer gap between
deliveries.

That makes the protocol indifferent to what is on the other end: an
editor, a script, one agent, or a fleet of them working alongside a
team of humans. Agents call MCP tools; humans use the CLI or
in-document syntax; the primitives underneath are identical.
Coordination that usually lives in a chat scrollback or a ticket
queue, like requesting review or recording a decision, travels as
signals next to the documents themselves.

Depending on how teams work, that can stand in for a centralized
wiki, doc tool, or tracker (Confluence, Notion, Google Docs, Jira):
documents are ordinary files they own, flags and decisions do the work
of tickets and comment threads, and the whole thing runs on
infrastructure you control. The relay is a lightweight WebSocket
server you self-host, authorizing machines with an SSH-style allowlist
file. On coding projects, kutl works alongside git.

## Get started

```sh
brew install kutl-io/tap/kutl
```

Create a space with `kutl init`, then follow the
[getting started guide](https://kutl.io/docs) to connect a second
machine.

## In this org

- [kutl](https://github.com/kutl-io/kutl) — the CLI, daemon, relay,
  and CRDT engine, in Rust. MIT OR Apache-2.0; the relay is AGPL-3.0.
- [homebrew-tap](https://github.com/kutl-io/homebrew-tap) — Homebrew
  formulae for the CLI.
- [kutl.io](https://github.com/kutl-io/kutl.io) — the website and
  docs.

Want a hosted relay with a web UI on top? That's
[kutlhub](https://kutlhub.com), built by
[Cogentient](https://cogentient.com).
