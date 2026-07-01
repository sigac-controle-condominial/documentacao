# UC-037 – Atualizar Andamento das Manutenções

## Objetivo
Permitir o registro do andamento de uma manutenção em execução.

## Atores
- Manutencista

## Interessados e Interesses
- Manutencista: registrar progresso, pendências e ações executadas.
- Gestor do Condomínio: acompanhar a evolução e o cumprimento de prazos.
- Usuários impactados: ser informados sobre a situação do serviço, quando aplicável.
- Sistema: consolidar histórico cronológico da manutenção.

## Gatilho
O caso de uso é iniciado quando existe nova informação relevante sobre uma manutenção em aberto.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para atualizar manutenções.
- Existe manutenção em aberto ou em andamento.

## Pós-condições
### Em caso de sucesso
- A atualização de andamento é registrada com sucesso no histórico.
- O status e demais dados derivados são atualizados conforme a informação lançada.
- Os perfis autorizados passam a visualizar a evolução mais recente.

### Em caso de falha
- Nenhuma movimentação parcial é gravada em caso de falha.
- O histórico anteriormente registrado permanece íntegro.

## Fluxo Principal
1. O manutencista localiza a manutenção em andamento.
2. O sistema apresenta o status atual e o histórico de atualizações.
3. O manutencista registra o progresso do serviço, incluindo observações, etapas concluídas, pendências ou anexos.
4. O sistema valida as informações informadas.
5. O manutencista confirma a atualização.
6. O sistema grava o novo andamento, ajusta o status quando aplicável e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Registro de pendência técnica
1. O manutencista informa necessidade de peça, fornecedor ou autorização adicional.
2. O sistema registra a pendência no histórico e ajusta o status conforme a regra do processo.

### FA-02 – Inclusão de evidência de execução
1. O manutencista anexa fotos, relatórios ou comprovantes.
2. O sistema valida e associa os anexos ao evento de andamento.

## Fluxos de Exceção
### FE-01 – Falha ao gravar o andamento
1. O sistema não adiciona a nova atualização ao histórico.
2. O erro técnico é registrado.
3. O manutencista é informado de que a operação não foi concluída.

## Regras de Negócio
- Cada atualização deve preservar o histórico cronológico da manutenção.
- Somente usuários autorizados podem registrar andamento em manutenção.
- Mudanças de status devem respeitar o fluxo operacional definido pelo condomínio.

## Requisitos Especiais
- A visualização do histórico deve facilitar a compreensão do progresso do serviço.
- As atualizações devem ficar disponíveis imediatamente para o gestor.
- Anexos precisam permanecer vinculados ao evento de andamento correspondente.

## Requisitos Relacionados
- UC-013 – Manter Manutenções
- UC-036 – Atender Manutenções
- UC-038 – Encerrar Manutenções
