# Repolex Knowledge Graph of stretchr/objx

RDF knowledge graph data for [stretchr/objx](https://github.com/stretchr/objx), parsed by [repolex](https://repolex.ai).

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
lexq download stretchr/objx
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b152998cb1395c270b4ae1659971578328983793
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b152998cb1395c270b4ae1659971578328983793.nq.gz
│   └── repolex
│       └── b152998cb1395c270b4ae1659971578328983793
│           └── chunk-001.nq.gz
├── blob
│   ├── 01c63d7d3bbf71bfea2dba315c57bf17e988a0b9.nq.gz
│   ├── 06eb996e89a2142ae06c9654a389e81a2bb9318a.nq.gz
│   ├── 1afdbe0056456d842c28f15ce03a517edb7558f8.nq.gz
│   ├── 30602347512c3d61110e58a1bd8ed8a6c52ca3bd.nq.gz
│   ├── 3fe0892940c5bedc3fe6ef2862da301ed816d318.nq.gz
│   ├── 44d4d9d5a7c38acb84d299e75e108e197b3040df.nq.gz
│   ├── 45850456e17f8d735b3c26e8ad77238c564c9f7c.nq.gz
│   ├── 4e5f9b77e69cb90c6beeb0b313ed56f87411d9a3.nq.gz
│   ├── 5099d59c97eaee1589edf11433d185bf0a3b3baa.nq.gz
│   ├── 54727f574dc1d488254a1962907577829a740490.nq.gz
│   ├── 559fa399c130eb720031bfb75daf16c8eef220df.nq.gz
│   ├── 5d1e492a04dd1e29772b1fd299a45a69d85b8cfb.nq.gz
│   ├── 6512bb768838e2a99fff8db2072c87c85c7d6fd6.nq.gz
│   ├── 6817ec29d4ef2b6df62cdd2f8fbcd9bd8adafbf6.nq.gz
│   ├── 692be8e2a9feb35955e1324b6004adb235838410.nq.gz
│   ├── 6b40d772b721ae0ea2eca26328e655c0b80c56a7.nq.gz
│   ├── 71702908defd2a07ce00e5ec7e87d7cea5da0df6.nq.gz
│   ├── 72f1d1c1ce3d4a81005875f6f3dd8572507e8a16.nq.gz
│   ├── 7b6f1a71a54194afce030b0810ea0cfacbd29b07.nq.gz
│   ├── 80f88d9fa29f84995f379f9cd61f702de64d9d3a.nq.gz
│   ├── 82adac2967989fa5994cbad3ff20b71f325eddcf.nq.gz
│   ├── 8796525642765f74e5d53b82665712e0f893d6a4.nq.gz
│   ├── 8a79e8d674c0dc48bcf9fd0c1f8ce5207d0e85f0.nq.gz
│   ├── 9a5f6e1f71471b3e6f13cdb06f2d6ac497f2609d.nq.gz
│   ├── ab9f9ae67cbf0c387afa7a9618f01666485aec0b.nq.gz
│   ├── b170af74b39ab25a4a2c0d02ce8a4ca9880b9a18.nq.gz
│   ├── bf6944e71bdc96eea89f926a9e32a810a532108e.nq.gz
│   ├── c3400a3f709a29145475a918a8912b550069e3b2.nq.gz
│   ├── ca16901680cd412ac02ad1c203cf6a63435f7f34.nq.gz
│   ├── d02e63b972a68307d7f28d1f2fed601dfb4a4248.nq.gz
│   ├── d9e0b479a4c0f89957ed7cebc98d186740d1a96c.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e994feebd8ea311a5f2db1c132ee0fa54f15b17a.nq.gz
│   ├── e9ba8307354f272a462b69c1d04a116cde91d462.nq.gz
│   ├── ea58090bd21e1b3182e644a2b27fb181a12cb6f6.nq.gz
│   ├── ede23411912a8fd535d5caa4f198dd983a1abee2.nq.gz
│   └── f5579b0e7c85159b881c0d67d1d48fb23b3411b2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b152998cb1395c270b4ae1659971578328983793.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 46 files
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

[stretchr/objx](https://github.com/stretchr/objx)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
