# Repolex Knowledge Graph of klen/muffin-donald

RDF knowledge graph data for [klen/muffin-donald](https://github.com/klen/muffin-donald), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-donald
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7bea4ab65688fd8f65d2c45e73f1853a97c89f0a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7bea4ab65688fd8f65d2c45e73f1853a97c89f0a
│           └── chunk-001.nq.gz
├── blob
│   ├── 04f82df8f9169ee7a48409d1b15cede202d2f1d3.nq.gz
│   ├── 06dc9bf8660b87cb2647087fb4794f9c235975d7.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 10eb39f313510e034eae85681c40442941d52357.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 5b06d2314d7364b7f392e2a857d5e85ce2c1aada.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 6ae9711789c1c2d2c4fc4ba48c0ca45799785bfc.nq.gz
│   ├── 73869d65441effefde2afc14f1d8bbe3e4c1c035.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 7ba4d01440b01755dc7de440cdb2e6d9bc70a842.nq.gz
│   ├── 80826d975aa6e305dddbe44be4b9e7ea0ca1dd87.nq.gz
│   ├── 88d438cc029370cb64c85895c9060c6d49a41670.nq.gz
│   ├── 8ca98fe5a321b3073e0858c48e8424f94607f3d2.nq.gz
│   ├── 8ee320f8de22a125c182ad3ad1c6d9697d9b4e28.nq.gz
│   ├── ac6377a328fa0b7346d7791479b15f6f67ff771a.nq.gz
│   ├── cbd0ac32bdbb3678eef5895c58cdb60456c99d14.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── d4b48a0d2586d9c537e0ef31d28d9b2c38e63276.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── ef23051ba28a3e87238a94de1f097f9bbd894ac8.nq.gz
│   ├── efa9363b7868dbece1d467fac824df51a5dd65f6.nq.gz
│   ├── f840edb33d36b3d2ff3b85f626e56079955cd0fc.nq.gz
│   └── fd329f88ee6ec45a3b4f498bb7083d671b1ad4fd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7bea4ab65688fd8f65d2c45e73f1853a97c89f0a.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 33 files
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

[klen/muffin-donald](https://github.com/klen/muffin-donald)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
