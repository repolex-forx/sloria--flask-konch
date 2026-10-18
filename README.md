# Repolex Knowledge Graph of sloria/flask-konch

RDF knowledge graph data for [sloria/flask-konch](https://github.com/sloria/flask-konch), parsed by [repolex](https://repolex.ai).

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
rlex download sloria/flask-konch
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e194dbaa1777c5eb20cf7b848089f03c8136d638
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e194dbaa1777c5eb20cf7b848089f03c8136d638
│           └── chunk-001.nq.gz
├── blob
│   ├── 195395c2f298612920b1616af0d98be0496278b6.nq.gz
│   ├── 311a8756ed9a636fe0f08c2e00f10f936961857a.nq.gz
│   ├── 3302ba0b681c2c27d09962ca8edf8631866a8786.nq.gz
│   ├── 3aac49c6a016a031088beb6db22930e6939869d6.nq.gz
│   ├── 5c869776234cd0eb4ea0d968ed4017c91d23b8a7.nq.gz
│   ├── 6693c94e2bc166f0643fc530c0b05c0e637b3220.nq.gz
│   ├── a04147cae415cb76930d95a7f3d03f5575cd0816.nq.gz
│   ├── bbb2905d0d501a0916d673b29657f6caac883a2b.nq.gz
│   ├── bdf6747a2699bc8cc328d72c3ce5fc283076ab73.nq.gz
│   ├── bfde558a31756c5af6c5de53fcfc871ae555d535.nq.gz
│   ├── cae4f39466f4e0149b5f9da229e4bfe28c7ea58a.nq.gz
│   ├── d2a38fc0424969003956fc8e8e5e65512ca119d1.nq.gz
│   ├── d6bd0dd3ab89ea4e21ac1b4a5c9c2e03cf86660d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ee5c2750aad201623487d0d5ed673e89743252d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e194dbaa1777c5eb20cf7b848089f03c8136d638.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[sloria/flask-konch](https://github.com/sloria/flask-konch)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
