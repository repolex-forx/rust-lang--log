# Repolex Knowledge Graph of rust-lang/log

RDF knowledge graph data for [rust-lang/log](https://github.com/rust-lang/log), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download rust-lang/log
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 98abd8feeaba4a8c7bdbf429bf2fb9eaab3faf68
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 98abd8feeaba4a8c7bdbf429bf2fb9eaab3faf68.nq.gz
│   └── repolex
│       └── 98abd8feeaba4a8c7bdbf429bf2fb9eaab3faf68
│           └── chunk-001.nq.gz
├── blob
│   ├── 04a410e146c3a7b95c3fb67a9170d8d0b1074e34.nq.gz
│   ├── 0df03e673304d9e1bbb5101f31c082837a70ab06.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1b82ecd3ae245234793e97348e156bde41b4ed15.nq.gz
│   ├── 1ff4a89ba7dc22e6ba47d13e215d73450c0ce36b.nq.gz
│   ├── 2c96eb1b6517f2617f9ddeae9f07f5fd7bd7ddef.nq.gz
│   ├── 39d4bdb5acd313c1a92dbeaa1c379aaf0596a315.nq.gz
│   ├── 3d1f291d5085a5713ace06295a3ae312a7d0f73c.nq.gz
│   ├── 5036fb8e3c9c332a790eb8ce9a789bf7dea7df86.nq.gz
│   ├── 66638c65ef0880fee70fd4da4348b75766cb13f5.nq.gz
│   ├── 74d0e04dbd6ed9ed0f1a4954dc7c28eda3bcb36a.nq.gz
│   ├── 7e2f9da7e3c1a3b0aa5129a47364d756223903cf.nq.gz
│   ├── 819d2d5d65648ef4bd069e8cbed4595a5cb173cb.nq.gz
│   ├── 841011deb237183a1ae6fa63a35f29d3e8597d6d.nq.gz
│   ├── 8672e2531071ebdbe729d686c68c27cb65f4dbb0.nq.gz
│   ├── e08d46db1951caf46a8f5ed7f96a8351dd14754e.nq.gz
│   └── f9a7788d2e608d524a7929c57539a571eff63578.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 98abd8feeaba4a8c7bdbf429bf2fb9eaab3faf68.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 26 files
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

## Source repository

[rust-lang/log](https://github.com/rust-lang/log)

---
*Parsed on 2026-04-23 by [repolex](https://repolex.ai)*
