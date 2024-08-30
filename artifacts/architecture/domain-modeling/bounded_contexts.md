| Tema            | Arquitetura |
| --------------- | ----------- |
| Data de criação | 29-08-2024  |
| Responsável     | @otiodarth  |
| Data de revisão | 29-08-2024  |
| Versão          | 01          |

## Visão geral

O objetivo deste documento é definir claramente as áreas de responsabilidade dentro do sistema **Adote um Dev**. Cada contexto delimitado contém um conjunto bem definido de responsabilidades, reduzindo a ambiguidade sobre o que cada parte do sistema deve fazer. A separação dos contextos e suas limitações facilitará a modularização do sistema.

## Mapa de contextos

![Context mapping](/artifacts/images/adoteumdev_context_mapping.png)

## Contextos Limitados

![Bounded Contexts](/artifacts/images/adoteumdev_bounded_context.png)

## Descrição dos contextos

### Mentorship

**Espaço Problema:**

A plataforma precisa facilitar o processo de mentoria entre desenvolvedores e aspirantes, garantindo que as sessões sejam produtivas e atendam às expectativas de ambas as partes.

**Desafio Principal:**

- Coordenar e gerenciar as sessões de mentoria, desde o agendamento até a conclusão, de forma eficiente e satisfatória para mentores e mentorados.

**Problemas Específicos:**

- Dificuldade em encontrar horários comuns para mentores e mentorados.
- Garantir que as sessões sejam devidamente registradas e avaliadas.
- Necessidade de acompanhar o progresso e ajustar o processo de mentoria conforme necessário.

**Espaço Solução:**

- Gerenciar o ciclo completo de mentoria, incluindo o agendamento, gestão e avaliação das sessões, além de fornecer feedback para melhorar continuamente a experiência de mentoria.

**Responsabilidades Principais:**

- Agendamento de Sessões: Coordenar horários entre mentores e mentorados.
- Gestão de Sessões: Monitorar e gerenciar o andamento das sessões.
- Qualidade da Mentoria: Coletar feedback e ajustar as sessões para atender melhor as expectativas.

**Entidades e Objetos de Valor:**

- Sessão de Mentoria: Representa um encontro agendado entre mentor e mentorado.
- Feedback de Sessão: Captura as avaliações e comentários sobre a qualidade da sessão.

**Regras de Negócio:**

- Sessões só podem ser agendadas se ambos os participantes confirmarem a disponibilidade.
- Feedback deve ser fornecido após cada sessão para ajudar na melhoria contínua.

### Match

**Espaço Problema:**

- A plataforma precisa combinar mentores e mentorados de maneira eficiente, garantindo compatibilidade e disponibilidade.

**Desafio Principal:**

- Desenvolver um algoritmo de matchmaking que maximize a compatibilidade e a disponibilidade dos usuários.

**Problemas Específicos:**

- Definir critérios eficazes de compatibilidade entre mentores e mentorados.
- Garantir que os matches realizados levem a sessões de mentoria bem-sucedidas.
- Ajustar o processo de matchmaking com base em feedback contínuo.

**Espaço Solução:**

- Implementar um sistema de matchmaking que considere preferências, experiência e disponibilidade para criar pares de mentoria eficientes.

**Responsabilidades Principais:**

- Critérios de Compatibilidade: Estabelecer e ajustar os critérios para matching.
- Algoritmo de Matchmaking: Realizar a combinação entre mentores e mentorados.
- Ajustes Baseados em Feedback: Adaptar o algoritmo com base nos resultados e feedbacks.

**Entidades e Objetos de Valor:**

- Perfil de Usuário: Contém informações sobre experiência, preferências e disponibilidade.
- Match: Representa a combinação entre um mentor e um mentorado.

**Regras de Negócio:**

- Matches devem priorizar compatibilidade em termos de habilidades e disponibilidade.
- Feedback negativo pode levar a ajustes nos critérios de matchmaking.

## Session

**Espaço Problema**

- Usuários precisam de uma forma eficiente de agendar, gerenciar e conduzir sessões de mentoria.

**Desafio Principal**

- Gerenciar as sessões de mentoria, garantindo que elas sejam organizadas, rastreadas e concluídas com sucesso, mantendo uma boa experiência para mentores e mentorados.

**Problemas Específicos:**

