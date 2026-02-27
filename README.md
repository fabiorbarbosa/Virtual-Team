# Virtual Engineering Team

Repositório de orquestração de papéis de engenharia com instruções em `AGENTS.md` e catálogo dinâmico em `.agents/`.

## Architecture Overview

Este projeto organiza diretrizes de trabalho em dois níveis:

- `AGENTS.md` na raiz: fluxo global, guardrails e formato de saída.
- `.agents/**/AGENTS.md`: papéis técnicos por categoria (governança, revisão e especialistas).

## Folder Structure

```text
.
├── AGENTS.md
├── README.md
├── .gitignore
└── .agents/
    ├── governance/
    │   ├── tech-lead/AGENTS.md
    │   ├── principal-engineer/AGENTS.md
    │   └── qa-architect/AGENTS.md
    ├── reviewers/
    │   ├── critical-reviewer/AGENTS.md
    │   ├── complexity-guard/AGENTS.md
    │   └── failure-mode/AGENTS.md
    └── specialists/
        ├── backend/AGENTS.md
        ├── database/AGENTS.md
        ├── design/AGENTS.md
        ├── devops/AGENTS.md
        ├── frontend/AGENTS.md
        ├── mobile/AGENTS.md
        ├── security/AGENTS.md
        └── uxui/AGENTS.md
```

## Run / Build

Não há aplicação executável ou pipeline de build neste repositório no estado atual.

Uso recomendado:

1. Ler `AGENTS.md` da raiz.
2. Carregar os papéis necessários em `.agents/**/AGENTS.md` conforme o tipo de tarefa.

## Environment Requirements

- Git para versionamento.
- Editor de texto/IDE para manutenção dos arquivos Markdown.

## Next Steps

- Definir exemplos práticos de uso para cada papel em `.agents/`.
- Adicionar templates de saída para cenários recorrentes.
- Incluir validações automatizadas para consistência dos arquivos `AGENTS.md`.
