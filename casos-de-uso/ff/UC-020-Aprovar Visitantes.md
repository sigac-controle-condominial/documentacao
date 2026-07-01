# UC-020 – Aprovar Visitantes

## Objetivo
Permitir que o morador aprove ou rejeite solicitações de acesso de visitantes vinculados à sua unidade habitacional.

## Atores
- Morador

## Interessados e Interesses
- Morador: decidir sobre o acesso de visitantes de forma segura e rápida.
- Visitante: obter retorno claro sobre a autorização de entrada.
- Portaria: receber a decisão do morador para proceder com o atendimento.
- Sistema: registrar a decisão e manter histórico da autorização.

## Gatilho
O caso de uso é iniciado quando existe visitante pendente de confirmação pelo morador.

## Pré-condições
- Usuário autenticado.
- Morador possui permissão para aprovar visitantes vinculados à sua unidade habitacional.
- Existe visitante ou solicitação de acesso pendente de aprovação.

## Pós-condições
### Em caso de sucesso
- O visitante é marcado como aprovado ou rejeitado conforme a decisão do morador.
- A decisão fica visível para a portaria no momento do atendimento.
- O histórico da decisão é registrado em auditoria.

### Em caso de falha
- Nenhuma aprovação é consolidada sem vínculo válido com a unidade habitacional.
- O visitante permanece com o status anterior até a conclusão correta da análise.

## Fluxo Principal
1. O morador acessa a lista de visitantes pendentes.
2. O sistema apresenta os dados do visitante, a data prevista e as observações registradas.
3. O morador analisa as informações e decide aprovar ou rejeitar o acesso.
4. Quando necessário, o morador informa justificativa ou observação complementar.
5. O sistema registra a decisão e atualiza o status do visitante.
6. O sistema confirma a operação e disponibiliza a decisão para a portaria.

## Fluxos Alternativos
### FA-01 – Aprovação antecipada
1. O morador aprova previamente o visitante antes de sua chegada.
2. O sistema mantém a autorização disponível para consulta da portaria dentro da vigência definida.

### FA-02 – Rejeição por falta de reconhecimento
1. O morador informa que não reconhece ou não autoriza o visitante.
2. O sistema registra a rejeição e impede o uso da autorização.

## Fluxos de Exceção
### FE-01 – Falha ao registrar a decisão
1. O sistema não altera o status do visitante.
2. O erro técnico é registrado.
3. O morador é informado para tentar novamente posteriormente.

## Regras de Negócio
- A aprovação do visitante deve respeitar a vigência definida para o acesso.
- Visitantes rejeitados ou com autorização expirada não podem ser liberados pela portaria.
- A portaria deve visualizar o status mais recente aprovado pelo morador.

## Requisitos Especiais
- A funcionalidade deve ser adequada para uso rápido em dispositivos móveis, quando aplicável.
- As notificações de pendência devem destacar nome do visitante e janela de acesso.
- O histórico deve indicar data, hora e responsável pela decisão.

## Requisitos Relacionados
- UC-019 – Manter Visitantes
- UC-021 – Gerenciar Autorizações Permanentes
- UC-029 – Registrar Entrada e Saída de Visitantes
