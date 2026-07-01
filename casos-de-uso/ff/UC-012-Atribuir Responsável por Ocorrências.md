# UC-012 – Atribuir Responsável por Ocorrências

## Objetivo
Permitir a atribuição de ocorrências ao responsável mais adequado.

## Atores
- Gestor do Condomínio

## Interessados e Interesses
- Gestor do Condomínio: distribuir ocorrências para garantir tratamento adequado e dentro do prazo.
- Responsável: receber responsabilidade formal sobre ocorrências com informações suficientes para execução.
- Sistema: manter rastreabilidade da atribuição e do responsável atual.

## Gatilho
O caso de uso é iniciado quando um ocorrência precisa receber ou alterar o responsável pela execução.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para atribuir ocorrências.
- Existem ocorrências abertas e equipe apta para tratá-las.
- Existe pelo menos um ocorrência aguardando atribuição.

## Pós-condições
### Em caso de sucesso
- O ocorrência passa a possuir responsável definido.
- A atribuição e eventual justificativa são registradas em auditoria.
- O responsável é notificado sobre a nova responsabilidade.

### Em caso de falha
- Nenhuma atribuição é confirmada sem responsável válido.
- O item permanece com o responsável anterior ou sem responsável, conforme o estado inicial.

## Fluxo Principal
1. O ator acessa a lista de ocorrências pendentes de atribuição.
2. O sistema apresenta os detalhes do ocorrência e os responsávels disponíveis.
3. O ator seleciona o responsável considerando prioridade, tipo da ocorrência, local, prazo e competência do responsável selecionado.
4. O ator confirma a atribuição.
5. O sistema valida a disponibilidade do responsável selecionado, registra a alteração e notifica os envolvidos.
6. O sistema apresenta a confirmação da operação.

## Fluxos Alternativos
### FA-01 – Reatribuição de ocorrência
1. O ator identifica que o ocorrência já possui responsável, mas precisa de redistribuição.
2. O sistema solicita justificativa para a mudança.
3. Após a confirmação, a nova atribuição é registrada no histórico.

### FA-02 – Nenhum responsável disponível
1. O sistema informa que não há responsável com disponibilidade compatível.
2. O ator pode manter o item pendente ou retornar para nova seleção posteriormente.

## Fluxos de Exceção
### FE-01 – Falha ao salvar a atribuição
1. O sistema não altera o responsável do item.
2. O erro técnico é registrado para análise.
3. O ator é informado de que a atribuição não foi concluída.

## Regras de Negócio
- A atribuição deve considerar prioridade, tipo da ocorrência, local, prazo e competência do responsável selecionado.
- O histórico de responsáveis por ocorrências deve ser preservado.
- Somente usuários habilitados podem receber a atribuição.

## Requisitos Especiais
- A funcionalidade deve destacar itens sem responsável ou com prazo próximo do vencimento.
- As notificações devem conter os dados mínimos para início do atendimento.
- A atualização do responsável deve ser refletida imediatamente nas filas operacionais.

## Requisitos Relacionados
- UC-011 – Manter Ocorrências
- UC-033 – Atender Ocorrências
- UC-034 – Atualizar Andamento das Ocorrências
