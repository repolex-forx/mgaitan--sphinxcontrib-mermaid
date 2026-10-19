# Repolex Knowledge Graph of mgaitan/sphinxcontrib-mermaid

RDF knowledge graph data for [mgaitan/sphinxcontrib-mermaid](https://github.com/mgaitan/sphinxcontrib-mermaid), parsed by [repolex](https://repolex.ai).

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
rlex download mgaitan/sphinxcontrib-mermaid
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 864b5436240962288f85ebd69884704aa1cca304
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 864b5436240962288f85ebd69884704aa1cca304
│           └── chunk-001.nq.gz
├── blob
│   ├── 060d56e646a522304747d789d2407296db77ea80.nq.gz
│   ├── 0de2d836fa2b70ac2736bcf6ed5618dcb9c1b329.nq.gz
│   ├── 1be820b3e467feaa694fa2ef937547fa1b8a1cc7.nq.gz
│   ├── 20189a4c752c992b3c1f4ca94b2a30d0f2839455.nq.gz
│   ├── 2840a3275504dadd7bbb4cab933d447efee4d617.nq.gz
│   ├── 303a37a3a9ed3da4d9ad411d618b9c68ab8d73d6.nq.gz
│   ├── 30581ec2a1df4c8af45822e22e99c8a956c5a76d.nq.gz
│   ├── 31b5be37afe84a951a69467aa935bdde8651e10e.nq.gz
│   ├── 3201af7b736ff2493d705f1bee84105a1ec9fd59.nq.gz
│   ├── 322f02c7bbb8f13870c801223906ca36cf070766.nq.gz
│   ├── 35cc7f62600220e1995283b55478f735c4a36cd1.nq.gz
│   ├── 38e59c073c40f932ac1f937af5f862fc384f6663.nq.gz
│   ├── 3b5c4e8ea74f119786ba773553165de18d05481d.nq.gz
│   ├── 3e04f5488077202dfc2cb0c819cda19cb77ea3cc.nq.gz
│   ├── 4930bd6166d44e80980d187c76fb0ef1d037f1e8.nq.gz
│   ├── 4c07fe7c3bbeb5f87d0b0834c2367aad36154138.nq.gz
│   ├── 5b6aa82df9b7a62ffd89d7cd163889c6f6c33d99.nq.gz
│   ├── 84ee931ed78995766effda85de43281ba436d596.nq.gz
│   ├── 85008e1e3d8c38c1a9ea49be27c00e5486574d62.nq.gz
│   ├── 8d90e5b5ea368c3c63440d7ed0c6c54e4d62c016.nq.gz
│   ├── 8daa27bf2cd72bf18c00a3a95c21aff21782d55d.nq.gz
│   ├── 91b4bd10df96d10575c54fb88b86663044866037.nq.gz
│   ├── 9509c47e8680b4df452086dee697c35e25a3513b.nq.gz
│   ├── a999f734790a9a73bcbc7b54f9bf65d47ba22754.nq.gz
│   ├── b696212b1831445f084c2a58f6de97f2cd255045.nq.gz
│   ├── bc0153fdbd31d54083b9c940a791590a8d120e4c.nq.gz
│   ├── bd18aae29a991fc57229a2421e809112b5e9616c.nq.gz
│   ├── be006de9a1ae3b9628e796c74277cd6d61e0a34a.nq.gz
│   ├── c762f98f52742668e8695a9cec7b4f9d9a8ed0ee.nq.gz
│   ├── d19ce3bf8127976f5393002fcbb4249dd70fe47e.nq.gz
│   ├── d9f078283b411c67ebd03de6114855522cfa6390.nq.gz
│   ├── da256cd83766803cf9515c3416b1ad467d49468c.nq.gz
│   ├── e0f3cfe721f173e99c834d4b6f38f8a786579b5f.nq.gz
│   ├── ead2621cda1a30adcc5c831d9de45b51638264f1.nq.gz
│   ├── f40474c54eded62161238c5f9db01aa81abe7a75.nq.gz
│   └── f8915d3b67d8b7492831e4c078228cddf8bf0f2a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 864b5436240962288f85ebd69884704aa1cca304.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[mgaitan/sphinxcontrib-mermaid](https://github.com/mgaitan/sphinxcontrib-mermaid)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
