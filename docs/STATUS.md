# Status de implementação — Bemmo

Este documento resume o estado público do projeto sem expor o código-fonte privado.

Atualizado em 29/09/2026 após o rebrand Bemmo e a integração do fluxo profissional de agendamentos.

## Integrado de ponta a ponta

### Frontend + Backend

- autenticação e sessão;
- recuperação de senha e verificação de e-mail no produto, ainda sem provedor externo de entrega;
- perfil profissional privado e página pública;
- serviços profissionais;
- disponibilidade semanal e exceções;
- consulta pública de horários reserváveis;
- booking público persistido;
- gestão profissional de agendamentos;
- transições de lifecycle como confirmação, cancelamento, conclusão e não comparecimento.

## Backend implementado / frontend ainda pendente

- reagendamento;
- CRM de clientes;
- histórico e resumo do cliente;
- financeiro;
- avaliações;
- moderação administrativa de avaliações.

## Parcial / demonstrativo

- marketplace público e busca sobre catálogo;
- métricas da home;
- vouchers;
- páginas e fluxos que ainda não consomem seus módulos backend correspondentes.

## Planejado

- pagamentos e assinaturas;
- vouchers comerciais transacionais;
- notificações;
- uploads;
- provedor transacional externo de e-mail;
- observabilidade de produção;
- ambiente público de beta/produção.

## Qualidade

No fechamento atual do rebrand Bemmo, o projeto principal registra:

- **139 testes frontend passando**;
- **219 testes backend passando**;
- build Vite de produção aprovado;
- schema Prisma validado;
- integrações selecionadas com Chromium e PostgreSQL/Neon.

## Infraestrutura

- PostgreSQL de desenvolvimento em Neon;
- Prisma para modelagem e acesso ao banco;
- health e readiness na API;
- configuração Render estática existente, ainda sem deploy público desta etapa;
- domínio **bemmo.com.br** registrado, ainda sem DNS/deploy público concluído.

## Segurança e arquitetura

Entre as decisões já incorporadas estão:

- Argon2id para senhas;
- access token JWT de curta duração;
- refresh token opaco em cookie `HttpOnly`;
- rotação e revogação de sessão;
- CORS explícito e validação de origem;
- rate limiting;
- logs estruturados com redaction;
- transações e locks em operações concorrentes;
- dados pessoais fora de URLs nos fluxos de booking.

## Princípio de documentação

O projeto diferencia explicitamente:

- **interface existente**;
- **modelagem de banco existente**;
- **backend implementado**;
- **integração full stack operacional**;
- **ambiente efetivamente em produção**.

Uma tabela no banco, endpoint ou tela isolada não é apresentada como funcionalidade concluída quando o fluxo completo ainda não está integrado.
