# Repolex Knowledge Graph of jaraco/jaraco.itertools

RDF knowledge graph data for [jaraco/jaraco.itertools](https://github.com/jaraco/jaraco.itertools), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/jaraco.itertools
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 2712e916b2b70f43b940e072f446557caf21dd14
│   │   │   └── chunk-001.nq.gz
│   │   └── cee7e54a836bc47a6cb5d291b19f0985036fd4a9
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── cee7e54a836bc47a6cb5d291b19f0985036fd4a9.nq.gz
│   └── repolex
│       ├── 2712e916b2b70f43b940e072f446557caf21dd14
│       │   └── chunk-001.nq.gz
│       └── cee7e54a836bc47a6cb5d291b19f0985036fd4a9
│           └── chunk-001.nq.gz
├── blob
│   ├── 14243051409fccc0404edd15a2c993e572626dd8.nq.gz
│   ├── 1719cac69dd80d416e01752c2440e22957a50459.nq.gz
│   ├── 1edccc762052a7d6856baab3a08b4ac3533e4393.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 43ace5be310745567fadbb5c624b7e52c69b7602.nq.gz
│   ├── 53513eee9b3a2f4df50df1febd59a5206718995a.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 5c05f9e27d57a4b7a3c3a9fdfecf8cddb8be499f.nq.gz
│   ├── 633e3648e99a9faf806677e5a2aabe6036b29f7a.nq.gz
│   ├── 63c0825f6bd49615f4f386b95463111f7992f6bc.nq.gz
│   ├── 6461d3d1feac8a48aa6e1c17777f39f3e2d975a5.nq.gz
│   ├── 6fa480e44f38768722368d7a986607adacf41d99.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 7d67d09a8c908dd4e062b0a828ef732e1cdd6c8b.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── a7f603f3e07aeca7b637e6f7e7d12216fe6b3ecc.nq.gz
│   ├── b62fb891c33d7fdb6092d680e906c93181c69533.nq.gz
│   ├── d222b178d4e94682f7e559f809132df9041de36a.nq.gz
│   ├── d53bbd1a771fc92a23e5c9262216d13961eccebb.nq.gz
│   ├── db4cebb634a92e476bb10b88320054ca6d271b4c.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── e4c1d80d8278d90009849cd768cbb9b893a6ccb1.nq.gz
│   └── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── cee7e54a836bc47a6cb5d291b19f0985036fd4a9.nq.gz
├── filetree
│   ├── 2712e916b2b70f43b940e072f446557caf21dd14.nq.gz
│   └── cee7e54a836bc47a6cb5d291b19f0985036fd4a9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

17 directories, 42 files
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

[jaraco/jaraco.itertools](https://github.com/jaraco/jaraco.itertools)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
