# Repolex Knowledge Graph of scikit-hep/scikit-hep

RDF knowledge graph data for [scikit-hep/scikit-hep](https://github.com/scikit-hep/scikit-hep), parsed by [repolex](https://repolex.ai).

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
rlex download scikit-hep/scikit-hep
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8d048d4df0f2a0ad4537c702f591ce2daf5c2825
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8d048d4df0f2a0ad4537c702f591ce2daf5c2825
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c8705477b20ae79d3a087ac2a31e2785d03bb2c.nq.gz
│   ├── 21492dd50888b57189bb85b7cad95692c69484af.nq.gz
│   ├── 2a2affb339fe1d8a2968636aaac06f86e3906658.nq.gz
│   ├── 2ed5fd37932e2c8f79df30f39bf2cb87ee7e9e83.nq.gz
│   ├── 31ae675d3f2ea3d50f5b320c579ed206e8400feb.nq.gz
│   ├── 35ed4ceb69bb92b5807aad2693863fb14287a266.nq.gz
│   ├── 36ae2c31df1f7a4daa90e0f8c6be357c1e2a85a3.nq.gz
│   ├── 36f3de22f1c87fd63ec23fa06942b19d5da38739.nq.gz
│   ├── 3c8699181fcee5b98f6e9a58b1bf4bb0f9b8beda.nq.gz
│   ├── 3f2034ad39e92cea4b5d1f9aa8ce80e7a166d248.nq.gz
│   ├── 484c90e92228bf4a247186c1d946679071cb7832.nq.gz
│   ├── 6b1ffdcba21a9e33010d73ec76f1e362446af6e3.nq.gz
│   ├── 783b82a68b3ff0f98755be7882e510d195e588f3.nq.gz
│   ├── 83de88ba40ea6bf6dce4570f5c3cde1a53bea1dd.nq.gz
│   ├── 848816a2bb534dd939e8f1a912030977750c6276.nq.gz
│   ├── 87428620c62f6b7ec074670a8b2218db75c1d6f8.nq.gz
│   ├── 898f5ae574f716f03f419060d9cd7411b764aecb.nq.gz
│   ├── a20f0db546d27ce34e6d1a600a172d8d39b219e0.nq.gz
│   ├── b0567b4fc06532946f91db171f3a9d015fe949ce.nq.gz
│   └── d6cfe41d4551fab542f0e986909c5031e4e4c111.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8d048d4df0f2a0ad4537c702f591ce2daf5c2825.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[scikit-hep/scikit-hep](https://github.com/scikit-hep/scikit-hep)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
