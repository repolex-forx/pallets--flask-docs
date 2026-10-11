# Repolex Knowledge Graph of pallets/flask-docs

RDF knowledge graph data for [pallets/flask-docs](https://github.com/pallets/flask-docs), parsed by [repolex](https://repolex.ai).

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
rlex download pallets/flask-docs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ba4713af853166590cd9119e513dd5943380ed58
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ba4713af853166590cd9119e513dd5943380ed58
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d32f53899ef3af64bfa1dd4205516dd22ad1168.nq.gz
│   ├── 1ba40504c19cbdd5807398d237d1442618fff403.nq.gz
│   ├── 1f84c92d3bace733c580132c23d59bd6119b4647.nq.gz
│   ├── 22e87d5cb59a811e9f6d06409667248521d38f35.nq.gz
│   ├── 24a535990e9fc0b8fed6bdfbffc328bd38a9e33e.nq.gz
│   ├── 270cc08dcfc22bcb3253475fb318a37e670cb48a.nq.gz
│   ├── 29f168e9dbf529555929483dead2487a8388fb79.nq.gz
│   ├── 3f2772e11d3aa5c5ef5ec708f31eead703af4193.nq.gz
│   ├── 4acc168d6005a393f9f904f61f6a5cf8e1e5f139.nq.gz
│   ├── 6841512977936ee3a2f99df8c32795079d42de5c.nq.gz
│   ├── 68dd806fcdf13b0f41672d33a8ca3082c3597b5b.nq.gz
│   ├── 6d71221b70142e450271a8ba6eed67aa0a7eedba.nq.gz
│   ├── 6eed758f55dbe70d37f79c18450bb669b8e1d366.nq.gz
│   ├── 718079a06cc0f7c11ba34d8262e26aa2297c5e6f.nq.gz
│   ├── 7612ea9813536c0bc6ac5cc679e47db9fd6eda42.nq.gz
│   ├── 797cfd46bfbdaad7baff4a31ac6b981f4feec156.nq.gz
│   ├── 79e31e1052d39315f440cc13adc0c82cc138ff6a.nq.gz
│   ├── 8ba3297783ea3da23738a944697b834f317fcce5.nq.gz
│   ├── 8d44cc8ee4fe41dec644d7f27442d5e6411eb6e4.nq.gz
│   ├── 8dbe8fdf451ef6d4323516911d8839c26cbdeb88.nq.gz
│   ├── 9cda2d062dd164a81537de1ef5aefaf3328e3736.nq.gz
│   ├── 9fef851680ddde7543e7e333a31a86deab963bbb.nq.gz
│   ├── a20df142f61ddd4edfe607da2b6079a8505b1614.nq.gz
│   ├── a582d053b4f6712e438a3920f5012af3c094b878.nq.gz
│   ├── aa39b45b27be9622dd4e8e4df4fdb6ff081dc7d9.nq.gz
│   ├── b28f72eae26cd484c434a34f0278dd398ddfbe7c.nq.gz
│   ├── b62deddef8d2cab89502e2e30589faaf564a8441.nq.gz
│   ├── c33e2dda62f20291840a8f1abcf3634b36de00f3.nq.gz
│   ├── d1a80cd325699a004ee2aa73db069c63f61c9c62.nq.gz
│   ├── d8a15c5a3b4fb50c2939ad59b3e0b6a791891f50.nq.gz
│   ├── dbcb5cae8c458e2d18d2c17212299e3c62be909b.nq.gz
│   └── dfa6795cc132095e1b642541967702444ea33c7e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ba4713af853166590cd9119e513dd5943380ed58.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 40 files
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

[pallets/flask-docs](https://github.com/pallets/flask-docs)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
