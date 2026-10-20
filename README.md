# Repolex Knowledge Graph of coleifer/wtf-peewee

RDF knowledge graph data for [coleifer/wtf-peewee](https://github.com/coleifer/wtf-peewee), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/wtf-peewee
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d75c7cbc4edab7ad58fe28d691f80cbfe920f82a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d75c7cbc4edab7ad58fe28d691f80cbfe920f82a
│           └── chunk-001.nq.gz
├── blob
│   ├── 02d199e7d055015a1a0a9b7974bc5c4d856f133d.nq.gz
│   ├── 080d16e6f95718051208ad76f4b96411228f580e.nq.gz
│   ├── 0b11880ca49b64b098c3ca95eee185e0184190a9.nq.gz
│   ├── 15aaa28073528ad5bf3d56a6d1c776fc92a629e9.nq.gz
│   ├── 1b2a9912a5a211a8d80c51b1cb486bfa3be2bf44.nq.gz
│   ├── 1cf4b8917ad35c1256ef9676ff1f372e80b2264e.nq.gz
│   ├── 2cc910989fbebff205a777146dc868d174f9fc1a.nq.gz
│   ├── 3e5feabb86b32d4ab02d7862dbf61d3743674527.nq.gz
│   ├── 5226d9dfe43479f6a3b33a9128b57b55e7cbe0ea.nq.gz
│   ├── 68a3db5f2052f2e43dde4e9aaced432eb9212c80.nq.gz
│   ├── 8edb93a6cb87bfa9fdcd99e88560032e3f88a812.nq.gz
│   ├── 97cf47f46b89d22b3c8fd7ce911bd15f8fd25bfd.nq.gz
│   ├── 9ccf8543658cbe3625ac935a89887a0f5f2b3daa.nq.gz
│   ├── a778eb8085b1342c7479d639ed4831e56f8407dd.nq.gz
│   ├── a8d15e24e0cb9c9b1151f96c837abde62e7e9d02.nq.gz
│   ├── b50da94dd6a7cb743e0a0959b7479f5edf82eda1.nq.gz
│   ├── ba2ad4733403f67b6c1f7e9b7b36eeafb2922d76.nq.gz
│   ├── c25a2cb52307aab8e468a3bbd5b87fa5a229a60e.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   ├── cc46761bed2815f825be175f767f6120a48a306a.nq.gz
│   ├── edd9759ac412e8e67637f9ca860363d358f590f7.nq.gz
│   └── f17bd77221c09f9bf71e53cd2290a797708e3459.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d75c7cbc4edab7ad58fe28d691f80cbfe920f82a.nq.gz
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

[coleifer/wtf-peewee](https://github.com/coleifer/wtf-peewee)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
