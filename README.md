# Repolex Knowledge Graph of agronholm/pyproject-flake8

RDF knowledge graph data for [agronholm/pyproject-flake8](https://github.com/agronholm/pyproject-flake8), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/pyproject-flake8
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b340fbc92ca355b8235d8a6209e9eec4a6a5b2ba
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b340fbc92ca355b8235d8a6209e9eec4a6a5b2ba
│           └── chunk-001.nq.gz
├── blob
│   ├── 5be60137011aed98e66c59e1ab46712ea30ca050.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── 70786c5ac71c53155c6fe0ff02825850afb3b104.nq.gz
│   ├── 93ac7349888c4dd926766670ca84223876b5ef5a.nq.gz
│   ├── c7c70d0be2f94f22b62f5b9fea21536367fe62e8.nq.gz
│   └── f45024a31979660b2b419fac43656cbc922ca3d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b340fbc92ca355b8235d8a6209e9eec4a6a5b2ba.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 12 files
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

[agronholm/pyproject-flake8](https://github.com/agronholm/pyproject-flake8)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