- Garantir que mentores e mentorados possam coordenar horários disponíveis para agendar as sessões.
- Acompanhar o status das sessões (agendadas, em andamento, concluídas) de maneira eficiente.
- Registrar as atividades durante as sessões e coletar feedback de ambos os lados para melhorar as futuras interações.
- Lidar com cancelamentos e reagendamentos de sessões.

**Espaço Solução**

**Responsabilidades Principais:**

- Facilitar a coordenação de horários entre mentores e mentorados, permitindo que ambos concordem com um horário mutuamente conveniente.
- Monitorar o andamento das sessões, registrando seu progresso e conclusão.
- Permitir que os participantes deixem comentários e avaliações após a conclusão de uma sessão.
- Gerenciar de forma eficaz solicitações de cancelamento e reagendamento, garantindo que as regras de política sejam seguidas.

**Entidades e Objetos de Valor:**

- Sessão: Representa um encontro agendado entre mentor e mentorado, contendo informações como data, hora, status (agendada, em andamento, concluída), e feedback.
- Agendamento: Entidade responsável por registrar e gerenciar a data e hora acordada para uma sessão.
- Feedback: Um objeto de valor que armazena as avaliações e comentários dados por mentores e mentorados após a sessão.

**Regras de Negócio:**

- Política de Cancelamento: Definir regras claras para cancelamentos e reagendamentos, como prazos para notificações e possíveis penalidades.
- Status de Sessão: Sessões devem ter estados claramente definidos (agendada, em andamento, concluída, cancelada), e as transições entre esses estados devem seguir regras específicas.
- Feedback Obrigatório: Após a conclusão de cada sessão, feedback deve ser coletado de ambos os participantes para melhorar a experiência e a qualidade das mentorias futuras.

### Communication

**Espaço Problema:**

- Os usuários precisam de um meio eficiente para se comunicarem antes, durante e após as sessões de mentoria.

**Desafio Principal:**

- Facilitar a comunicação fluida e eficiente entre mentores e mentorados, tanto de forma assíncrona quanto em tempo real.

**Problemas Específicos:**

- Garantir que as mensagens sejam entregues e visualizadas de forma eficaz.
- Integrar videoconferências para sessões de mentoria.
- Notificar os usuários sobre novas mensagens e atualizações importantes.

**Espaço Solução:**

- Fornecer um sistema robusto de mensagens, notificações internas e videoconferência para apoiar a comunicação durante o processo de mentoria.

**Responsabilidades Principais:**

- Troca de Mensagens: Facilitar a comunicação assíncrona dentro da plataforma.
- Notificações Internas: Alertar usuários sobre novas mensagens e eventos relevantes.

**Entidades e Objetos de Valor:**

- Mensagem: Representa uma comunicação textual entre usuários.
- Notificação Interna: Alerta o usuário sobre uma nova mensagem ou atualização.

**Regras de Negócio:**

- Notificações internas devem ser geradas para cada nova mensagem ou evento relevante.

### Engagement

Espaço Problema:

- A plataforma precisa incentivar os usuários a participar ativamente das sessões de mentoria e contribuir para a comunidade.

**Desafio Principal:**

- Manter os usuários motivados e engajados através de recompensas, desafios e acompanhamento do progresso.

**Problemas Específicos:**

- Dificuldade em manter usuários consistentemente ativos e envolvidos.
- Necessidade de recompensar comportamentos positivos e progressos.
- Garantir que o sistema de engajamento seja justo e estimulante.

Espaço Solução:

- Implementar um sistema de gamificação que recompense os usuários por participação, progresso e sucesso nas interações de mentoria.

**Responsabilidades Principais:**

- Sistema de Pontos e Badges: Recompensar os usuários por atividades e conquistas.
- Desafios e Metas: Criar desafios para incentivar o progresso.
- Painel de Progresso: Exibir o progresso e as conquistas dos usuários.

**Entidades e Objetos de Valor:**

- Ponto: Unidade de recompensa por atividades realizadas.
- Badge: Distinção concedida por alcançar marcos importantes.
- Desafio: Tarefa específica que motiva o usuário a completar ações.

**Regras de Negócio:**

- Pontos e badges devem ser atribuídos com base em regras claras e transparentes.
- Desafios devem ser atualizados regularmente para manter o interesse dos usuários.

### Evaluation

**Espaço Problema:**

