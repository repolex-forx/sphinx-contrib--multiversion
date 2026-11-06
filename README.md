# Repolex Knowledge Graph of sphinx-contrib/multiversion

RDF knowledge graph data for [sphinx-contrib/multiversion](https://github.com/sphinx-contrib/multiversion), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/multiversion
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cd4c0db66473f04d7e037188f5f13444574b4b0e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cd4c0db66473f04d7e037188f5f13444574b4b0e
│           └── chunk-001.nq.gz
├── blob
│   ├── 01667946c130038ad20ac7fb98ca67fd0e07d1f1.nq.gz
│   ├── 03ae9c7600ecd0d66b29145b65223155db135b7a.nq.gz
│   ├── 0a79d014e9196a05f44b101f9481d1e7e93ce379.nq.gz
│   ├── 0f2a27be274016d6ff0675674a8faaa06bfd7576.nq.gz
│   ├── 10191535cabb81ffdf72ae18b85621a6cd9c9f0d.nq.gz
│   ├── 10559f6334bd20b75a901e338d9f8dacb54ee3d5.nq.gz
│   ├── 172d6b3f5d798030f17fbdc7aa8cd41d72c5b0a9.nq.gz
│   ├── 26e4dff2da45227a6c7e8870f7350fc913efae1b.nq.gz
│   ├── 3bdb3650aeed73eb4a6723fc2e610c84be824169.nq.gz
│   ├── 421c859f24e2df6e2b907ed5820f06da7986b962.nq.gz
│   ├── 4fea4a930ff9874d21b4aa3854d1b195cf5ecb82.nq.gz
│   ├── 5a7fd68ec61c420b28e911a70856702ea8c31e23.nq.gz
│   ├── 5ad9204951d53b0aaf03573b9ae07717d4c3c820.nq.gz
│   ├── 5fb5bd2528da9dbe39bcde1f445320e2adeef665.nq.gz
│   ├── 6313b56c57848efce05faa7aa7e901ccfc2886ea.nq.gz
│   ├── 655bb7c2f32a07f028174d726824469dac5801b5.nq.gz
│   ├── 6b1e43e8e17f3b50a4de40cfa8979d7895d0f576.nq.gz
│   ├── 6c0383cf8023802ea25d8be457677bf808b58280.nq.gz
│   ├── 750801a8e565ad74caa648ff542492c090c275cc.nq.gz
│   ├── 76ca000cf903c46ce767565efdc7842c021990cd.nq.gz
│   ├── 7b5e408c553efb7802d70af36c0f7f2307faa9da.nq.gz
│   ├── 7df77a4d78d109fb94483bbd946bfad600dfe5f2.nq.gz
│   ├── 7e36a7b5c2c1ff48feef07f687003f56bc5d932f.nq.gz
│   ├── 7fc4c63206859f302f93b63c77d632254a40a3c6.nq.gz
│   ├── 8304481183565432d6a8b900c13fa2d63360ae61.nq.gz
│   ├── 85895c176f4ef3b172df68459bd7d0b4dbe93778.nq.gz
│   ├── 8e55276363a02728ae365ef14ca73999dcba4f95.nq.gz
│   ├── 9e4b0d28e1f23cf5e16f7b06c5faf91f97ab8a8e.nq.gz
│   ├── ab9943f2b058ba9be3391b61afd39dac51b98342.nq.gz
│   ├── b99d1a49a830723698673f59533f3f2d708f43b4.nq.gz
│   ├── bd25a9474e15f0ac102c4ed580009655a41abd59.nq.gz
│   ├── bd6bea97a6ea71a8a45dd6fd14929582eefc0f45.nq.gz
│   ├── c4f26486d190ab6d3e11c59642e23244fe873019.nq.gz
│   ├── c82bcfa5cd1dd05a7dfeac9c68dc14ee9b2aaea1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e70475c9c598f3cc57b78b8500fd0f91138534ea.nq.gz
│   └── e94631080bc8a893ff8d2f58f8777cc8b2237cc6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cd4c0db66473f04d7e037188f5f13444574b4b0e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[sphinx-contrib/multiversion](https://github.com/sphinx-contrib/multiversion)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
