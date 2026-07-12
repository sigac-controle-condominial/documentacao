# UC-002 – Alterar Senha

## Objetivo
Permitir que o usuário altere sua senha de acesso, reforçando a segurança da conta.

## Atores
- Usuário

## Interessados e Interesses
- Usuário: proteger o acesso à própria conta.
- Administração do condomínio: reduzir riscos de acesso indevido.
- Sistema: aplicar política de segurança e registrar a alteração credencial.

## Gatilho
O caso de uso é iniciado quando o usuário decide trocar sua senha por segurança, rotina ou exigência operacional.

## Pré-condições
- Usuário autenticado.
- Usuário possui conta ativa.
- A política de senhas do sistema está configurada.

## Pós-condições
### Em caso de sucesso
- A senha é atualizada com sucesso.
- As novas regras de autenticação passam a valer imediatamente.
- A alteração é registrada em histórico de segurança.

### Em caso de falha
- A senha anterior permanece válida até que a alteração seja confirmada com sucesso.
- Nenhum dado sensível é exibido em caso de erro.

## Fluxo Principal
1. O usuário acessa a funcionalidade de alteração de senha.
2. O sistema solicita a senha atual e a nova senha.
3. O usuário informa os dados requeridos e confirma a operação.
4. O sistema valida a senha atual, a confirmação da nova senha e a aderência à política de segurança.
5. O sistema grava a nova senha de forma segura e registra a alteração.
6. O sistema informa a conclusão da operação ao usuário.

## Fluxos Alternativos
### FA-01 – Senha atual incorreta
1. O sistema informa que a senha atual não confere.
2. O usuário corrige a informação.
3. O fluxo retorna ao passo 2 do fluxo principal.

### FA-02 – Nova senha fora da política
1. O sistema informa que a nova senha não atende aos critérios mínimos.
2. O usuário informa uma nova senha válida.
3. O fluxo retorna ao passo 2 do fluxo principal.

## Fluxos de Exceção
### FE-01 – Falha ao atualizar a senha
1. O sistema não altera a credencial do usuário.
2. O erro técnico é registrado.
3. O usuário é informado para tentar novamente posteriormente.

## Regras de Negócio
- A nova senha deve atender à política de complexidade definida pelo sistema.
- A confirmação da nova senha deve coincidir integralmente com o valor informado.
- A senha deve ser armazenada de forma segura, sem exposição em texto puro.

## Requisitos Especiais
- A interface não deve exibir a senha em texto aberto.
- O sistema deve informar os critérios mínimos de senha antes da confirmação.
- A alteração deve invalidar sessões conforme a política de segurança adotada, se aplicável.

## Requisitos Relacionados
- UC-001 – Manter Dados Pessoais