- É necessário coletar feedback e avaliações dos usuários para garantir que a plataforma e as sessões de mentoria estão atendendo às expectativas.

**Desafio Principal:**

- Desenvolver um sistema de avaliação que capture feedback de forma precisa e útil, permitindo ajustes e melhorias contínuas.

**Problemas Específicos:**

- Garantir que o feedback seja objetivo e relevante.
- Necessidade de ajustar o processo de mentoria com base nas avaliações recebidas.
- Dificuldade em interpretar e aplicar feedback de forma eficaz.

**Espaço Solução:**

- Criar um sistema de avaliação robusto que permita a coleta, análise e aplicação de feedback para melhorar a experiência geral na plataforma.

**Responsabilidades Principais:**

- Coleta de Feedback: Gerenciar o processo de coleta de avaliações dos usuários.
- Avaliações: Permitir que os usuários classifiquem sessões, mentores e matches.
- Relatórios e Análise: Gerar insights e recomendações com base nas avaliações coletadas.

**Entidades e Objetos de Valor:**

- Feedback: Dados coletados dos usuários sobre suas experiências.
- Relatório de Avaliação: Documento que resume e analisa os feedbacks recebidos.

**Regras de Negócio:**

- Feedback deve ser coletado após cada sessão e ao longo do tempo para acompanhamento contínuo.
- Avaliações devem influenciar ajustes no processo de mentoria e matchmaking.

### Apointment

**Espaço Problema:**

- Usuários precisam de uma forma eficiente de agendar sessões de mentoria que se ajustem às suas disponibilidades.

**Desafio Principal:**

- Criar um sistema de agendamento que consiga coordenar os horários de mentores e mentorados de forma eficiente e evitar conflitos de agenda.

**Problemas Específicos:**

- Conflitos de agenda entre mentores e mentorados.
- Necessidade de notificações para lembrar os usuários sobre sessões agendadas.
- Garantir flexibilidade e facilidade no processo de agendamento.

**Espaço Solução:**

- Implementar uma ferramenta de agendamento que permita a fácil coordenação de horários e inclua notificações externas para garantir que os usuários estejam cientes de suas sessões.

**Responsabilidades Principais:**

- Coordenação de Horários: Facilitar o encontro de horários disponíveis para ambos.
- Gestão de Conflitos: Prevenir e resolver conflitos de agenda.
- Notificações Externas: Enviar lembretes de sessões via e-mail ou SMS.

**Entidades e Objetos de Valor:**

- Calendário de Agendamento: Ferramenta que mostra a disponibilidade dos usuários.
- Notificação Externa: Lembrete enviado para fora da plataforma, como por e-mail.

**Regras de Negócio:**

- Sessões só podem ser agendadas se houver confirmação de ambas as partes.
- Notificações devem ser enviadas com antecedência suficiente para garantir que os usuários se lembrem das sessões.

### Contextos e suas relações

#### Contexto principal

<table>
  <tbody>
    <tr>
      <td rowspan="4">Mentorship (core)</td>
      <td rowspan="4">Coordenar e gerenciar as sessões de mentoria, desde o agendamento até a conclusão, de forma eficiente e satisfatória para mentores e mentorados.</td>
      <td>Match</td>
      <td>Recebe os pares de mentores e mentorados para iniciar o processo de mentoria.</td>
    </tr>
    <tr>
      <td>Communication</td>
      <td>Facilita a troca de mensagens durante e após as sessões.</td>
    </tr>
    <tr>
      <td>Engagement</td>
      <td>Atribui recompensas com base na participação nas sessões de mentoria.</td>
    </tr>
    <tr>
      <td>Evaluation</td>
      <td>Coleta feedback detalhado sobre as sessões para melhorar a qualidade da mentoria.</td>
    </tr>
  </tbody>
</table>

#### Contextos de Suporte

