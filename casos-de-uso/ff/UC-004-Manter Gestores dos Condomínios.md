# UC-004 – Manter Gestores dos Condomínios

## Objetivo
Manter gestores dos condomínios do sistema de gerenciamento de condomínios, assegurando que as informações permaneçam completas, consistentes e disponíveis para os demais processos do negócio.

## Atores
- Administrador do Sistema

## Interessados e Interesses
- Administrador do Sistema: cadastrar, consultar, atualizar e inativar gestores dos condomínios conforme sua responsabilidade operacional.
- Administração do condomínio: manter gestores dos condomínios consistentes para suportar processos administrativos, operacionais e de segurança.
- Sistema: garantir integridade cadastral, rastreabilidade das alterações e vínculo correto com existem condomínios previamente cadastrados para associação do gestor..

## Gatilho
O caso de uso é iniciado quando o ator precisa cadastrar, consultar, atualizar ou inativar gestores dos condomínios para dar suporte à operação do condomínio.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para manter gestores dos condomínios.
- Existem condomínios previamente cadastrados para associação do gestor.

## Pós-condições
### Em caso de sucesso
- Gestor do condomínio cadastrado, atualizado, inativado ou consultado conforme a operação solicitada.
- Alteração registrada em auditoria com identificação do responsável, data e hora.
- As informações ficam disponíveis para os demais processos que dependem de gestores dos condomínios.

### Em caso de falha
- Nenhuma alteração é confirmada enquanto existirem inconsistências de validação ou restrições de negócio.
- O sistema preserva os dados válidos anteriormente registrados.

## Fluxo Principal
1. O ator acessa a funcionalidade de manutenção de gestores dos condomínios.
2. O sistema apresenta a lista de gestores dos condomínios e as opções de inclusão, edição, consulta e inativação.
3. O ator seleciona a operação desejada e informa dados de identificação do gestor, forma de contato, situação, perfil e vínculo com o condomínio correspondente.
4. O sistema valida os campos obrigatórios, formatos, vínculos e duplicidades aplicáveis.
5. O ator confirma a operação.
6. O sistema persiste a operação sobre gestores dos condomínios, atualiza os vínculos relacionados e registra auditoria.
7. O sistema apresenta mensagem de sucesso e a visão atualizada dos dados.

## Fluxos Alternativos
### FA-01 – Consulta sem alteração
1. O ator localiza um gestor do condomínio.
2. O sistema apresenta os dados para consulta.
3. O fluxo é encerrado sem persistir alterações.

### FA-02 – Dados inválidos ou incompletos
1. O sistema destaca os campos com inconsistência e informa a regra violada.
2. O ator corrige os dados informados.
3. O fluxo retorna ao passo 3 do fluxo principal.

### FA-03 – Inativação de gestor do condomínio
1. O ator seleciona a opção de inativar o gestor do condomínio.
2. O sistema solicita confirmação da operação.
3. O sistema marca o gestor do condomínio como inativo, preservando o histórico para auditoria.

## Fluxos de Exceção
### FE-01 – Falha de persistência ou indisponibilidade
1. O sistema interrompe a operação antes da confirmação.
2. O sistema registra o erro técnico para análise.
3. O sistema informa que a operação não pôde ser concluída naquele momento.

## Regras de Negócio
- O sistema não deve permitir duplicidade indevida de gestor do condomínio considerando os identificadores de negócio aplicáveis.
- Gestor do condomínio inativo não deve ser oferecido para novos processos operacionais, salvo quando a regra do negócio exigir consulta histórica.
- Toda operação de inclusão, alteração e inativação deve ser auditável.
- Um mesmo usuário só pode atuar como gestor nos condomínios para os quais estiver formalmente vinculado.
- Não é permitido manter vínculo duplicado ativo entre o mesmo gestor e o mesmo condomínio.

## Requisitos Especiais
- A interface deve permitir pesquisa e filtragem para agilizar a manutenção cadastral.
- As mensagens de validação devem indicar claramente o campo e a regra que impediram a confirmação.
- A funcionalidade deve manter consistência transacional entre o cadastro principal e os vínculos associados.

## Requisitos Relacionados
- UC-003 – Manter Condomínios
- UC-010 – Manter Comunicados
- UC-011 – Manter Ocorrências
