# UC-031 – Registrar Recebimento de Encomendas

## Objetivo
Registrar o recebimento de encomendas destinadas às unidades habitacionais, garantindo rastreabilidade desde a chegada até a entrega ao destinatário.

## Atores
- Porteiro

## Interessados e Interesses
- Porteiro: registrar corretamente a chegada da encomenda.
- Morador: ter visibilidade de que a encomenda foi recebida.
- Administração do condomínio: manter controle sobre itens sob guarda temporária.
- Sistema: armazenar histórico da encomenda e seu status atual.

## Gatilho
O caso de uso é iniciado quando uma encomenda chega ao condomínio e precisa ser recebida pela portaria.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para registrar recebimento de encomendas.
- Existe unidade habitacional destinatária identificável para a encomenda.

## Pós-condições
### Em caso de sucesso
- A encomenda é registrada com destinatário, origem, data e hora de recebimento.
- O status da encomenda passa a indicar disponibilidade para entrega.
- O morador ou fluxo correspondente pode ser notificado sobre o recebimento.

### Em caso de falha
- Nenhuma encomenda é registrada com destinatário inconsistente ou dados mínimos ausentes.
- O estoque lógico de encomendas aguardando entrega permanece inalterado até a confirmação correta.

## Fluxo Principal
1. O porteiro acessa a funcionalidade de recebimento de encomendas.
2. O sistema apresenta o formulário de registro.
3. O porteiro informa unidade destinatária, identificação da encomenda, remetente, transportadora e observações, quando aplicável.
4. O sistema valida os dados obrigatórios e o vínculo com a unidade habitacional.
5. O porteiro confirma o recebimento.
6. O sistema registra a encomenda com status de aguardando entrega e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Destinatário não localizado de imediato
1. O porteiro pesquisa a unidade ou o morador responsável.
2. O sistema apresenta opções compatíveis para seleção.
3. Após a identificação correta, o fluxo segue normalmente.

### FA-02 – Recebimento com avaria observada
1. O porteiro registra observação sobre a condição da encomenda.
2. O sistema associa a observação ao histórico do item.

## Fluxos de Exceção
### FE-01 – Falha ao registrar o recebimento
1. O sistema não cria o registro da encomenda.
2. O erro técnico é registrado.
3. O porteiro é informado de que a operação não foi concluída.

## Regras de Negócio
- Cada encomenda recebida deve permanecer vinculada a uma unidade habitacional até sua entrega.
- O status inicial após o recebimento deve indicar que a encomenda está sob guarda do condomínio.
- Observações relevantes, como avarias aparentes, devem compor o histórico do item.

## Requisitos Especiais
- O registro deve ser rápido para não comprometer o atendimento da portaria.
- O histórico da encomenda deve indicar claramente quem registrou o recebimento.
- Se houver notificação ao morador, ela deve ocorrer logo após a confirmação do recebimento.

## Requisitos Relacionados
- UC-027 – Consultar Encomendas
- UC-032 – Registrar Entrega de Encomendas
