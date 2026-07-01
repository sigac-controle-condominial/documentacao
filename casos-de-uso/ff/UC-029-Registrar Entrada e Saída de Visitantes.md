# UC-029 – Registrar Entrada e Saída de Visitantes

## Objetivo
Registrar com precisão eventos de entrada e saída de visitantes no condomínio, garantindo segurança operacional e histórico auditável.

## Atores
- Porteiro

## Interessados e Interesses
- Porteiro: controlar acessos e manter registro confiável da movimentação de visitantes.
- Administração do condomínio: utilizar o histórico para segurança e conferências operacionais.
- Moradores: ter segurança quanto ao controle de acessos relacionados à unidade habitacional.
- Sistema: armazenar o evento com rastreabilidade e consistência temporal.

## Gatilho
O caso de uso é iniciado quando ocorre a entrada ou saída de visitantes e a portaria precisa registrar o evento.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para registrar entrada e saída de visitantes.
- Existe o visitante ou a autorização de acesso correspondente previamente cadastrada ou passível de validação no momento do atendimento.

## Pós-condições
### Em caso de sucesso
- O evento de entrada ou saída de visitante é registrado com data, hora e operador responsável.
- O histórico de acessos é atualizado imediatamente.
- As consultas e auditorias passam a refletir o novo evento.

### Em caso de falha
- Nenhum evento é confirmado com identificação inconsistente ou sem autorização válida.
- O estado anterior do histórico é preservado até que o lançamento seja concluído corretamente.

## Fluxo Principal
1. O porteiro acessa a funcionalidade de registro de acessos.
2. O sistema solicita a identificação de visitante e o tipo de evento a registrar.
3. O porteiro localiza o visitante ou a autorização de acesso correspondente, confirma os dados apresentados e informa observações, quando necessário.
4. O sistema valida a autorização, a situação atual e a coerência do evento solicitado.
5. O porteiro confirma o lançamento.
6. O sistema registra a entrada ou saída, atualiza o histórico e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Consulta de situação antes do registro
1. O porteiro localiza visitante no sistema.
2. O sistema apresenta a situação atual e o último evento registrado.
3. Após a conferência, o porteiro prossegue com o lançamento adequado.

### FA-02 – Evento incompatível com a situação atual
1. O sistema identifica, por exemplo, tentativa de registrar saída sem entrada anterior compatível.
2. O porteiro revisa os dados informados e decide corrigir o lançamento ou cancelar a operação.

## Fluxos de Exceção
### FE-01 – Falha ao salvar o evento
1. O sistema não registra o acesso.
2. O erro técnico é registrado.
3. O porteiro é informado para repetir a operação quando possível.

## Regras de Negócio
- Todo evento de acesso deve indicar operador responsável, data e hora do registro.
- O sistema deve impedir lançamentos incoerentes com a situação atual sem tratamento explícito autorizado.
- Visitantes somente podem ter acesso liberado quando houver autorização válida ou procedimento equivalente permitido pelo condomínio.

## Requisitos Especiais
- A tela deve permitir registro rápido, adequado ao contexto da portaria.
- A confirmação do evento deve ser imediata para evitar filas no atendimento.
- Os registros devem ficar disponíveis para consulta histórica e auditoria.

## Requisitos Relacionados
- UC-019 – Manter Visitantes
- UC-020 – Aprovar Visitantes
- UC-021 – Gerenciar Autorizações Permanentes
- UC-022 – Consultar Histórico de Acessos
