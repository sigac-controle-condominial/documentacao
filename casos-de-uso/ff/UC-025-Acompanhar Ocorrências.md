# UC-025 – Acompanhar Ocorrências

## Objetivo
Permitir que o morador acompanhe o andamento das ocorrências que registrou ou que estejam vinculadas à sua unidade habitacional.

## Atores
- Morador

## Interessados e Interesses
- Morador: obter visibilidade sobre o tratamento da demanda.
- Gestor do Condomínio: reduzir contatos paralelos por meio de informação transparente.
- Sistema: consolidar histórico, status e interações da ocorrência.

## Gatilho
O caso de uso é iniciado quando o morador deseja consultar o status ou o histórico de uma ocorrência.

## Pré-condições
- Usuário autenticado.
- Morador possui permissão para consultar ocorrências vinculadas ao seu perfil.
- Existe pelo menos uma ocorrência acessível ao morador.

## Pós-condições
### Em caso de sucesso
- O morador visualiza a situação atual da ocorrência e o histórico de movimentações.
- Nenhum dado da ocorrência é alterado durante a consulta.

### Em caso de falha
- Nenhum dado é alterado.
- O sistema mantém os filtros para nova tentativa, quando aplicável.

## Fluxo Principal
1. O morador acessa a funcionalidade de acompanhamento de ocorrências.
2. O sistema apresenta a lista de ocorrências vinculadas ao morador ou à sua unidade habitacional.
3. O morador aplica filtros de pesquisa e seleciona a ocorrência desejada.
4. O sistema apresenta status, prioridade, responsável, histórico de atualizações e anexos disponíveis.
5. O morador analisa as informações e encerra a consulta.

## Fluxos Alternativos
### FA-01 – Ocorrência encerrada
1. O sistema apresenta a data de encerramento e a solução registrada.
2. O morador consulta o histórico final da tratativa.
3. O fluxo é encerrado normalmente.

### FA-02 – Sem ocorrências localizadas
1. O sistema informa que não existem ocorrências compatíveis com os filtros informados.
2. O morador ajusta os filtros e refaz a pesquisa.

## Fluxos de Exceção
### FE-01 – Falha ao recuperar o histórico
1. O sistema não apresenta os detalhes da ocorrência.
2. O erro técnico é registrado.
3. O morador é informado para tentar novamente posteriormente.

## Regras de Negócio
- O morador só pode visualizar ocorrências às quais possua vínculo legítimo de acesso.
- Atualizações registradas pela equipe devem compor o histórico em ordem cronológica.
- Ocorrências encerradas permanecem disponíveis para consulta histórica.

## Requisitos Especiais
- A linha do tempo da ocorrência deve apresentar data, autor e descrição resumida de cada atualização.
- O status deve ser apresentado de forma clara e padronizada.
- Anexos e observações devem respeitar as permissões de visualização do perfil do morador.

## Requisitos Relacionados
- UC-024 – Abrir Ocorrências
- UC-034 – Atualizar Andamento das Ocorrências
- UC-035 – Encerrar Ocorrências