<table>
  <tbody>
    <tr>
      <td rowspan="4">Match</td>
      <td rowspan="4">Desenvolver um algoritmo de matchmaking que maximize a compatibilidade e a disponibilidade dos usuários.</td>
      <td>Mentorship</td>
      <td>Fornece os matches para agendamento e gestão de sessões.</td>
    </tr>
    <tr>
      <td>Communication</td>
      <td>Facilita o contato inicial entre os pares após o match.</td>
    </tr>
    <tr>
      <td>Engagement</td>
      <td>Ajusta o sistema de recompensas com base no sucesso dos matches.</td>
    </tr>
    <tr>
      <td>Evaluation</td>
      <td>Recebe feedback sobre a eficácia dos matches para ajuste contínuo.</td>
    </tr>
    <tr>
      <td rowspan="4">Session</td>
      <td rowspan="4">Desenvolver e aprimorar funcionalidades para a gestão completa de sessões de mentoria, desde o agendamento até o registro e acompanhamento.</td>
      <td>Mentorship</td>
      <td>Sessões fazem parte do processo de mentoria e estão diretamente ligadas às interações e avaliações entre mentores e mentorados.</td>
    </tr>
    <tr>
      <td>Appointment</td>
      <td>Interage com o sistema de agendamento para coordenar horários e disponibilidades.</td>
    </tr>
    <tr>
      <td>Engagement</td>
      <td>O sucesso e frequência das sessões podem impactar o sistema de recompensas e reconhecimento dos usuários.</td>
    </tr>
    <tr>
      <td>Communication</td>
      <td>Facilita o contato entre mentores e mentorados antes, durante, e após as sessões.</td>
    </tr>
     <tr>
      <td>Evaluation</td>
      <td>Permite que os usuários avaliem a sessão de mentoria como parte do feedback.</td>
    </tr>
    <tr>
      <td rowspan="4">Communication</td>
      <td rowspan="4">Facilitar a comunicação fluida e eficiente entre mentores e mentorados.</td>
      <td>Mentorship</td>
      <td>Fornece ferramentas de comunicação para as sessões.</td>
    </tr>
    <tr>
      <td>Match</td>
      <td>Facilita a comunicação inicial após a combinação.</td>
    </tr>
    <tr>
      <td>Engagement</td>
      <td>Pode usar a comunicação para incentivar interações significativas.</td>
    </tr>
    <tr>
      <td>Evaluation</td>
      <td>Permite que os usuários avaliem a comunicação como parte do feedback.</td>
    </tr>
    <tr>
      <td rowspan="4">Engagement</td>
      <td rowspan="4">Manter os usuários motivados e engajados através de recompensas, desafios e acompanhamento do progresso.</td>
      <td>Mentorship</td>
      <td>Recompensa os usuários com base na participação em sessões.</td>
    </tr>
    <tr>
      <td>Match</td>
      <td>Ajusta recompensas com base no sucesso dos matches.</td>
    </tr>
    <tr>
      <td>Communication</td>
      <td>Pode recompensar interações úteis ou significativas.</td>
    </tr>
    <tr>
      <td>Evaluation</td>
      <td>Ajusta o sistema de engajamento com base no feedback.</td>
    </tr>
    <tr>
      <td rowspan="4">Evaluation</td>
      <td rowspan="4">Desenvolver um sistema de avaliação que capture feedback de forma precisa e útil, permitindo ajustes e melhorias contínuas.</td>
      <td>Mentorship</td>
      <td>Coleta e analisa feedback sobre as sessões.</td>
    </tr>
    <tr>
      <td>Match</td>
      <td>Avalia a eficácia dos matches com base no feedback recebido.</td>
    </tr>
    <tr>
      <td>Communication</td>
      <td>Inclui a avaliação da qualidade da comunicação.</td>
    </tr>
    <tr>
      <td>Engagement</td>
      <td>Ajusta desafios e recompensas com base nas avaliações recebidas.</td>
    </tr>
    <tr>
      <td rowspan="4">Appointment</td>
      <td rowspan="4">Criar um sistema de agendamento que consiga coordenar os horários de mentores e mentorados de forma eficiente e evitar conflitos de agenda.</td>
      <td>Mentorship</td>
      <td>Gerencia o processo de agendamento dentro do contexto da mentoria.</td>
    </tr>
    <tr>
      <td>Communication</td>
      <td>Suporte para enviar notificações relacionadas ao agendamento.</td>
    </tr>
    <tr>
      <td>Engagement</td>
      <td>Pode incluir recompensas por sessões agendadas e completadas com sucesso.</td>
    </tr>
    <tr>
      <td>Evaluation</td>
      <td>Coleta feedback sobre o processo de agendamento para melhorias.</td>
    </tr>
  </tbody>
</table>

### Changelog

| Data       | Descrição            |
| ---------- | -------------------- |
| 29-08-2024 | Criação do documento |
