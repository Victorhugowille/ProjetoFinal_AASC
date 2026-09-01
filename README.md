# 🏫 Sistema de Gestão de Escolas — Análise Arquitetural

> **Trabalho Avaliativo** da disciplina de **Análise Arquitetural de Sistema Corporativo** — 6º Período

## 📋 Sobre o Projeto

Este repositório contém a documentação arquitetural de um **Sistema de Gestão de Escolas**, elaborada como projeto final da disciplina. O objetivo não é a implementação do sistema, mas sim a **análise do domínio, decomposição em módulos e proposta de uma organização arquitetural coerente**, aplicando conceitos estudados ao longo do curso.

O sistema proposto resolve a organização da **grade de horários (só o pedagogo; alteração em qualquer dia)**, alocação de salas, **reserva de laboratórios apenas em faixa ociosa**, e a consulta da grade vigente pelos alunos.

## 👤 Autor

| Nome | GitHub |
|------|--------|
| Victor Hugo Wille | [@Victorhugowille](https://github.com/Victorhugowille) |

## 🏗️ Arquitetura Proposta

O sistema adota uma arquitetura **Backend-as-a-Service (BaaS)** com Supabase, separada em dois frontends:

| Aplicação | Público-Alvo | Tecnologia |
|-----------|-------------|------------|
| App Mobile | Alunos | React Native / Expo |
| Portal Web | Pedagogos, Professores e Diretor | React / Next.js |

### Visão Geral das Camadas

```
┌─────────────────────────────────────────────┐
│         Camada de Apresentação              │
│   App Aluno (Mobile)  ·  Web Admin (Web)    │
├─────────────────────────────────────────────┤
│         Camada de Aplicação                 │
│   API REST Supabase  ·  Edge Functions      │
├─────────────────────────────────────────────┤
│      Camada de Domínio e Persistência       │
│   RLS · Triggers · PostgreSQL               │
└─────────────────────────────────────────────┘
```

## 📂 Estrutura do Repositório

```
📁 ProjetoFinal_AASC/
├── 📄 README.md                         ← Você está aqui
├── 📄 analise_inicial_sistema.md        ← Análise do domínio (fatos, fluxo, operações)
└── 📄 trabalho_arquitetura_escola.md    ← Trabalho de arquitetura
```

## 📖 Conteúdo do Documento

O arquivo [`trabalho_arquitetura_escola.md`](trabalho_arquitetura_escola.md) contém todas as seções exigidas pelo enunciado:

1. **Introdução e Descrição do Problema**
2. **Identificação dos Atores** — Aluno, Pedagogo, Professor, Diretor
3. **Módulos do Sistema** — Grade, Salas, Reservas, Usuários
4. **Arquitetura em Camadas** — Apresentação, Aplicação, Domínio, Persistência
5. **Diagramas Obrigatórios (Mermaid)**
   - Diagrama de Ecossistema
   - Diagrama Arquitetural
   - Diagrama de Fluxo (Reserva de laboratório ocioso)
   - Diagrama de Módulos
6. **Reflexão Arquitetural** — Trade-offs e desafios
7. **ADR-001** — Decisão por BaaS (Supabase)
8. **Funcionalidades Inovadoras**
   - Notificações em Tempo Real (Supabase Realtime / WebSockets)
   - Mapa Visual de Ocupação da Escola (SVG interativo)
9. **Cenário de Evolução** — Ensino Híbrido / EAD
10. **Conclusão**

## 🛠️ Tecnologias Mencionadas

> ⚠️ O foco do trabalho **não é a seleção de tecnologias**, mas sim decisões arquiteturais. As tecnologias abaixo são citadas apenas para contextualizar as escolhas.

- **Supabase** — BaaS (PostgreSQL + Auth + Realtime + Storage)
- **React Native / Expo** — App mobile do aluno
- **React / Next.js** — Portal web administrativo
- **Mermaid** — Diagramas integrados ao Markdown

## 📜 Licença

Projeto acadêmico — uso educacional.
