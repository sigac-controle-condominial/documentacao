# UC-023 – Solicitar Reserva de Área Comum

## Objetivo
Permitir que o morador solicite a reserva de uma área comum, respeitando disponibilidade, regras de uso e critérios de aprovação do condomínio.

## Atores
- Morador

## Interessados e Interesses
- Morador: reservar a área comum desejada com transparência sobre disponibilidade e regras.
- Gestor do Condomínio: garantir uso ordenado dos espaços e cumprimento das políticas internas.
- Demais moradores: evitar conflitos de agenda e assegurar uso justo das áreas comuns.
- Sistema: controlar disponibilidade, registrar solicitações e suportar o processo de aprovação.

## Gatilho
O caso de uso é iniciado quando o morador deseja utilizar uma área comum em data e horário específicos.

## Pré-condições
- Usuário autenticado.
- Morador vinculado a uma unidade habitacional ativa.
- Existem áreas comuns configuradas para reserva.
- O morador possui permissão para solicitar reservas.

## Pós-condições
### Em caso de sucesso
- A solicitação de reserva é registrada com status adequado para análise ou confirmação automática, conforme a regra do condomínio.
- A área comum permanece bloqueada para reservas conflitantes, quando a política assim exigir.
- O solicitante recebe protocolo ou confirmação da solicitação.

### Em caso de falha
- Nenhuma reserva é criada quando houver conflito, restrição ou inconsistência nos dados informados.
- A disponibilidade existente é preservada sem bloqueios indevidos.

## Fluxo Principal
1. O morador acessa a funcionalidade de solicitação de reserva.
2. O sistema apresenta as áreas comuns disponíveis e suas regras de utilização.
3. O morador seleciona a área, a data, o horário e informa os dados complementares exigidos.
4. O sistema valida disponibilidade, antecedência mínima, duração máxima e demais regras aplicáveis.
5. O morador confirma a solicitação.
6. O sistema registra a solicitação, define o status inicial e apresenta a confirmação ao morador.

## Fluxos Alternativos
### FA-01 – Área com aprovação automática
1. O sistema identifica que a área escolhida dispensa aprovação manual.
2. O sistema confirma a reserva imediatamente.
3. O morador recebe a confirmação com os detalhes da utilização.

### FA-02 – Conflito de horário
1. O sistema informa que já existe reserva ou bloqueio no período desejado.
2. O morador ajusta a data, o horário ou a área comum.
3. O fluxo retorna ao passo 2 do fluxo principal.

### FA-03 – Solicitação cancelada pelo morador
1. Antes da confirmação final, o morador desiste da solicitação.
2. O sistema encerra o caso de uso sem registrar a reserva.

## Fluxos de Exceção
### FE-01 – Falha ao registrar a solicitação
1. O sistema não cria a solicitação de reserva.
2. O erro técnico é registrado para análise.
3. O morador é informado de que a operação não foi concluída.

## Regras de Negócio
- Uma unidade habitacional só pode solicitar reservas dentro dos limites de quantidade e frequência definidos pelo condomínio.
- Reservas não podem conflitar com indisponibilidades, manutenções ou eventos previamente cadastrados.
- Quando houver necessidade de aprovação, a utilização da área depende da decisão do gestor.

## Requisitos Especiais
- A agenda deve ser apresentada de forma visual para facilitar a identificação de horários disponíveis.
- O sistema deve informar claramente as regras da área comum antes da confirmação da solicitação.
- O protocolo da solicitação deve poder ser consultado posteriormente pelo morador.

## Requisitos Relacionados
- UC-015 – Manter Áreas Comuns
- UC-016 – Aprovar Reservas
