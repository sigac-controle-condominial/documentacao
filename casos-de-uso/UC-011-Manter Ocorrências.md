# UC-011 – Manter Ocorrências

## Objetivo
Manter ocorrências do sistema de gerenciamento de condomínios, assegurando que as informações permaneçam completas, consistentes e disponíveis para os demais processos do negócio.

## Atores
- Gestor do Condomínio

## Interessados e Interesses
- Gestor do Condomínio: cadastrar, consultar, atualizar e inativar ocorrências conforme sua responsabilidade operacional.
- Administração do condomínio: manter ocorrências consistentes para suportar processos administrativos, operacionais e de segurança.
- Sistema: garantir integridade cadastral, rastreabilidade das alterações e vínculo correto com existem categorias, prioridades e regras de tratamento definidas para o condomínio..

## Gatilho
O caso de uso é iniciado quando o ator precisa cadastrar, consultar, atualizar ou inativar ocorrências para dar suporte à operação do condomínio.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para manter ocorrências.
- Existem categorias, prioridades e regras de tratamento definidas para o condomínio.

## Pós-condições
### Em caso de sucesso
- Ocorrência cadastrado, atualizado, inativado ou consultado conforme a operação solicitada.
- Alteração registrada em auditoria com identificação do responsável, data e hora.
- As informações ficam disponíveis para os demais processos que dependem de ocorrências.

### Em caso de falha
- Nenhuma alteração é confirmada enquanto existirem inconsistências de validação ou restrições de negócio.
- O sistema preserva os dados válidos anteriormente registrados.

## Fluxo Principal
1. O ator acessa a funcionalidade de manutenção de ocorrências.
2. O sistema apresenta a lista de ocorrências e as opções de inclusão, edição, consulta e inativação.
3. O ator seleciona a operação desejada e informa dados como categoria, prioridade, descrição, situação, unidade relacionada e demais informações administrativas.
4. O sistema valida os campos obrigatórios, formatos, vínculos e duplicidades aplicáveis.
5. O ator confirma a operação.
6. O sistema persiste a operação sobre ocorrências, atualiza os vínculos relacionados e registra auditoria.
7. O sistema apresenta mensagem de sucesso e a visão atualizada dos dados.

## Fluxos Alternativos
### FA-01 – Consulta sem alteração
1. O ator localiza um ocorrência.
2. O sistema apresenta os dados para consulta.
3. O fluxo é encerrado sem persistir alterações.

### FA-02 – Dados inválidos ou incompletos
1. O sistema destaca os campos com inconsistência e informa a regra violada.
2. O ator corrige os dados informados.
3. O fluxo retorna ao passo 3 do fluxo principal.

### FA-03 – Inativação de ocorrência
1. O ator seleciona a opção de inativar o ocorrência.
2. O sistema solicita confirmação da operação.
3. O sistema marca o ocorrência como inativo, preservando o histórico para auditoria.

## Fluxos de Exceção
### FE-01 – Falha de persistência ou indisponibilidade
1. O sistema interrompe a operação antes da confirmação.
2. O sistema registra o erro técnico para análise.
3. O sistema informa que a operação não pôde ser concluída naquele momento.

## Regras de Negócio
- O sistema não deve permitir duplicidade indevida de ocorrência considerando os identificadores de negócio aplicáveis.
- Ocorrência inativo não deve ser oferecido para novos processos operacionais, salvo quando a regra do negócio exigir consulta histórica.
- Toda operação de inclusão, alteração e inativação deve ser auditável.
- A ocorrência deve possuir status compatível com o fluxo de tratamento adotado pelo condomínio.
- Categorias e prioridades devem seguir as tabelas configuradas para o condomínio.

## Requisitos Especiais
- A interface deve permitir pesquisa e filtragem para agilizar a manutenção cadastral.
- As mensagens de validação devem indicar claramente o campo e a regra que impediram a confirmação.
- A funcionalidade deve manter consistência transacional entre o cadastro principal e os vínculos associados.

## Requisitos Relacionados
- UC-012 – Atribuir Responsável por Ocorrências
- UC-024 – Abrir Ocorrências
- UC-033 – Atender Ocorrências
