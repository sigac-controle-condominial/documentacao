# UC-036 – Atender Manutenções

## Objetivo
Permitir que o manutencista inicie o atendimento de uma manutenção sob sua responsabilidade.

## Atores
- Manutencista

## Interessados e Interesses
- Manutencista: iniciar o serviço com base nas informações planejadas.
- Gestor do Condomínio: acompanhar o início da manutenção.
- Moradores e usuários impactados: saber que a manutenção está em execução.
- Sistema: registrar início, responsável e evidências da execução.

## Gatilho
O caso de uso é iniciado quando uma manutenção atribuída está pronta para execução.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para atender manutenções.
- Existe manutenção atribuída ao manutencista ou liberada para início.

## Pós-condições
### Em caso de sucesso
- A manutenção passa para status de atendimento em andamento ou equivalente.
- O início do serviço é registrado com data, hora e responsável.
- Observações iniciais da execução ficam disponíveis no histórico.

### Em caso de falha
- Nenhuma manutenção é iniciada se não atender às condições operacionais ou de negócio.
- O histórico anterior permanece preservado.

## Fluxo Principal
1. O manutencista acessa a lista de manutenções sob sua responsabilidade.
2. O sistema apresenta os dados da manutenção, como local, descrição, prioridade e prazo.
3. O manutencista analisa as informações e inicia o atendimento.
4. O sistema atualiza o status da manutenção.
5. O manutencista registra observações iniciais, quando necessário.
6. O sistema salva a movimentação e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Necessidade de reagendamento
1. O manutencista identifica impedimento para iniciar o serviço no momento.
2. O sistema permite registrar a justificativa e a pendência conforme a regra do processo.

### FA-02 – Atendimento dependente de material
1. O manutencista informa indisponibilidade de material ou recurso.
2. O sistema registra a pendência no histórico para acompanhamento.

## Fluxos de Exceção
### FE-01 – Falha ao iniciar a manutenção
1. O sistema não altera o status da manutenção.
2. O erro técnico é registrado.
3. O manutencista é informado da falha.

## Regras de Negócio
- Somente manutenções atribuídas e aptas podem entrar em atendimento.
- O histórico deve registrar quem iniciou a execução e quando.
- Mudanças de status precisam seguir o fluxo definido pelo condomínio.

## Requisitos Especiais
- A funcionalidade deve oferecer acesso rápido às informações do serviço em campo.
- As atualizações devem refletir imediatamente nos painéis de acompanhamento.
- Observações de execução devem permanecer associadas ao histórico da manutenção.

## Requisitos Relacionados
- UC-014 – Atribuir Manutencista
- UC-037 – Atualizar Andamento das Manutenções
- UC-038 – Encerrar Manutenções
