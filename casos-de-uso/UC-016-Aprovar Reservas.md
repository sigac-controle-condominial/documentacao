# UC-016 – Aprovar Reservas

## Objetivo
Permitir que solicitações de reserva sejam aprovadas ou reprovadas conforme as regras do condomínio.

## Atores
- Gestor do Condomínio

## Interessados e Interesses
- Gestor do Condomínio: decidir sobre solicitações de reserva com base nas regras do condomínio.
- Solicitante relacionado: obter retorno claro e tempestivo sobre o status de solicitação de reserva.
- Sistema: aplicar as regras de negócio, registrar a decisão e notificar os envolvidos.

## Gatilho
O caso de uso é iniciado quando existe solicitação de reserva pendente de decisão por parte do ator.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para aprovar solicitações de reserva.
- Existem reservas pendentes associadas a áreas comuns ativas.
- Existe ao menos um solicitação de reserva pendente de análise.

## Pós-condições
### Em caso de sucesso
- Solicitações aprovadas ficam aptas para utilização da área comum no período reservado.
- Solicitações reprovadas permanecem registradas com a justificativa correspondente.
- A decisão é registrada em auditoria com responsável, data, hora e justificativa quando informada.

### Em caso de falha
- Nenhuma decisão é confirmada sem atendimento dos critérios de aprovação.
- O item permanece com o status anterior até a conclusão válida da análise.

## Fluxo Principal
1. O ator acessa a fila de solicitações de reserva pendentes.
2. O sistema apresenta os detalhes necessários para análise de cada solicitação de reserva.
3. O ator avalia a disponibilidade da área, as regras de uso, a situação do solicitante e eventuais conflitos de agenda.
4. O ator escolhe aprovar ou reprovar e, quando aplicável, informa uma justificativa.
5. O sistema valida a decisão, atualiza o status do item e registra auditoria.
6. O sistema notifica o solicitante e apresenta a confirmação da operação.

## Fluxos Alternativos
### FA-01 – Item fora do prazo ou conflito de agenda
1. O sistema identifica conflito ou impedimento de aprovação.
2. O ator analisa a situação e registra a reprovação ou ajusta a decisão conforme a regra aplicável.
3. O sistema comunica o resultado ao solicitante.

### FA-02 – Solicitação cancelada antes da análise
1. O sistema informa que o item não está mais pendente.
2. O caso de uso é encerrado sem nova decisão.

## Fluxos de Exceção
### FE-01 – Falha ao registrar a decisão
1. O sistema não altera o status final do item.
2. O erro é registrado para análise técnica.
3. O ator é informado para tentar novamente posteriormente.

## Regras de Negócio
- A aprovação deve observar a disponibilidade da área, as regras de uso, a situação do solicitante e eventuais conflitos de agenda.
- O histórico de análise deve permanecer disponível para auditoria.
- Uma solicitação já decidida não pode retornar ao estado pendente sem ação administrativa autorizada.

## Requisitos Especiais
- A tela de análise deve exibir todas as informações necessárias para a decisão sem exigir navegação excessiva.
- As notificações ao solicitante devem ocorrer imediatamente após a decisão.
- A justificativa de reprovação deve ser apresentada de forma clara para reduzir retrabalho.

## Requisitos Relacionados
- UC-015 – Manter Áreas Comuns
- UC-023 – Solicitar Reserva de Área Comum
