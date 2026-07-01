# UC-035 – Encerrar Ocorrências

## Objetivo
Permitir o encerramento formal de uma ocorrência após a conclusão de sua tratativa.

## Atores
- Segurança

## Interessados e Interesses
- Segurança: concluir formalmente a ocorrência.
- Gestor do Condomínio: assegurar que a demanda teve tratamento adequado.
- Morador solicitante: visualizar a solução final e o encerramento do caso.
- Sistema: preservar histórico e solução registrada.

## Gatilho
O caso de uso é iniciado quando a ocorrência atingiu condição de conclusão e precisa ter seu status final registrado.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para encerrar ocorrências.
- Existe ocorrência em estado compatível com encerramento.

## Pós-condições
### Em caso de sucesso
- A ocorrência recebe status final de encerramento.
- A solução adotada, data e responsável pelo encerramento ficam registradas no histórico.
- A ocorrência permanece disponível para consulta histórica.

### Em caso de falha
- A ocorrência não é encerrada sem registro mínimo da solução ou justificativa exigida.
- O status anterior permanece válido até que o encerramento seja confirmado.

## Fluxo Principal
1. O responsável localiza a ocorrência apta para encerramento.
2. O sistema apresenta o histórico completo e os dados atuais do registro.
3. O responsável informa a solução adotada, resultado do atendimento e observações finais.
4. O sistema valida se a ocorrência atende aos critérios de encerramento.
5. O responsável confirma o encerramento.
6. O sistema atualiza o status final, registra o histórico e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Retorno para atendimento
1. Durante a análise, o responsável identifica pendência que impede o encerramento.
2. O sistema mantém a ocorrência em aberto ou em atendimento.
3. O responsável registra a pendência no histórico.

### FA-02 – Encerramento com necessidade de validação do gestor
1. O sistema identifica que o tipo de ocorrência exige validação adicional.
2. O registro fica sinalizado para conferência administrativa antes da conclusão definitiva, se essa regra existir.

## Fluxos de Exceção
### FE-01 – Falha ao encerrar a ocorrência
1. O sistema não altera o status final do registro.
2. O erro técnico é registrado.
3. O responsável é informado da indisponibilidade.

## Regras de Negócio
- Ocorrências só podem ser encerradas quando houver solução ou desfecho formalmente registrado.
- O histórico final deve indicar responsável, data, hora e resumo do encerramento.
- Ocorrências encerradas não devem receber novas atualizações sem reabertura autorizada pelo processo do negócio.

## Requisitos Especiais
- A solução final deve ser apresentada de forma clara para futuras consultas.
- O encerramento deve refletir imediatamente nas filas e indicadores operacionais.
- O sistema deve permitir consulta histórica completa após a conclusão.

## Requisitos Relacionados
- UC-025 – Acompanhar Ocorrências
- UC-033 – Atender Ocorrências
- UC-034 – Atualizar Andamento das Ocorrências
