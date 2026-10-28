# Repolex Knowledge Graph of python-hyper/branchmgr

RDF knowledge graph data for [python-hyper/branchmgr](https://github.com/python-hyper/branchmgr), parsed by [repolex](https://repolex.ai).

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
rlex download python-hyper/branchmgr
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 574dc8dc90382ef3dd8687737fc39c929e9bb641
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 574dc8dc90382ef3dd8687737fc39c929e9bb641
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f356cc57bfa00a3b251402604c54702fb414c96.nq.gz
│   ├── 3bf2cbbc0c96546a287fe0ad24b80ee53cc47d9e.nq.gz
│   ├── 649e30d310d8fd3d0e773f74178ff6f4da3e44dd.nq.gz
│   ├── 843a4250b43fbffb5241078ae0efc641132d2870.nq.gz
│   ├── 90ee449e0a42c7c255aa8401d9e45dd8dd9e8493.nq.gz
│   ├── 98a24edf8de39bb2f4963bf4eb0a8750f820f392.nq.gz
│   ├── 9d19e106e3ce4ffa975e054f77e6d2b8a522c942.nq.gz
│   ├── aa8d17c3d85e5cd4a1c71469eaaaac9f3522f194.nq.gz
│   └── ca8b131e258ea6c811606e94a43187c2839fcfe3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 574dc8dc90382ef3dd8687737fc39c929e9bb641.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[python-hyper/branchmgr](https://github.com/python-hyper/branchmgr)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
