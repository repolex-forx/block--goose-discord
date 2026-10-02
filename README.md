# Repolex Knowledge Graph of block/goose-discord

RDF knowledge graph data for [block/goose-discord](https://github.com/block/goose-discord), parsed by [repolex](https://repolex.ai).

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
rlex download block/goose-discord
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b70a363d73409f9bd0b15aabc17e60f94ad82d88
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b70a363d73409f9bd0b15aabc17e60f94ad82d88.nq.gz
│   └── repolex
│       └── b70a363d73409f9bd0b15aabc17e60f94ad82d88
│           └── chunk-001.nq.gz
├── blob
│   ├── 0eccaab481d6d68c925d56860a852251e0ec1706.nq.gz
│   ├── 106202f22fd5facae86373f8d7b26b7dd3fdbf23.nq.gz
│   ├── 17bcfc02fa2eaf3c2e13494b5fc0572d965471da.nq.gz
│   ├── 1d93cef331b1fc5a8ee35676ab38cd310b664120.nq.gz
│   ├── 22dacaedbabbccec5df608467a85028618a844ab.nq.gz
│   ├── 25d104d3c1c834144433b200ea6e04e83b780e11.nq.gz
│   ├── 2987198d6327d975651b579c7ace2ff02e3a33c1.nq.gz
│   ├── 358bf09b871cb60810a2db1e572aa07103ead0fd.nq.gz
│   ├── 3a722a9eaf66707da857ada211d83f72e2242d0a.nq.gz
│   ├── 3b142965109e3f9598be202631ea7272e2c2c109.nq.gz
│   ├── 4146e81a7353b5a894b0be5c42ee95979fc18718.nq.gz
│   ├── 430b2b19e7d440c76fbb735bca0d88f42d865096.nq.gz
│   ├── 4e6e6408ffcbd5b79d9a3a66fbe56882d9e391ad.nq.gz
│   ├── 664205e8378a80d3895e5f0533f4c3b52869493f.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 6d83c9d5b19c4d5b6e8acb738c0f219b76942c0d.nq.gz
│   ├── 79e5c2afdbead038bdfcf4ca2e350e991096dbe7.nq.gz
│   ├── 849d47a75fd0066240485f987db983af1abb5b31.nq.gz
│   ├── 86a9cf7c4deea223fcadd3a78628cefe6f6c87dd.nq.gz
│   ├── 95b911b5036ea0b6f35401886d1535dd86a7badb.nq.gz
│   ├── b72af8f44767e14d592baeb857791cac9585fdee.nq.gz
│   ├── bf468ff2255279d58acb5a1c618d103e29e8fe06.nq.gz
│   ├── d1bc07a06b3685903c64113c95551644e702b6a2.nq.gz
│   ├── d738fc5f658ab4f535f2a03c6dd3060bf5c7e042.nq.gz
│   ├── dd22a3824c199a28d48babd5f72d1a626ff2aa9f.nq.gz
│   ├── e9b6c2ecfab1fdca849bb57ce02bc82633028a10.nq.gz
│   ├── ea3f6fdea53c7fda50d609fc598866baf74c6c1f.nq.gz
│   ├── ec154fb251697c945fbb7ce0a602655c86eafd52.nq.gz
│   ├── f286c8ad44fa589a048e77f38c462bd00af07355.nq.gz
│   ├── f8f6ad877e14466dec8ba8af47be60c6a5e90c7f.nq.gz
│   └── fe0802f6b838c35bae5381cef4efcebf9f1f59e4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b70a363d73409f9bd0b15aabc17e60f94ad82d88.nq.gz
├── filetree
│   └── b70a363d73409f9bd0b15aabc17e60f94ad82d88.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[block/goose-discord](https://github.com/block/goose-discord)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
