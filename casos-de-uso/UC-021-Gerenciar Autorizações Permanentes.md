# UC-021 – Gerenciar Autorizações Permanentes

## Objetivo
Permitir que o morador gerencie autorizações permanentes de acesso relacionadas à sua unidade habitacional.

## Atores
- Morador

## Interessados e Interesses
- Morador: controlar previamente quem pode acessar a unidade ou o condomínio em caráter recorrente.
- Portaria: consultar autorizações válidas para agilizar o atendimento.
- Sistema: manter autorizações atualizadas, vigentes e auditáveis.

## Gatilho
O caso de uso é iniciado quando o morador precisa conceder, revisar, atualizar ou revogar autorizações recorrentes de entrada.

## Pré-condições
- Usuário autenticado.
- Morador vinculado a unidade habitacional ativa.
- Usuário possui permissão para gerenciar autorizações permanentes.

## Pós-condições
### Em caso de sucesso
- A autorização permanente é cadastrada, atualizada ou revogada conforme a solicitação.
- A vigência e as condições de uso ficam disponíveis para consulta da portaria.
- A alteração é registrada em auditoria.

### Em caso de falha
- Nenhuma autorização é confirmada em desacordo com as regras de vigência e identificação.
- As autorizações anteriormente válidas são preservadas até uma alteração confirmada.

## Fluxo Principal
1. O morador acessa a funcionalidade de autorizações permanentes.
2. O sistema apresenta a lista de autorizações ativas e inativas vinculadas à unidade habitacional.
3. O morador escolhe incluir, editar, consultar ou revogar uma autorização.
4. O morador informa os dados da pessoa autorizada, condições de acesso, vigência e observações.
5. O sistema valida a identificação, a vigência e eventuais conflitos.
6. O morador confirma a operação.
7. O sistema registra a autorização e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Revogar autorização vigente
1. O morador seleciona uma autorização ativa.
2. O sistema solicita confirmação da revogação.
3. Após a confirmação, a autorização deixa de ser considerada pela portaria.

### FA-02 – Atualizar vigência ou observações
1. O morador localiza uma autorização existente.
2. O sistema permite ajustar dados permitidos sem perder o histórico.
3. As alterações confirmadas passam a valer imediatamente ou na data definida.

## Fluxos de Exceção
### FE-01 – Falha ao salvar a autorização
1. O sistema não altera a autorização.
2. O erro técnico é registrado.
3. O morador é informado de que a operação não foi concluída.

## Regras de Negócio
- Autorizações permanentes devem possuir identificação mínima da pessoa autorizada e vigência definida ou condição equivalente prevista pela política do condomínio.
- Autorizações revogadas ou vencidas não podem ser utilizadas para liberar acesso.
- Toda alteração deve ficar disponível para consulta histórica da portaria e da administração.

## Requisitos Especiais
- A portaria deve visualizar autorizações vigentes de forma simples e rápida.
- O morador deve conseguir identificar claramente o status de cada autorização.
- As informações devem ser protegidas conforme a política de privacidade do condomínio.

## Requisitos Relacionados
- UC-019 – Manter Visitantes
- UC-020 – Aprovar Visitantes
- UC-029 – Registrar Entrada e Saída de Visitantes
