# Repolex Knowledge Graph of dtolnay/build-alert

RDF knowledge graph data for [dtolnay/build-alert](https://github.com/dtolnay/build-alert), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/build-alert
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a584969f1949c74cfe24ae829fc46b1f50d2adaa
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a584969f1949c74cfe24ae829fc46b1f50d2adaa.nq.gz
│   └── repolex
│       └── a584969f1949c74cfe24ae829fc46b1f50d2adaa
│           └── chunk-001.nq.gz
├── blob
│   ├── 07b395bdbf4f5b6ab0e59fcb05a317b6322c717d.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 3281a4d93ab0f0132314bd668884bdd89ab39b2b.nq.gz
│   ├── 5ac3440c5f7a9b6a695f0a4a39b0b0ad8ae89ef4.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 9ebc52387101e7326a3c922125e31d30ad2e57f3.nq.gz
│   ├── e6685110a28bd5150fe7fd547a474fa8472d794c.nq.gz
│   └── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── a584969f1949c74cfe24ae829fc46b1f50d2adaa.nq.gz
├── filetree
│   └── a584969f1949c74cfe24ae829fc46b1f50d2adaa.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[dtolnay/build-alert](https://github.com/dtolnay/build-alert)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
