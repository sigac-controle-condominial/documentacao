# UC-032 – Registrar Entrega de Encomendas

## Objetivo
Registrar a entrega de encomendas recebidas pelo condomínio ao destinatário ou representante autorizado.

## Atores
- Porteiro

## Interessados e Interesses
- Porteiro: comprovar a entrega da encomenda.
- Morador: receber a encomenda com registro adequado.
- Administração do condomínio: manter histórico de guarda e entrega dos itens.
- Sistema: atualizar o status final da encomenda e preservar a trilha de auditoria.

## Gatilho
O caso de uso é iniciado quando uma encomenda aguardando retirada é entregue ao morador ou responsável autorizado.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para registrar entrega de encomendas.
- Existe pelo menos uma encomenda registrada como aguardando entrega.

## Pós-condições
### Em caso de sucesso
- A entrega é registrada com data, hora e identificação de quem recebeu.
- O status da encomenda passa a indicar que o item foi entregue.
- O histórico completo da encomenda fica disponível para consulta futura.

### Em caso de falha
- Nenhuma encomenda tem seu status alterado sem confirmação válida da entrega.
- Encomendas ainda não entregues permanecem disponíveis para controle da portaria.

## Fluxo Principal
1. O porteiro acessa a lista de encomendas aguardando entrega.
2. O sistema apresenta as encomendas pendentes e seus destinatários.
3. O porteiro localiza a encomenda e confirma a identificação de quem está recebendo o item.
4. O sistema valida se o recebedor é o destinatário ou representante autorizado.
5. O porteiro confirma a entrega.
6. O sistema registra a entrega, atualiza o status e apresenta a confirmação.

## Fluxos Alternativos
### FA-01 – Entrega a representante autorizado
1. O recebedor não é o destinatário principal.
2. O porteiro informa o representante autorizado.
3. O sistema registra a entrega vinculando o nome do recebedor efetivo ao histórico.

### FA-02 – Localização de encomenda específica
1. O porteiro utiliza filtros de pesquisa por unidade, morador ou identificador da encomenda.
2. O sistema apresenta os itens compatíveis para seleção.

## Fluxos de Exceção
### FE-01 – Falha ao registrar a entrega
1. O sistema não altera o status da encomenda.
2. O erro técnico é registrado.
3. O porteiro é informado de que a operação não foi concluída.

## Regras de Negócio
- Somente encomendas com status de aguardando entrega podem ser entregues.
- O histórico deve registrar quem recebeu, quem efetuou a entrega e quando a operação ocorreu.
- Uma encomenda entregue não pode retornar ao estado anterior sem ação administrativa autorizada.

## Requisitos Especiais
- A operação deve exigir o mínimo de passos possível para agilizar o atendimento.
- O detalhamento da entrega deve ficar visível em consultas posteriores.
- Quando houver coleta de comprovação de recebimento, ela deve ser vinculada ao histórico do item.

## Requisitos Relacionados
- UC-027 – Consultar Encomendas
- UC-031 – Registrar Recebimento de Encomendas
