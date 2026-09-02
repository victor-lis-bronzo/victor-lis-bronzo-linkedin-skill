# StarSeg — Desenvolvedor Full-Stack (mar/2025 – atual)

Contexto: empresa de tecnologia para gestão de condomínios e portarias.
Mantém uma plataforma de 7 sistemas interligados: controle de acesso
condominial (Star Condomine, hub central), lockers inteligentes para
encomendas (Star Locker), botões de emergência IoT (Star Emergency),
triagem de chamadas por voz com IA (Star Audio), rastreamento veicular
(Star Tracking), gestão de clientes externos (Star Clients) e gestão
administrativa interna (Star Fucando). Time de 2 desenvolvedores na
manutenção contínua hoje.

Nota de uso: este bloco é material bruto para seleção por vaga, não um
currículo pronto. Os sistemas abaixo são repositórios privados da empresa
(`github.com/starseg/...`) — não têm link público, então não entram na
seção "Projetos" do template de CV (que exige link clicável). Entram como
bullets desta experiência.

## Star Condomine (sistema principal, mais de 1 ano de atuação)

- Um dos maiores contribuidores individuais do sistema, entre uma equipe de
  vários desenvolvedores ao longo de mais de um ano. Entrou em um projeto já
  existente — não é autor do commit inicial.
- Construiu, ponta a ponta, a integração com hardware de controle de acesso
  Control iD: schema de dados, controller HTTP, fila de comandos com
  retry e cache em memória, tela de sincronização e administração dos
  dispositivos.
- Construiu o módulo de registro e resolução de problemas de portaria
  (falta de energia, internet, portão com defeito), com geração de
  relatório em PDF e CSV.
- Projetou e implementou o pipeline de CI/CD de deploy (GitHub Actions):
  backup do banco antes de cada deploy, dry-run de migration contra dump
  real de produção, deploy via SSH com restart gerenciado por PM2, smoke
  test. Reduziu de forma significativa a taxa de falha de deploy em
  relação ao processo manual anterior. *(números exatos: ver notas
  privadas — não publicar métrica operacional da empresa em repositório
  público)*

## Star Audio

- Autor do commit inicial e maior contribuidor do sistema.
- Serviço de triagem de visitantes por voz: recebe ligação SIP via central
  Asterisk, conduz a triagem com a API Realtime da OpenAI (streaming de
  áudio bidirecional, 50 frames por segundo), e transfere automaticamente
  para atendente humano via protocolo AMI do Asterisk (implementado sem
  biblioteca de terceiros) quando a triagem não se completa.
- Evidência de execução real em produção (logs de chamada e gravações
  geradas pelo próprio sistema).
- Testes automatizados com pytest.

## Star Locker

- Autor do commit inicial e maior contribuidor do sistema.
- Sistema de armários inteligentes para recebimento de encomendas: firmware
  em C para ESP32 (abertura de porta por motor de passo), comunicação MQTT
  com o backend, controle de presença dos controladores via Redis (TTL de
  15s), notificação ao morador por WhatsApp com link de abertura
  autenticado.
- Escreveu a camada de regra de negócio de entregas e a integração deste
  sistema com o Star Condomine (consulta de moradores/portarias via API).

## Star Emergency

- Contexto do problema *(relato do usuário, não verificável no código)*:
  o maior cliente da empresa teve falhas com botões de emergência pelo
  método tradicional, que não era viável para o caso; o usuário propôs e
  construiu uma solução alternativa com dispositivos IoT.
- Autor do commit inicial e maior contribuidor do sistema. Atividade de
  commits cessa em maio de 2026 — dado do git é neutro: mostra quando
  parou, não o motivo. Motivo relatado: o sistema estabilizou após a
  entrega e não precisou de mudanças desde então; não é abandono, é
  entrega concluída com baixa manutenção subsequente.
- Backend de alertas de emergência acionados por botão físico IoT (ESP32):
  regra de negócio de criação e leitura de alertas, aplicativo desktop em
  Electron para exibição prioritária do alerta (janela sempre visível,
  inicialização automática com o Windows), integração MQTT com o firmware.
- Boa história para entrevista comportamental (problema urgente em cliente
  estratégico, solução proposta e entregue pelo próprio candidato) — mas
  evitar nomear o cliente real se for identificável publicamente.

## Star Tracking

- Entrou em um projeto já existente — não é autor do commit inicial, mas
  tornou-se um dos maiores contribuidores.
- Construiu o módulo de Ordens de Serviço (criação, filtros combinados,
  detalhe técnico com acesso protegido por OTP, exportação em PDF/Excel/
  DOCX) e o módulo de problemas de comunicação de rastreadores veiculares.

## Star Fucando e Star Clients — não usar como projeto próprio

- Star Fucando: envolvimento pontual e recente, não é autor do sistema.
- Star Clients: um único ajuste de paleta de cor visual. Não reivindicar
  como trabalho próprio em nenhum contexto.

---

## Freelance — Desenvolvedor Freelancer
**Período:** Setembro de 2024 – Presente (atual)
**Localização:** Remoto
