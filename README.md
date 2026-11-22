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
│   │   ├── 95ae10efa52b5ec450b7e39e43e29401645a59ee
│   │   │   └── chunk-001.nq.gz
│   │   └── af7ee2dccd4bc96da32bb801c6c1317f9dcfa602
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 95ae10efa52b5ec450b7e39e43e29401645a59ee.nq.gz
│   └── repolex
│       ├── 95ae10efa52b5ec450b7e39e43e29401645a59ee
│       │   └── chunk-001.nq.gz
│       └── af7ee2dccd4bc96da32bb801c6c1317f9dcfa602
│           └── chunk-001.nq.gz
├── blob
│   ├── 113b6aaa6b7aa8041489a1600908f12c65d5b5a3.nq.gz
│   ├── 14243051409fccc0404edd15a2c993e572626dd8.nq.gz
│   ├── 228449ea3fc3ace47e1148d318e6d3b7ccf6f9ca.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 35a357398e961dec0546b87d58f9eb52e715bfbc.nq.gz
│   ├── 4422384704c8072165b8825bd076fa32712b079f.nq.gz
│   ├── 45666c48edd3e5a324be4312ae3dc845240560f9.nq.gz
│   ├── 53513eee9b3a2f4df50df1febd59a5206718995a.nq.gz
│   ├── 535bfe17db446987f16b137b6f07db012c9a3195.nq.gz
│   ├── 54f99acbfac68c2be8283174ea64f1730a795e49.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 633e3648e99a9faf806677e5a2aabe6036b29f7a.nq.gz
│   ├── 63c0825f6bd49615f4f386b95463111f7992f6bc.nq.gz
│   ├── 6fa480e44f38768722368d7a986607adacf41d99.nq.gz
│   ├── 7231313d012aa8167d2804e66907038e2556f754.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 8d5473eff850ebaeadb0633026cf8865afde4464.nq.gz
│   ├── 8e13ede1d35c9b9fa8350cb4b63b35127c861eaf.nq.gz
│   ├── 9567ead73521e9f5007b5dd186132c877f7259da.nq.gz
│   ├── a71138445b5d32c9ffc9ed98583792a1cbd716ab.nq.gz
│   ├── ae4195ce0ae747ef5707488154726e0d40deff4f.nq.gz
│   ├── b08bb315caf894719e11b232e3239a2658124ffe.nq.gz
│   ├── b4055e48f8b5e92ade4874e9baf072d1de33dc85.nq.gz
│   ├── bb6633f70b132a7681bf6325c83921f55fc481ea.nq.gz
│   ├── c3f6cf30658e44a6ee8cd7981882d1a07ed1c8ae.nq.gz
│   ├── cff2993051fb3b899b6908dbae26e22a75a00e43.nq.gz
│   ├── d16988b96efb7a76a4e728083feb3c2eccec899c.nq.gz
│   ├── d226e149623898a43f35ab57295bb82004dc7d8d.nq.gz
│   ├── d483d33fee8c00bfcff522cab31554eb7e46ccc3.nq.gz
│   ├── d6419037a1854765e7341c5b2ba11e815e0582b3.nq.gz
│   ├── dcee809c8b9f079af0912a1f4f51872a86f8f5d5.nq.gz
│   ├── edb23fb878492a0d0f8635838af9bec917ac6e2e.nq.gz
│   ├── ef37ccf0fdf52b3bb184ca7328aa0b15f7366dff.nq.gz
│   ├── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
│   └── f6b936f131090523a2cf4f8b43843355e4f4f786.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 95ae10efa52b5ec450b7e39e43e29401645a59ee.nq.gz
├── filetree
│   ├── 95ae10efa52b5ec450b7e39e43e29401645a59ee.nq.gz
│   └── af7ee2dccd4bc96da32bb801c6c1317f9dcfa602.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

17 directories, 49 files
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
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
