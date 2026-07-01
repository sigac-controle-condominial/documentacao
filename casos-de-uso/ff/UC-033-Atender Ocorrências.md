# UC-033 – Atender Ocorrências

## Objetivo
Permitir que o profissional responsável inicie o atendimento de uma ocorrência atribuída, executando as providências necessárias em campo ou no posto de trabalho.

## Atores
- Segurança

## Interessados e Interesses
- Segurança: iniciar a tratativa da ocorrência com base nas informações disponíveis.
- Gestor do Condomínio: acompanhar o início do tratamento da ocorrência.
- Morador solicitante: saber que sua demanda está em atendimento.
- Sistema: registrar o início e as evidências do atendimento.

## Gatilho
O caso de uso é iniciado quando uma ocorrência atribuída entra em fase de atendimento operacional.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para atender ocorrências.
- Existe ocorrência atribuída ao responsável ou disponível para início do atendimento.

## Pós-condições
### Em caso de sucesso
- A ocorrência passa para status compatível com atendimento em andamento.
- O início do atendimento é registrado no histórico com data, hora e responsável.
- Observações iniciais de execução podem ser associadas ao registro.

### Em caso de falha
- Nenhuma alteração é confirmada se a ocorrência não estiver apta para atendimento.
- O histórico anterior da ocorrência é preservado.

## Fluxo Principal
1. O responsável acessa a fila de ocorrências sob sua responsabilidade.
2. O sistema apresenta os detalhes da ocorrência, incluindo prioridade, descrição e histórico.
3. O responsável analisa as informações e inicia o atendimento.
4. O sistema atualiza o status para em atendimento ou equivalente.
5. O responsável registra observações iniciais, quando necessário.
6. O sistema salva a movimentação e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Necessidade de complemento de informações
1. O responsável identifica informações insuficientes para atendimento.
2. O sistema permite registrar a pendência no histórico.
3. A ocorrência permanece aguardando complemento conforme o fluxo definido pelo negócio.

### FA-02 – Atendimento iniciado por outro responsável autorizado
1. Outro usuário com permissão assume o atendimento mediante redistribuição válida.
2. O sistema registra a mudança no histórico antes de iniciar a execução.

## Fluxos de Exceção
### FE-01 – Falha ao iniciar o atendimento
1. O sistema não altera o status da ocorrência.
2. O erro técnico é registrado.
3. O responsável é informado sobre a falha.

## Regras de Negócio
- Somente ocorrências válidas e atribuídas podem ser colocadas em atendimento.
- O histórico deve registrar data, hora e responsável por cada início de atendimento.
- Mudanças de status devem seguir o fluxo operacional definido pelo condomínio.

## Requisitos Especiais
- A tela deve consolidar dados suficientes para evitar consultas paralelas durante o atendimento.
- O sistema deve atualizar imediatamente a fila operacional após o início do atendimento.
- As observações inseridas devem ficar disponíveis para o gestor e para futuras atualizações.

## Requisitos Relacionados
- UC-012 – Atribuir Responsável por Ocorrências
- UC-034 – Atualizar Andamento das Ocorrências
- UC-035 – Encerrar Ocorrências
