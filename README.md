# Repolex Knowledge Graph of certifi/node-certifi

RDF knowledge graph data for [certifi/node-certifi](https://github.com/certifi/node-certifi), parsed by [repolex](https://repolex.ai).

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
rlex download certifi/node-certifi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 868e3910301344f33c8aaad8b58f34fae9d87e3b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 868e3910301344f33c8aaad8b58f34fae9d87e3b
│           └── chunk-001.nq.gz
├── blob
│   ├── 060005e33ff2b9cebc928fbc4e5fae2c49832e9b.nq.gz
│   ├── 1c6314a31833395fd5ff016a6506bdd51860657c.nq.gz
│   ├── 239ecff1372358a22aa99dcbb375fdad7abba817.nq.gz
│   ├── 2a5dc335bb92acd413bb954d099f2a74fff25840.nq.gz
│   ├── 3346ab5caed9219a4b75d579f9258da9baccbb5b.nq.gz
│   ├── 391f0a4e4b04a8b63e39431a8444e58f84214805.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 51fc7fed9a112a2fec7c2b5ebde50fb6a777724f.nq.gz
│   ├── 71324e205f30f9eef273c05949e6043bed8ae92b.nq.gz
│   ├── 802b53ff11e347c9bd2cabebeff5c51f716f1db9.nq.gz
│   └── e0cc34891cd3a6a9763d4f877a4ab58ba7ba7336.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 868e3910301344f33c8aaad8b58f34fae9d87e3b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[certifi/node-certifi](https://github.com/certifi/node-certifi)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
