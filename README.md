# Repolex Knowledge Graph of PyCQA/pep8-naming

RDF knowledge graph data for [PyCQA/pep8-naming](https://github.com/PyCQA/pep8-naming), parsed by [repolex](https://repolex.ai).

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
rlex download PyCQA/pep8-naming
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1587bfe4ca73800d64a067580a8f6eb1b8dad209
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1587bfe4ca73800d64a067580a8f6eb1b8dad209
│           └── chunk-001.nq.gz
├── blob
│   ├── 090042b3c3858631c4b21801ad5f2fd13c9bc470.nq.gz
│   ├── 108d857781864ef9b6b533e2120e4c98485ea4cc.nq.gz
│   ├── 187f2cdc3576587b7abe827b2f9b80057945431d.nq.gz
│   ├── 22e3ba35b33ede9a4537ba82cecfcb550943cbe7.nq.gz
│   ├── 2afa41c80d7035d31dec9add563aaa9b805f8bcf.nq.gz
│   ├── 2d6bf6935a411961776fe6a5cc9fb7760722c785.nq.gz
│   ├── 3462aac523bc71a629aeac280d61b864ffe1f050.nq.gz
│   ├── 34ce2f29a71c57f2331b9a558c68f87ef8300157.nq.gz
│   ├── 5098f80d6b59a4bdc1f6000ee6d23b9f57c5d284.nq.gz
│   ├── 51c8a2abc5e00edf72306d9ee19f7c658adbd916.nq.gz
│   ├── 554b973e9c54468459a63dd6f0fb26b2ec2d7858.nq.gz
│   ├── 5a0ba27783e384eb3d5a49c7c9a9bdef9378545d.nq.gz
│   ├── 6d1c404ebc24334a1b3c5c856a6ac32e27436f86.nq.gz
│   ├── 741b435e4af390e484e5a8408559691357a6b675.nq.gz
│   ├── 755bf2d50fc8c94381d951e9427551be4a4e0259.nq.gz
│   ├── 809832ef20c065242a265f64289bb60e74cadd42.nq.gz
│   ├── 9612a0c196d44c656a95cca4f33c605aec92ae0a.nq.gz
│   ├── a7621d39f87432a7fcd92c5646bdd1523a6f2dcc.nq.gz
│   ├── ae3d48086e7de59d38afe57301f88b2c61735201.nq.gz
│   ├── c516eeed33bf111cf473fd3ad1dc4d8e12fa21f8.nq.gz
│   ├── c644b694f238c894b5cc7ce9f6eeaee60590013e.nq.gz
│   ├── cb9c4071ecddfb3ed36591d654f60341d667c35a.nq.gz
│   ├── d386a3f6f8ac233e11815610297ae2d042beb327.nq.gz
│   ├── dd21409a2e4e1bcb645478e1f38b37a749ad2346.nq.gz
│   └── df2f3256e5daae9b01d20d13c2f831b2f5fdde3b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1587bfe4ca73800d64a067580a8f6eb1b8dad209.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[PyCQA/pep8-naming](https://github.com/PyCQA/pep8-naming)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
