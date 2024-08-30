| Tema            | Decisão técnica               |
| --------------- | ----------------------------- |
| Recurso         | Gerenciamento de notificações |
| Data de criação | 30-08-2024                    |
| Responsável     | @otiodarth                    |
| Data de revisão | 30-08-2024                    |
| Versão          | 01                            |

# Visão Geral

O sistema de notificações na plataforma precisará lidar com diferentes tipos de notificações para diferentes cenários, como:

- Notificações relacionadas a sessões de mentoria: Informar os usuários sobre novas sessões, lembretes, ou atualizações de sessões.
- Notificações de atividades internas: Notificar sobre atividades gerais da plataforma, como novas mensagens, eventos, ou conquistas.
- Notificações gerais da plataforma: Comunicados, alertas administrativos, e outros avisos globais.
- Notificações por diferentes canais: Notificações internas na plataforma, notificações por e-mail, etc.

## Possíveis Soluções

1. Manter uma única tabela de notificações com uma coluna indicando o tipo de notificação
   Descrição: Esta abordagem cria uma tabela de notificações genérica com uma coluna específica para indicar o tipo de notificação, seja ela relacionada a uma sessão de mentoria, a uma atividade interna ou a uma notificação geral.

**Vantagens:**

- Simplicidade na implementação.
- Facilidade de manutenção inicial.

**Desvantagens:**

- Pode se tornar complexa e difícil de escalar com o aumento de tipos e volumes de notificações.
- Necessidade de realizar várias verificações condicionais para filtrar ou processar notificações específicas. 2. Criar tabelas separadas para diferentes tipos de notificações

2. Separar as notificações em tabelas distintas com base no tipo, como uma tabela para notificações de sessões, outra para notificações de atividades internas, e uma terceira para notificações gerais da plataforma.

**Vantagens:**

- Melhor organização e separação de responsabilidades.
- Facilita a manutenção e escalabilidade em longo prazo.
- Menor risco de impacto em performance à medida que o volume de notificações aumenta.

**Desvantagens:**

- Aumenta a complexidade inicial na implementação.
- Pode exigir maior esforço de integração para lidar com notificações de diferentes fontes. 3. Uso de uma tabela de notificações principal com tabelas auxiliares para detalhes específicos

3. Implementar uma tabela principal de notificações relacionadas às sessões de mentoria.

**Vantagens:**

- Balanceia simplicidade e escalabilidade.
- Mantém uma estrutura organizada sem perder a flexibilidade.

**Desvantagens:**

- Introduz alguma complexidade, mas é gerenciável.
- Pode exigir consultas mais complexas para obter detalhes específicos.

## Decisão

Após avaliar as opções e considerando o estágio atual da plataforma (MVP), a abordagem mais adequada será a opção 3:

- Implementar uma tabela principal de notificações de memsagens das sessões. Esta tabela conterá uma flag para indicar se foi lida pelo destinatário.

Justificativa:

Essa abordagem oferece um bom equilíbrio entre simplicidade e escalabilidade. Ela permite que o sistema de notificações seja implementado de maneira eficiente e com capacidade de expansão futura, sem introduzir complexidade desnecessária desde o início.

Caso a aplicação escale, basta criar o mesmo conceito para os diferentes tipos de notificações.
