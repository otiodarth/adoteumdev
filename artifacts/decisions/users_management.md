| Tema            | Decisão técnica           |
| --------------- | ------------------------- |
| Recurso         | Gerenciamento de usuários |
| Data de criação | 30-08-2024                |
| Responsável     | @otiodarth                |
| Data de revisão | 30-08-2024                |
| Versão          | 01                        |

# Visão geral

Existem três papéis principais para os usuários da plataforma: mentores, mentorados e admin. Logo, surge a questão:
Como gerenciar os perfis de usuários de forma simplificada por se tratar de um MVP, mas ao mesmo tempo pensando em escalabilidade?

## Possíveis soluções

As duas principais abordagens são:

1. Manter uma tabela apenas para usuários, com uma coluna indicando o tipo de usuário. É definitivamente a abordagem mais simples. Caso implementada, em caso de escala da aplicação, será necessário separar os tipos de usuários em tabelas diferentes (caso abaixo).

**Vantagem**

- Maior simplicidade

**Desvantagem**

- Retrabalho em caso de escala da aplicação

2. Criar uma tabela principal para usuarios, e tabelas secundárias para mentores e mentorados, contendo a referência do usuário. Esta abordagem possui maior complexidade devido a configurações iniciais de relacionamentos entre as tabelas.

**Vantagem**

- Reduz o retrabalho em caso de escala da aplicação

**Desvantagem**

- Adiciona complexidade

## Decisão

Visto que se trata de um MVP, será adotada a abordagem mais simplificada, a fim de ganhar tempo no desenvolvimento.
Porém, deve ser montada uma estratégia clara de transição para uma arquitetura mais escalável em caso de crescimento da plataforma.
Além disso, a implementação de uma arquitetura modular desde o início pode contribuir para facilitar a refatoração no futuro.
