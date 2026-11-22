# Repolex Knowledge Graph of Manishearth/pathdiff

RDF knowledge graph data for [Manishearth/pathdiff](https://github.com/Manishearth/pathdiff), parsed by [repolex](https://repolex.ai).

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
rlex download Manishearth/pathdiff
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5180ff5b23d9d7eef0a14de13a3d814eb5d8d65c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5180ff5b23d9d7eef0a14de13a3d814eb5d8d65c.nq.gz
│   └── repolex
│       └── 5180ff5b23d9d7eef0a14de13a3d814eb5d8d65c
│           └── chunk-001.nq.gz
├── blob
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 34233b31dcf8d80a859af4bf5741ba7e77905ee3.nq.gz
│   ├── 46b7e0b6ddea8e3d1a1eae8d33c31aeaf41bc431.nq.gz
│   ├── 6aa106405a4b4a00d779beab77c90c9473a6d203.nq.gz
│   ├── 988d9aa26d719ddd40bb2a82270069d906a82354.nq.gz
│   └── a44161eae7521423332466f61f94c5ea45ff1522.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5180ff5b23d9d7eef0a14de13a3d814eb5d8d65c.nq.gz
├── filetree
│   └── 5180ff5b23d9d7eef0a14de13a3d814eb5d8d65c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 16 files
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

[Manishearth/pathdiff](https://github.com/Manishearth/pathdiff)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
