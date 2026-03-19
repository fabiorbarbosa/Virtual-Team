# create-skill.md

Quero que você crie uma Skill reutilizável para análise estrutural de código-fonte backend/frontend a partir de um diretório informado.

## Objetivo da Skill
- Ler recursivamente um diretório base.
- Identificar e mapear:
  - subdiretórios
  - interfaces
  - classes
  - DTOs
  - contratos
  - relacionamentos entre arquivos
- Gerar uma visão estruturada e padronizada da arquitetura encontrada.

## Comportamento esperado da Skill
1. Receber um caminho de diretório como entrada.
2. Percorrer toda a estrutura recursivamente.
3. Detectar padrões comuns de nomenclatura, incluindo:
   - interfaces com prefixo `I`
   - DTOs com sufixos como `Dto`, `DTO`, `Request`, `Response`
   - classes de serviço, repositório, handler, controller, model, entity
4. Para cada arquivo encontrado, identificar:
   - nome do arquivo
   - tipo do artefato (interface, classe, dto, enum, record, etc.)
   - namespace/module/package
   - herança
   - interfaces implementadas
   - propriedades principais
   - métodos principais
   - dependências/imports/usings relevantes
5. Organizar a saída por diretório e subdiretório.
6. Destacar relações entre contratos e implementações.
7. Separar claramente:
   - Interfaces
   - DTOs
   - Classes de domínio
   - Serviços
   - Repositórios
   - Controllers/Handlers
8. Ao final, produzir um resumo arquitetural contendo:
   - visão geral da estrutura
   - principais camadas encontradas
   - convenções identificadas
   - possíveis inconsistências de organização
   - oportunidades de melhoria estrutural

## Regras importantes
- Não alterar nenhum arquivo do projeto.
- Apenas ler e analisar.
- Se encontrar múltiplas linguagens, adaptar a análise ao contexto de cada uma.
- Priorizar C#, TypeScript, JavaScript e Java, mas ser genérico o suficiente para outros cenários.
- Se houver ambiguidade, inferir pelo contexto do nome do arquivo, conteúdo e posição na árvore de diretórios.
- Ignorar arquivos de build, binários e dependências externas (`bin`, `obj`, `node_modules`, `dist`, `.git`, etc.).

## Formato de saída
- Gerar a resposta em Markdown
- Incluir as seções:
  1. Estrutura de Diretórios
  2. Interfaces Encontradas
  3. DTOs Encontrados
  4. Classes Encontradas
  5. Relacionamentos
  6. Resumo Arquitetural
  7. Pontos de Atenção

## Modularização para reutilização futura
Além disso, quero que essa Skill seja pensada para reutilização futura, então estruture a lógica de forma modular, com etapas bem definidas:
- descoberta da árvore
- classificação dos arquivos
- extração de metadados
- correlação entre artefatos
- geração do relatório final

## Itens adicionais
Se fizer sentido, crie também:
- instruções de uso da Skill
- parâmetros de entrada esperados
- exemplos de execução
- limitações conhecidas

## Entrega esperada
Entregue a Skill pronta para uso, com foco em clareza, extensibilidade e reaproveitamento em outros projetos.
