# 🧠 LinkedIn Skill — Victor Lis Bronzo

Skill de contexto profissional para agentes de IA (Antigravity/Gemini).

## O que é

Este repositório é uma **skill** que expõe o perfil profissional completo de Victor Lis Bronzo, extraído e curado a partir do LinkedIn Data Export. Outros agentes podem consumi-la como contexto para gerar CVs, preparar entrevistas, escrever propostas comerciais, pitches e qualquer conteúdo profissional.

## Estrutura

```text
├── SKILL.md                    ← Ponto de entrada da skill (frontmatter YAML)
├── resources/                  ← Dados profissionais detalhados
│   ├── profile.md              ← Perfil, headline, resumo, links
│   ├── experience.md           ← Experiência profissional
│   ├── education.md            ← Formação acadêmica
│   ├── skills-and-endorsements.md ← 69 competências + endorsements
│   ├── certifications.md       ← 91 certificações
│   ├── projects.md             ← 23 projetos em destaque
│   ├── recommendations.md      ← Recomendações recebidas e dadas
│   └── learning.md             ← Cursos do LinkedIn Learning
├── references/                 ← Progressive disclosure
│   └── full-summary.md         ← Resumo executivo compilado
└── README.md                   ← Este arquivo
```

## Como usar

### Como skill global (todas as conversas)

Copie ou symlinke este repositório para:

```text
~/.gemini/config/skills/victor-lis-bronzo-profile/
```

### Como skill de projeto

Copie ou symlinke para:

```text
.agents/skills/victor-lis-bronzo-profile/
```

### Referenciando via `skills.json`

```json
{
  "skills": [
    {
      "name": "victor-lis-bronzo-profile",
      "path": "/caminho/para/este/repo"
    }
  ]
}
```

## Dados fonte

Os dados foram extraídos do **LinkedIn Data Export** (agosto de 2026) e curados em Markdown estruturado. Os arquivos CSV originais **não estão incluídos** no repositório por conterem dados pessoais sensíveis.

## Licença

Repositório privado — uso pessoal.
