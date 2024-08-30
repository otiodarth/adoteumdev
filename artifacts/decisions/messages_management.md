| Tema            | Decisão técnica            |
| --------------- | -------------------------- |
| Recurso         | Gerenciamento de mensagens |
| Data de criação | 30-08-2024                 |
| Responsável     | @otiodarth                 |
| Data de revisão | 30-08-2024                 |
| Versão          | 01                         |

# Visão Geral

A plataforma "Adote um Dev" exige um sistema de mensagens para facilitar a comunicação entre diferentes tipos de usuários, como:

- Mensagens entre mentores e mentorados durante as sessões de mentoria.
- Mensagens gerais da plataforma (anúncios, atualizações).
- Mensagens diretas entre usuários (que podem ser introduzidas no futuro).

## Possíveis Soluções

1. Tabela Única de Mensagens
   Criar uma única tabela de mensagens com uma coluna adicional para indicar o tipo de canal utilizado (e.g., sessões de mentoria, mensagens gerais, etc.).

**Vantagens:**

- Simplicidade: Menor complexidade inicial, ideal para um MVP.
- Foco no Core: Permite o desenvolvimento rápido das funcionalidades principais, como a comunicação em sessões de mentoria.

**Desvantagens:**

- Escalabilidade: Pode exigir refatoração significativa ao adicionar novos canais de comunicação.
- Manutenção: Dificuldade em manter a tabela organizada e eficiente conforme a complexidade aumenta.

2. Tabelas Separadas por Canal

Criar tabelas distintas para cada tipo de mensagem (e.g., MensagensMentoria, MensagensGerais, MensagensDiretas).

**Vantagens:**

- Responsabilidades Claras: Facilita a manutenção e a escalabilidade, com cada tabela gerenciando um canal específico.
- Otimização: Melhor performance em consultas específicas a um canal.

**Desvantagens:**

- Complexidade Inicial: Maior complexidade no desenvolvimento inicial, não ideal para um MVP.
- Desenvolvimento Mais Lento: Demanda mais tempo e recursos para implementar.

## Decisão

Para o MVP da plataforma "Adote um Dev", será adotada a seguinte abordagem:

Tabela Única Focada em Sessões de Mentoria: Iniciar com uma tabela única dedicada a mensagens trocadas durante sessões de mentoria. Isso permitirá um desenvolvimento mais ágil, concentrando-se no core da plataforma.

Plano de Refatoração Futuro: Um plano será desenvolvido para, no futuro, separar as mensagens por canal à medida que a aplicação escalar. Isso incluirá a criação de tabelas adicionais e migração dos dados conforme novos tipos de mensagens sejam introduzidos.
