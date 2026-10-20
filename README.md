# Repolex Knowledge Graph of asottile/scratch

RDF knowledge graph data for [asottile/scratch](https://github.com/asottile/scratch), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/scratch
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a6016c69dbc535c217c6d901232cda545784e4ba
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a6016c69dbc535c217c6d901232cda545784e4ba
│           └── chunk-001.nq.gz
├── blob
│   ├── 00fe92bd345a5b2b19337c03572386359cf08a34.nq.gz
│   ├── 04386736c41b7cf64dda7643dc469e818751e47f.nq.gz
│   ├── 0bb4137b501f8cfd667dc2c93adb0d29af1b03aa.nq.gz
│   ├── 0d20b6487c61e7d1bde93acf4a14b7a89083a16d.nq.gz
│   ├── 1fe4adfbf123e5c1cbe38604a83ca7897d9a3e92.nq.gz
│   ├── 2627edc8cd5832898103b6cb357ed37e0d735adc.nq.gz
│   ├── 2c6b03e0fcbaeca4c599397f6b7f92d4aef8bf63.nq.gz
│   ├── 318bc8aa40ad60a66aaaef942531069bd3e7b475.nq.gz
│   ├── 339b8835b3ab83688119d9bd2051bb9575856a41.nq.gz
│   ├── 3a9423baa70f0f40617e577e9acf2749aeb4fdb3.nq.gz
│   ├── 4afb73956cd45a05a158e7c97875d853f12065df.nq.gz
│   ├── 54515eee37ee3b38688b7752bf7b8f926147506f.nq.gz
│   ├── 5bb491bc725127f34ac39ec3eec01ce502ff114a.nq.gz
│   ├── 5c66a063afebd765c9cd6da602088113e0c4a7e5.nq.gz
│   ├── 698372a31ae8e167c87f1196b5ca498ec94ebef2.nq.gz
│   ├── 6a5d3a15c15d619c7f6b7d0f83de934146cc85f6.nq.gz
│   ├── 6e932b01eb8a43e08a61b7c3fb1af0ee2e0ced7f.nq.gz
│   ├── 712c45f89393f7d0188607cf0ba286c2aba90331.nq.gz
│   ├── 768a532d923b47bc09ee5e4f56a98fa35aa1349e.nq.gz
│   ├── 7a7300a1e90c7d02d7ad5612ca6acdea5526931a.nq.gz
│   ├── 83800428d095e8b14af05583fc94229ce0fcfe93.nq.gz
│   ├── 86794cc012cbe476dd32a74ffb33b31116272e7b.nq.gz
│   ├── 8aa8631e8976cc1846a3baf310633b3016dd6046.nq.gz
│   ├── 8d1e06c795af1af706ae6450cd35e0dfcea2bd13.nq.gz
│   ├── 912627482364c594263ea8673d1a2eb88adeaa9a.nq.gz
│   ├── 93d62d07fdc9435ee2145d63dcb4b464237629e0.nq.gz
│   ├── 98d13dc4dc0eed620c77593d9ef5fe69d2a8261e.nq.gz
│   ├── a506785da2dba6767e76236e0924592b7153b6f8.nq.gz
│   ├── b751d6b9fadee65a1c1117dcf0981573a70b9823.nq.gz
│   ├── b86ec4ce743a884686c154b0f04d21ed33dbf311.nq.gz
│   ├── c14f207ab37bcad0c8eaddd3a66773d7f6a53238.nq.gz
│   ├── c25cfe138474e83280791f09559f515dcaa8b814.nq.gz
│   ├── d8c6b3274a9fd4a98ed933829a7f20884fb6ee5d.nq.gz
│   ├── da61f16cbf54acc00b4f906695eb32663b1b4ec3.nq.gz
│   ├── e03e944532a11962fd394d18a60221fb9943e5f7.nq.gz
│   ├── e50e1474af690885b0eda840c4b947405834a0ed.nq.gz
│   ├── e75680919e409d9dcd9cb9a21ed814331d081df5.nq.gz
│   ├── ed75a9500223cbce1ca24b46208bb213c10d79c1.nq.gz
│   └── f5f13a22b36607bccffb675d99d2146c36b90ea9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a6016c69dbc535c217c6d901232cda545784e4ba.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 47 files
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

[asottile/scratch](https://github.com/asottile/scratch)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
