# UC-038 – Encerrar Manutenções

## Objetivo
Permitir o encerramento formal de uma manutenção após a conclusão do serviço.

## Atores
- Manutencista

## Interessados e Interesses
- Manutencista: concluir formalmente o serviço executado.
- Gestor do Condomínio: confirmar que a manutenção foi finalizada.
- Usuários impactados: saber que o serviço foi encerrado.
- Sistema: manter histórico completo do ciclo da manutenção.

## Gatilho
O caso de uso é iniciado quando a manutenção foi concluída e precisa ter seu resultado final registrado.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para encerrar manutenções.
- Existe manutenção em estado compatível com encerramento.

## Pós-condições
### Em caso de sucesso
- A manutenção recebe status final de encerrada ou concluída.
- O resultado do serviço, data e responsável pelo encerramento ficam registrados.
- O histórico permanece disponível para consulta e auditoria.

### Em caso de falha
- A manutenção não é encerrada sem dados mínimos de conclusão.
- O status anterior permanece inalterado até a confirmação correta da operação.

## Fluxo Principal
1. O manutencista localiza a manutenção apta para encerramento.
2. O sistema apresenta o histórico completo da manutenção.
3. O manutencista informa o resultado do serviço, as providências adotadas e observações finais.
4. O sistema valida os critérios de encerramento.
5. O manutencista confirma a conclusão.
6. O sistema altera o status final, registra o histórico de encerramento e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Serviço ainda pendente
1. Durante a análise, o manutencista identifica que ainda há atividade pendente.
2. O sistema mantém a manutenção em andamento.
3. O manutencista registra a pendência no histórico.

### FA-02 – Encerramento com custo ou material consumido
1. O manutencista informa dados complementares de execução exigidos pelo processo.
2. O sistema associa essas informações ao histórico final do serviço.

## Fluxos de Exceção
### FE-01 – Falha ao encerrar a manutenção
1. O sistema não altera o status final.
2. O erro técnico é registrado.
3. O manutencista é informado da falha.

## Regras de Negócio
- Uma manutenção só pode ser encerrada quando houver registro mínimo do resultado do serviço.
- O histórico final deve indicar responsável, data, hora e desfecho da execução.
- Manutenções encerradas não devem receber novas atualizações sem procedimento formal de reabertura, se existir.

## Requisitos Especiais
- O encerramento deve refletir imediatamente nos indicadores e listas operacionais.
- O resultado final precisa ser facilmente consultável em auditorias futuras.
- Informações complementares exigidas pelo processo devem ficar registradas no histórico final.

## Requisitos Relacionados
- UC-013 – Manter Manutenções
- UC-036 – Atender Manutenções
- UC-037 – Atualizar Andamento das Manutenções
