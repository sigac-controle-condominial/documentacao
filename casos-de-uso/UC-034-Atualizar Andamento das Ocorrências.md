# UC-034 – Atualizar Andamento das Ocorrências

## Objetivo
Permitir o registro do andamento de uma ocorrência em tratamento, mantendo os envolvidos informados sobre sua evolução.

## Atores
- Segurança

## Interessados e Interesses
- Segurança: registrar progresso, pendências e providências adotadas.
- Gestor do Condomínio: acompanhar evolução e gargalos.
- Morador solicitante: visualizar o avanço da tratativa, quando aplicável.
- Sistema: manter histórico cronológico e consistente da ocorrência.

## Gatilho
O caso de uso é iniciado quando há nova informação relevante sobre uma ocorrência em aberto.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para atualizar ocorrências.
- Existe ocorrência em aberto ou em atendimento.

## Pós-condições
### Em caso de sucesso
- O andamento informado é registrado no histórico da ocorrência.
- O status e outros campos derivados são atualizados quando necessário.
- Os envolvidos passam a visualizar a informação mais recente.

### Em caso de falha
- Nenhuma atualização parcial é confirmada sem sucesso na gravação.
- O histórico anteriormente registrado é preservado.

## Fluxo Principal
1. O responsável localiza a ocorrência em andamento.
2. O sistema apresenta o histórico e o status atual.
3. O responsável registra a atualização de andamento, podendo incluir nova situação, observações, anexos e pendências.
4. O sistema valida os dados informados.
5. O responsável confirma a atualização.
6. O sistema grava o histórico, ajusta o status quando necessário e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Registro de pendência externa
1. O responsável informa dependência de terceiro, material ou aprovação.
2. O sistema registra a pendência e pode ajustar o status para aguardando ação externa, se essa situação existir.

### FA-02 – Inclusão de evidências
1. O responsável anexa imagens, documentos ou comprovantes ao andamento.
2. O sistema valida e associa os anexos ao histórico da ocorrência.

## Fluxos de Exceção
### FE-01 – Falha ao gravar o andamento
1. O sistema não adiciona a nova movimentação ao histórico.
2. O erro técnico é registrado.
3. O responsável é informado para tentar novamente.

## Regras de Negócio
- Cada atualização deve compor o histórico da ocorrência em ordem cronológica.
- Mudanças de status devem ser coerentes com o estágio atual da ocorrência.
- Somente usuários autorizados podem registrar andamentos.

## Requisitos Especiais
- O histórico deve destacar claramente data, autor e resumo da atualização.
- Anexos precisam permanecer vinculados ao evento de andamento correspondente.
- As atualizações relevantes devem ficar disponíveis para consulta pelo perfil autorizado imediatamente após o registro.

## Requisitos Relacionados
- UC-025 – Acompanhar Ocorrências
- UC-033 – Atender Ocorrências
- UC-035 – Encerrar Ocorrências
