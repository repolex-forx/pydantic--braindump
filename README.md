# Repolex Knowledge Graph of pydantic/braindump

RDF knowledge graph data for [pydantic/braindump](https://github.com/pydantic/braindump), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/braindump
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 11a3431f11a7ad3786c5e5f7c42f068c33fd7fb7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 11a3431f11a7ad3786c5e5f7c42f068c33fd7fb7
│           └── chunk-001.nq.gz
├── blob
│   ├── 027834b1aed743e036955b2f55abd71ed8a2bd80.nq.gz
│   ├── 28efe7ac4f6ff2adadaa9d942dd3d1c15a7291f1.nq.gz
│   ├── 2e3b61abf3748b609699af2a5387114f1e8834ca.nq.gz
│   ├── 47dc3e3d863cfb5727b87d785d09abf9743c0a72.nq.gz
│   ├── 500f63b038b452e4b236ecdb441587edbdb7a786.nq.gz
│   ├── 66f6450e59916d88f83698464c2910ad32df6143.nq.gz
│   ├── 6700baff2cdebfc075599ffd0be260be460274ed.nq.gz
│   ├── 6821884f9c8c43e07e451681604d8d851586dd81.nq.gz
│   ├── 70d76797262dbd33af112d99a0d42417ac6d5e50.nq.gz
│   ├── 7bc0a44fb42142bbedd77a98c32b6fa377948153.nq.gz
│   ├── 87d55972e8f1832c365615cfb242b6c10b5c7c42.nq.gz
│   ├── a56f0492a952ed4ff6a82dc9f6bdc3ad957ee31d.nq.gz
│   ├── ada20cc1dcd70d25dbe17fdcebb33eefeb2b0977.nq.gz
│   ├── b1665912f874d4f212ea0b7a70040a3db5e343f4.nq.gz
│   ├── b7cb4113a21885047d89e2c8b898f53fd9c237b8.nq.gz
│   ├── c2544b82f16f9e446eb54a3e0dea5a2aa776615b.nq.gz
│   ├── c46c4cf0b604352a8da983788cfb60389101cee4.nq.gz
│   ├── dad4c5883bbd6ce846147a20cef67945303fd902.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6ec4bafb80454331c25cdbe126786f560970115.nq.gz
│   ├── f76096ed61099bbc483fd354f811711ed1444f34.nq.gz
│   └── fae652720caeb044b71e2b8d7fb86f44f7f6e637.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 11a3431f11a7ad3786c5e5f7c42f068c33fd7fb7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[pydantic/braindump](https://github.com/pydantic/braindump)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
