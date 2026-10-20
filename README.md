# Repolex Knowledge Graph of simonw/click-app

RDF knowledge graph data for [simonw/click-app](https://github.com/simonw/click-app), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/click-app
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5e571600f0498c534180ae1a5271bfcb48355551
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5e571600f0498c534180ae1a5271bfcb48355551
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 410de3d276e11953643ecdb23365e09dca0c4797.nq.gz
│   ├── 47f6a6f2b9c3cf8e4fc5533238884c326d8dfc1e.nq.gz
│   ├── 4c45cac65e57e2c00a1bbc453bc5e3e3c2ac6bec.nq.gz
│   ├── 53605b7a5ec51bc95dca4fb43fdb350bf9362435.nq.gz
│   ├── 6090908934c2a028d46f4f9277734f25a85e08af.nq.gz
│   ├── 98dcca0c2836ae53d67260be8a5431b855e461bb.nq.gz
│   ├── aa1083bd0613601b8920c6225677bd85e7b312f2.nq.gz
│   ├── b58bd4644f749b219bc585ee8586edac7b9f165d.nq.gz
│   ├── cc5aeba6be6b59e1c7ef2b7cb9ac5aa028e5afe6.nq.gz
│   ├── d87ae37f0168b571f19fc53381bf509569c63a2f.nq.gz
│   ├── dff15e177668d0af058193d4b32d0b480a74452e.nq.gz
│   ├── e2139a6bc893b3de0638ec8eefd683d13d95410d.nq.gz
│   ├── e22ac4141b5b8de3445f9265af36b56e13aa8b2f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fab44ea721f056055f94baa00f2251f658e1e185.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5e571600f0498c534180ae1a5271bfcb48355551.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[simonw/click-app](https://github.com/simonw/click-app)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
