# Repolex Knowledge Graph of anthropics/anthropic-tokenizer-typescript

RDF knowledge graph data for [anthropics/anthropic-tokenizer-typescript](https://github.com/anthropics/anthropic-tokenizer-typescript), parsed by [repolex](https://repolex.ai).

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
rlex download anthropics/anthropic-tokenizer-typescript
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4d75e64d32fe5cd2b5a24d954242f9fab12e8b4b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4d75e64d32fe5cd2b5a24d954242f9fab12e8b4b
│           └── chunk-001.nq.gz
├── blob
│   ├── 14ec4464c56075c979e4380bf2139441caf48996.nq.gz
│   ├── 1b763b1bae0d0061ad60e8847714df98e68f7eac.nq.gz
│   ├── 388314f5f42cf18696d81b085858a9e45c241f62.nq.gz
│   ├── 4006f770784f86a87ccb77359614407b87759d58.nq.gz
│   ├── 506b4a1b916069e606d130479050af6feb5af19f.nq.gz
│   ├── 5c945e140ff64eee100a20dbb3b772743f8b85d9.nq.gz
│   ├── 60f0e7a3514bfc1511b2a0915e07d5467ae00025.nq.gz
│   ├── 6f72f437cf25ab5b665ca1811da8f65bfb8af8c9.nq.gz
│   ├── 8432893a31a44d1df4e45f2844078065a8f5d574.nq.gz
│   ├── 93cab344de4136ed953946da089c6439df327910.nq.gz
│   ├── ac71a66cf790ec2b4cc699891aed7671a6233dd7.nq.gz
│   ├── da4c7ae30817476f68b1ed96fd2fd8baca171edc.nq.gz
│   └── e9b3bac6045e4a94c5e3d34bfa5d1e58077bc0a6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4d75e64d32fe5cd2b5a24d954242f9fab12e8b4b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[anthropics/anthropic-tokenizer-typescript](https://github.com/anthropics/anthropic-tokenizer-typescript)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
