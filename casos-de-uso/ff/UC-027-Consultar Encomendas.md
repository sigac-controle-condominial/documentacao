# UC-027 – Consultar Encomendas

## Objetivo
Permitir a consulta de encomendas relevantes para a gestão e operação do condomínio.

## Atores
- Morador

## Interessados e Interesses
- Morador: localizar e analisar encomendas com rapidez para tomada de decisão operacional.
- Administração do condomínio: obter visibilidade sobre encomendas sem comprometer a integridade dos registros.
- Sistema: retornar informações consistentes, atualizadas e compatíveis com o perfil de acesso do solicitante.

## Gatilho
O caso de uso é iniciado quando o ator precisa consultar encomendas para análise, conferência ou atendimento operacional.

## Pré-condições
- Usuário autenticado.
- Usuário possui permissão para consultar encomendas.
- Existem encomendas vinculadas à unidade habitacional do morador.

## Pós-condições
### Em caso de sucesso
- Os dados de encomendas são apresentados conforme os filtros aplicados.
- A consulta fica disponível sem alterar os registros originais.

### Em caso de falha
- Nenhum dado é alterado.
- O sistema preserva os filtros informados para nova tentativa, quando aplicável.

## Fluxo Principal
1. O ator acessa a funcionalidade de consulta de encomendas.
2. O sistema apresenta filtros de pesquisa, como período, status, destinatário e identificador da encomenda.
3. O ator informa os critérios desejados e solicita a pesquisa.
4. O sistema valida os filtros e executa a consulta.
5. O sistema apresenta a lista de encomendas compatível com os critérios informados.
6. O ator analisa os resultados e, se necessário, acessa o detalhamento de um registro.

## Fluxos Alternativos
### FA-01 – Nenhum resultado encontrado
1. O sistema informa que não há registros compatíveis com os critérios pesquisados.
2. O ator pode ajustar os filtros.
3. O fluxo retorna ao passo 2 do fluxo principal.

### FA-02 – Filtros inválidos
1. O sistema informa a inconsistência dos parâmetros informados.
2. O ator corrige os filtros.
3. O fluxo retorna ao passo 2 do fluxo principal.

## Fluxos de Exceção
### FE-01 – Falha na consulta
1. O sistema não conclui a pesquisa.
2. O erro é registrado para análise técnica.
3. O sistema informa a indisponibilidade temporária da consulta.

## Regras de Negócio
- Somente registros compatíveis com o perfil de acesso do ator devem ser exibidos.
- A consulta deve considerar somente dados ativos por padrão, preservando a possibilidade de consulta histórica quando cabível.
- O morador só pode consultar encomendas vinculadas à sua unidade habitacional.
- Encomendas entregues devem permanecer acessíveis para consulta histórica.

## Requisitos Especiais
- Os resultados devem permitir ordenação e paginação quando houver grande volume de registros.
- A resposta da consulta deve ocorrer em tempo adequado ao uso operacional.
- O detalhamento deve preservar a confidencialidade de dados sensíveis.

## Requisitos Relacionados
- UC-031 – Registrar Recebimento de Encomendas
- UC-032 – Registrar Entrega de Encomendas
