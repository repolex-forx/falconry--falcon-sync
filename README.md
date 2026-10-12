# Repolex Knowledge Graph of falconry/falcon-sync

RDF knowledge graph data for [falconry/falcon-sync](https://github.com/falconry/falcon-sync), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/falcon-sync
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c3a3eefdd8918401f3cc45e944b5efb48fdb00ef
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c3a3eefdd8918401f3cc45e944b5efb48fdb00ef
│           └── chunk-001.nq.gz
├── blob
│   ├── 0897949718c2ba20b6b0ec792d1697beeaf935f8.nq.gz
│   ├── 166b65e08d47e29331d407f4e82d7b855894483e.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2a811e40f6b2ace647c104f9c2cdb02806f440ee.nq.gz
│   ├── 2d3caac55385ba782de5ce59b469512ec46caac6.nq.gz
│   ├── 3c0e2f4ef087b344e41c3e42796fc197478e54f7.nq.gz
│   ├── 43994abdcb383098e66902d1dc65785b3adad3fb.nq.gz
│   ├── 5a81d024813c668116448f9b2ba70e5a6071946a.nq.gz
│   ├── 5ed56a5eb0910a7b5d1e6f025eea2e1a0d0b00dd.nq.gz
│   ├── 7318dc9352f6650251c7890238e3f8b8ef7486ea.nq.gz
│   ├── 7ac5ee68ce608afebf904fbdf1c4c208fae22559.nq.gz
│   ├── 82f927558a3dff0ea8c20858856e70779fd02c93.nq.gz
│   ├── a3ba279e1308938c1153405a0642299cee050688.nq.gz
│   ├── a7af6d9aa87384ec86ccf427c3ee739400532205.nq.gz
│   ├── b914cdc224d7fd0d96b278a79511d3779c4f1d1a.nq.gz
│   ├── ceed4a9e53e38b3ad07cdba29a50030fb07ad858.nq.gz
│   ├── dac91d02f954eb805cd09c101694e144c64fd389.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fc2680ccde89f917d3ca47556d53191b8eea6467.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c3a3eefdd8918401f3cc45e944b5efb48fdb00ef.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 25 files
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

[falconry/falcon-sync](https://github.com/falconry/falcon-sync)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
