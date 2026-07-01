# UC-001 – Manter Dados Pessoais

## Objetivo
Permitir que o usuário mantenha seus dados pessoais e de contato atualizados para uso em autenticação, comunicação e identificação dentro do sistema.

## Atores
- Usuário

## Interessados e Interesses
- Usuário: manter seus dados corretos para acesso e comunicação.
- Administração do condomínio: contar com informações cadastrais confiáveis para atendimento e contato.
- Sistema: preservar consistência, rastreabilidade e integridade do perfil do usuário.

## Gatilho
O caso de uso é iniciado quando o usuário precisa cadastrar, revisar ou atualizar informações do próprio perfil.

## Pré-condições
- Usuário autenticado.
- Usuário possui cadastro ativo no sistema.
- O perfil acessado pertence ao próprio usuário ou a contexto permitido pela regra de negócio.

## Pós-condições
### Em caso de sucesso
- Os dados pessoais e de contato do usuário são atualizados com sucesso.
- As alterações passam a valer para os processos que utilizam o cadastro do usuário.
- A operação fica registrada em auditoria.

### Em caso de falha
- Nenhuma alteração é persistida enquanto houver inconsistências.
- Os dados anteriormente válidos permanecem ativos até a confirmação da atualização.

## Fluxo Principal
1. O usuário acessa a área de dados pessoais.
2. O sistema apresenta os dados atualmente cadastrados.
3. O usuário altera as informações permitidas, como nome, telefone, e-mail e demais campos do perfil.
4. O sistema valida campos obrigatórios, formatos e regras de unicidade quando aplicáveis.
5. O usuário confirma a atualização.
6. O sistema grava as alterações, registra auditoria e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Consulta sem alteração
1. O usuário acessa o próprio cadastro apenas para consulta.
2. O sistema apresenta os dados atuais.
3. O caso de uso é encerrado sem persistir mudanças.

### FA-02 – Dados inválidos
1. O sistema informa as inconsistências encontradas nos campos preenchidos.
2. O usuário corrige os dados.
3. O fluxo retorna ao passo 3 do fluxo principal.

## Fluxos de Exceção
### FE-01 – Falha ao atualizar o perfil
1. O sistema não salva as alterações solicitadas.
2. O erro técnico é registrado.
3. O usuário é informado de que a operação não pôde ser concluída.

## Regras de Negócio
- Campos de identificação e contato devem obedecer aos formatos definidos pelo sistema.
- Alterações em dados sensíveis podem exigir validações adicionais definidas pela política do condomínio.
- Toda alteração no perfil deve ser auditável.

## Requisitos Especiais
- A interface deve destacar claramente quais dados são editáveis pelo próprio usuário.
- As mensagens de validação devem ser objetivas e indicar o campo com problema.
- A confirmação da atualização deve ocorrer sem ambiguidades para o usuário.

## Requisitos Relacionados
- UC-002 – Alterar Senha
