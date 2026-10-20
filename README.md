# Repolex Knowledge Graph of graphql-python/aiohttp-graphql

RDF knowledge graph data for [graphql-python/aiohttp-graphql](https://github.com/graphql-python/aiohttp-graphql), parsed by [repolex](https://repolex.ai).

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
rlex download graphql-python/aiohttp-graphql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5f7580310761dd7de33b44bc92f30b2695f2d523
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5f7580310761dd7de33b44bc92f30b2695f2d523
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a940f9ffd72f4c68dcbef9deac0bbdc2c5f2a6c.nq.gz
│   ├── 0e5c7e487bf04e119cc21108dd84499c18587e67.nq.gz
│   ├── 43f7e99496152e32cb1becad75e5b58daf619662.nq.gz
│   ├── 59e7ff1c98c3d12de39496e1f42af87fbd9f7833.nq.gz
│   ├── 5f4a9734bf45d772d0f9ac51c3fc447fb178e1b8.nq.gz
│   ├── 61e4d59c274d0d6f1dec24909fc7bf09b1ecba84.nq.gz
│   ├── 642f015bf654723c3863819074fc78c5dbe328a6.nq.gz
│   ├── 7223ca8371ba66d81d9cd34f21ddbada298bd922.nq.gz
│   ├── b1dbd18170c62d1ece0d4a77ed015b3109caadd3.nq.gz
│   ├── bd85dbb6068cecfe7dd0574d0dc3e9cd34716228.nq.gz
│   ├── c44bad69ce42b6a30d229603a96908154b0ef6a5.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea2c92160c1fd065fa59728e50b172199a525764.nq.gz
│   ├── eb0db43855082865ef38410b979c2f1400f8f025.nq.gz
│   └── ec879546a818848a6d3fbd9c80a0944fbc8c07e3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5f7580310761dd7de33b44bc92f30b2695f2d523.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[graphql-python/aiohttp-graphql](https://github.com/graphql-python/aiohttp-graphql)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
