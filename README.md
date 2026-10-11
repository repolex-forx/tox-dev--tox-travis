# Repolex Knowledge Graph of tox-dev/tox-travis

RDF knowledge graph data for [tox-dev/tox-travis](https://github.com/tox-dev/tox-travis), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-travis
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fd98366ef28b44e2001f4b491573290f1908be91
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fd98366ef28b44e2001f4b491573290f1908be91
│           └── chunk-001.nq.gz
├── blob
│   ├── 08f37962581f400b5a24900b2548ff291bc6fee3.nq.gz
│   ├── 1388d4f75289c94fe57f2391d6d17bddef813267.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 30f7ef0307d45cf77e8956b26c7f9d4e28147c4e.nq.gz
│   ├── 3202689b2fd5f6431992794b64d142c68da733e6.nq.gz
│   ├── 37c470f9424ed173f9aa0631324a52bda6d100e8.nq.gz
│   ├── 385a0f7b70e66e06da554731be91be3cceb92575.nq.gz
│   ├── 529d2732dce968c0115c2eedf699477414f81137.nq.gz
│   ├── 53e67f70ca043d9056c9334ff4ee99079fac1aa4.nq.gz
│   ├── 55f1b0632f3cada3da820b032753f1c30ecf7e9f.nq.gz
│   ├── 5cccd493c3f6f9afdf1e432d7a6db052881c7b3d.nq.gz
│   ├── 5ff77ed42ea8feb4c7e433a3ba102e063681b59d.nq.gz
│   ├── 67ee49c5fa229448fe8b03eb4fde305e41a561fe.nq.gz
│   ├── 69751f2f21097a098ddd539f8bed18e05f2f621e.nq.gz
│   ├── 72340811817ff8f1f5a6fe14753ccc1b218253e1.nq.gz
│   ├── 8528b3c17a6d3eb9ddc3c33dc65d928dd2888dd4.nq.gz
│   ├── 8a65536546aab42f071b9995c3d649cbbff533e1.nq.gz
│   ├── 90714fc78c0e8af52f30dc3a29c8a9b5a905f691.nq.gz
│   ├── a51f2bccc280a982842e896e72b8face297707f6.nq.gz
│   ├── afc3f1f52c05f7028e604e2a75fea92109dd6a03.nq.gz
│   ├── b21cb4af1bba0429ba94c62b82f1910a72b7b9f8.nq.gz
│   ├── bd8711ff4c64a27d745f0f895e78db68a168da0e.nq.gz
│   ├── bf086370c1c17d412524bdbe4a76e8b5f8fd969b.nq.gz
│   ├── d242ff5b2251944490e665b0435d408a0f3a23e6.nq.gz
│   ├── d359e920f6085ac2e997718d05d8255aedf5fc79.nq.gz
│   ├── d84402b24fb0ca591d08f5c761b7b2635f8f0175.nq.gz
│   ├── e4661dd46478dd358c900fffc6f1a2661300bda1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e907dc984bee6d8d515338b0bb53630933e7f6d7.nq.gz
│   ├── ebb50ffb8f5ded7a06d8948ba042361a764f3275.nq.gz
│   ├── f5b88021caf7f4409e7d46faafa7d9782a2600a3.nq.gz
│   └── fcdc2b67945e7a81a499420c6bfd18be08d254ba.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fd98366ef28b44e2001f4b491573290f1908be91.nq.gz
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

[tox-dev/tox-travis](https://github.com/tox-dev/tox-travis)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
