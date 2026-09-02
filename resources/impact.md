# Impacto — StarSeg (versão para repositório público)

Este arquivo é qualitativo por design. Números exatos de commits, taxa de
falha de deploy e volume de produção ficam em notas privadas, não neste
repositório público — ver `notas-privadas-NAO-COMMITAR.md` (uso local,
nunca commitado).

## Deploy e confiabilidade — Star Condomine

O processo de deploy era manual (SSH direto em produção), sem log de
falhas — problemas só eram percebidos quando um usuário reclamava.
Projetei e implementei um pipeline de CI/CD (GitHub Actions) com backup
automático do banco antes de cada deploy, verificação de migration contra
um dump real de produção antes de aplicar de fato, e smoke test após o
deploy. Isso reduziu de forma significativa a taxa de falhas percebidas
em produção, com todo o processo agora auditável.

## Escala

Plataforma em produção há mais de um ano, atendendo dezenas de clientes
(condomínios) com milhares de usuários finais (moradores). Maior schema
de dados entre os sistemas da empresa.

## Autoria — usar sempre por sistema, nunca agregada

Um agregado único de "% de contribuição" entre os sete sistemas mistura
situações muito diferentes (de participação mínima a autoria integral) e
não deve ser citado como número único em nenhum documento, público ou
privado. Ver `notas-privadas-NAO-COMMITAR.md` para a tabela por sistema.

Qualitativamente, para uso público:
- Autor original e maior contribuidor: star-audio, star-locker,
  star-emergency.
- Um dos maiores contribuidores, entrou em projeto já existente:
  star-condomine, star-tracking.
- Envolvimento pontual/recente, não reivindicar como projeto próprio:
  star-fucando, star-clients.

## Equipe

Núcleo de manutenção contínua hoje: equipe pequena (2 desenvolvedores).
Ao longo da vida dos sistemas, mais pessoas passaram pelos repositórios.

## O que nunca vai neste arquivo nem em nenhum lugar público

- Números exatos de commits/porcentagem por sistema.
- Taxa de falha de deploy, duração de pipeline, volume exato de dados.
- Qualquer achado de segurança (mesmo sem valores) — isso é pauta interna
  com o time da StarSeg, nunca conteúdo público.
- Nomes reais de clientes identificáveis.

## Lacunas que continuam sem resposta

- Se star-clients e star-fucando estão de fato em produção.
- Tamanho real da equipe além dos autores identificados via git.

## Resolvido nesta rodada

- Motivo da parada de atividade no star-emergency: não foi saída ou
  substituição — o sistema resolveu um problema urgente pontual no maior
  cliente da empresa e estabilizou, sem necessidade de mudanças desde
  então. *(relato do usuário)*
