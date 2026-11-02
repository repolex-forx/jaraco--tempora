# Repolex Knowledge Graph of jaraco/tempora

RDF knowledge graph data for [jaraco/tempora](https://github.com/jaraco/tempora), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download jaraco/tempora
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── af7ee2dccd4bc96da32bb801c6c1317f9dcfa602
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── af7ee2dccd4bc96da32bb801c6c1317f9dcfa602
│           └── chunk-001.nq.gz
├── blob
│   ├── 535bfe17db446987f16b137b6f07db012c9a3195.nq.gz
│   ├── 7231313d012aa8167d2804e66907038e2556f754.nq.gz
│   ├── 9567ead73521e9f5007b5dd186132c877f7259da.nq.gz
│   ├── ae4195ce0ae747ef5707488154726e0d40deff4f.nq.gz
│   ├── b08bb315caf894719e11b232e3239a2658124ffe.nq.gz
│   ├── b4055e48f8b5e92ade4874e9baf072d1de33dc85.nq.gz
│   ├── cff2993051fb3b899b6908dbae26e22a75a00e43.nq.gz
│   ├── d483d33fee8c00bfcff522cab31554eb7e46ccc3.nq.gz
│   ├── d6419037a1854765e7341c5b2ba11e815e0582b3.nq.gz
│   ├── dcee809c8b9f079af0912a1f4f51872a86f8f5d5.nq.gz
│   ├── edb23fb878492a0d0f8635838af9bec917ac6e2e.nq.gz
│   ├── ef37ccf0fdf52b3bb184ca7328aa0b15f7366dff.nq.gz
│   └── f6b936f131090523a2cf4f8b43843355e4f4f786.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── af7ee2dccd4bc96da32bb801c6c1317f9dcfa602.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[jaraco/tempora](https://github.com/jaraco/tempora)

---
*Parsed on 2026-11-02 by [repolex](https://repolex.ai)*
