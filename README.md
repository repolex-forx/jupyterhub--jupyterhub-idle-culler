# Repolex Knowledge Graph of jupyterhub/jupyterhub-idle-culler

RDF knowledge graph data for [jupyterhub/jupyterhub-idle-culler](https://github.com/jupyterhub/jupyterhub-idle-culler), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/jupyterhub-idle-culler
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0b92132cf9a1ba5f5c425c790e44246b2dfbfe52
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0b92132cf9a1ba5f5c425c790e44246b2dfbfe52
│           └── chunk-001.nq.gz
├── blob
│   ├── 08e2c862d18b0e57e16015943ebe4f4d698168f3.nq.gz
│   ├── 144086c7c7d24a3095e9490b7506a8ce2485aa9b.nq.gz
│   ├── 1891b4176ff408b2281cf9e0f37a9da6be52fc36.nq.gz
│   ├── 30cb383b143e4b70853a5401923363f21318bce8.nq.gz
│   ├── 3d0dc29c52436d7c8c0af1a1ef472b463bcf9315.nq.gz
│   ├── 491ae499b59bc5d5699284d1a709c39b48ac43c2.nq.gz
│   ├── 53829260419d3dbc858be3ae12559858390ce23b.nq.gz
│   ├── 70ef20a0bbbdb509e46e59cced968740480011b4.nq.gz
│   ├── 82aeb4c40e4b3d6a80a79c7b17437d461c23c419.nq.gz
│   ├── 8ab49531685a0077b9f85f070981e9e7ed3dc5ac.nq.gz
│   ├── b155fc58e9670f8d4dd89ecb97169d51bb37e8f0.nq.gz
│   ├── b46f0ef776101a5bfaa6ce4abff0f59f839c15e5.nq.gz
│   ├── b70dc762d22cb88113eed38b9a9b3e3be1083ae5.nq.gz
│   ├── bed7cc29730a72ceec345ab621cec247da8e79d1.nq.gz
│   ├── c677c8efabf925318fce71678f0348b9f0533caa.nq.gz
│   ├── d5b5154410b4484b1cc5d31211b9f5cf16b7c89a.nq.gz
│   ├── d62c3724692e9678ea7b5fb3a453ab58a0093e8b.nq.gz
│   ├── d6e9681c21b6880b079b8db53dd819d0029520f6.nq.gz
│   └── ec401e79d02b2fc4953736b1fa4b3fa70301c6cf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0b92132cf9a1ba5f5c425c790e44246b2dfbfe52.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[jupyterhub/jupyterhub-idle-culler](https://github.com/jupyterhub/jupyterhub-idle-culler)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
