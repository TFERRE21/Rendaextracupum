# Renda Automática AI

Plataforma independente para administrar vendas de produtos digitais, afiliados, loja e assinaturas, com automações de divulgação e entrega digital.

> **Status:** planejamento técnico inicial. Este repositório ainda não representa um sistema pronto para produção. Integrações, credenciais, pagamentos e publicação automática precisam ser implementados, configurados e testados.

## Objetivo

Construir uma aplicação que possa funcionar continuamente, com operação controlada e rastreável, reduzindo tarefas manuais sem prometer renda garantida nem executar ações financeiras sem autorização.

## Escopo do produto

- Cadastro e autenticação segura de usuários.
- Catálogo de produtos digitais, ofertas e links de afiliados.
- Pedidos, assinaturas e histórico de transações.
- Integrações de pagamento com **Asaas** e **Stripe**, confirmando pagamentos somente por webhooks verificados.
- Entrega automática após confirmação válida do pagamento.
- Filas e agendamentos para tarefas de segundo plano.
- Painel administrativo com vendas, custos, receita, falhas e histórico de automações.
- Divulgação programada por canais oficiais: blog/Google, Instagram/Facebook via Meta, TikTok e YouTube Shorts, respeitando permissões e políticas de cada plataforma.
- Modos de operação: **teste**, **supervisionado** e **automático**, com limites de gastos, registros de auditoria e possibilidade de pausar automações.
- Proteção de dados e controles compatíveis com a LGPD.

## Arquitetura inicial

- **Aplicação/API:** a definir durante a implementação, priorizando uma estrutura simples de manter por uma única pessoa.
- **Banco de dados:** PostgreSQL.
- **Filas/cache:** Redis.
- **Execução local e implantação:** Docker e Docker Compose.
- **Testes:** testes automatizados para autenticação, catálogo, pedidos, webhooks e regras de automação.
- **Segredos:** variáveis de ambiente; nunca incluir tokens, senhas, chaves privadas ou arquivos `.env` no Git.

## Ordem de implementação

1. Estrutura do projeto, configuração Docker e documentação de ambiente.
2. Banco de dados, migrações e autenticação.
3. Catálogo e administração de produtos.
4. Pedidos, estados de pagamento e testes.
5. Webhooks seguros de Asaas e Stripe e entrega digital idempotente.
6. Filas, agendamentos, logs, limites e painel financeiro.
7. Integrações de divulgação com APIs oficiais, começando pelo Instagram/Meta.
8. Monitoramento, segurança, LGPD e preparação para produção.

## Regras de segurança e confiabilidade

- Nunca confiar apenas no redirecionamento do navegador para marcar um pedido como pago.
- Validar assinatura/autenticidade dos webhooks e impedir processamento duplicado.
- Não publicar conteúdo nem gastar dinheiro sem as permissões e configurações necessárias.
- Não armazenar dados de cartão diretamente.
- Usar limites configuráveis, trilha de auditoria e pausa de emergência para automações.
- Não declarar integrações como concluídas até que tenham credenciais válidas e testes comprovados.

## Desenvolvimento local

Os comandos de instalação e execução serão documentados quando a estrutura executável for adicionada. Não há, neste momento, garantia de build, testes ou implantação funcional.

## Configuração

Use um arquivo local `.env` baseado em um futuro `.env.example`. Nunca envie credenciais reais ao GitHub ou ao chat. Se alguma chave tiver sido publicada por engano, revogue-a e gere outra.

## Licença

A definir.
