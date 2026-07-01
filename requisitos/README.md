# Requisitos do Sistema de Gestão Condominial

## Requisitos Funcionais

### RF-01 - Gestão de Unidades Habitacionais

- RF-01-01 - O sistema deve permitir o gerenciamento de dados das unidades habitacionais.
- RF-01-02 - O sistema deve permitir o gerenciamento de dados dos agrupamentos físicos (Torres, Blocos, Quadras, Setores).
- RF-01-03 - O sistema deve permitir a associação entre unidades habitacionais e agrupamentos físicos.

### RF-02 - Gestão de Usuários e Perfis

- RF-02-01 - O sistema deve permitir o gerenciamento de dados dos usuários.
- RF-02-02 - O sistema deve permitir o gerenciamento de dados dos perfís de acesso.
- RF-02-03 - O sistema deve permitir a associação entre usuários e perfis de acesso.
- RF-02-04 - O sistema deve permitir que o usuário tenha multiplos perfis.

### RF-03 - Gestão de Moradores

- RF-03-01 - O sistema deve permitir a associação entre usuários e unidades habitacionais.
- RF-03-02 - O sistema deve permitir o gerenciamento dos dados dos moradores.

### RF-04 - Controle de Acesso

- RF-04-01 - O sistema deve permitir o gerenciamento dos dados dos visitantes.
- RF-04-02 - O sistema deve permitir o gerenciamento dos dados dos prestadores de serviço.
- RF-04-03 - O sistema deve permitir o gerenciamento das altorizações prévias de acesso.
- RF-04-04 - O sistema deve permitir realizar consultas históricas de acesso.

### RF-05 - Gestão de Veículos

- RF-05-01 - O sistema deve permitir o gerenciamento dos dados dos veiculos.
- RF-05-02 - O sistema deve permitir a associação de veículos e usuários.
- RF-05-03 - O sistema deve permitir a associação de veículos a unidades habitacionais.

### RF-06 - Correspondências e Encomendas

- RF-06-01 - O sistema deve permitir o gerenciamento dos dados das encomendas.
- RF-06-02 - O sistema deve notificar os moradores sobre as encomendas recebidas.
- RF-06-03 - O sistema deve permitir anexar comprovantes de entrega.
- RF-06-04 - O sistema deve manter histórico das movimentações.

### RF-07 - Reserva de Áreas Comuns

- RF-07-01 - O sistema deve permitir o gerenciamento dos dados das áreas comuns.
- RF-07-02 - O sistema deve permitir a reserva de áreas comuns.
- RF-07-03 - O sistema deve permitir o cancelamento de reservas.
- RF-07-04 - O sistema deve impedir conflitos entre reservas.

### RF-08 - Gestão de Ocorrências

- RF-08-01 - O sistema deve permitir o gerenciamento dos dados das ocorrências.
- RF-08-02 - O sistema deve permitir a atribuição de usuários para a ocorrência.
- RF-08-03 - O sistema deve permitir o acompanhamento de ocorrências.
- RF-08-04 - O sistema deve notificar sobre ocorrências.

### RF-09 - Manutenção

- RF-09-01 - O sistema deve permitir o gerenciamento dos dados das manutenções.
- RF-09-02 - O sistema deve permitir a atribuição de responsáveis.
- RF-09-03 - o sistema deve permitir o anexo de detalhes dos problemas.
- RF-09-04 - O sistema deve permitir o anexo comprovantes de execução.

### RF-10 - Comunicação

- RF-10-01 - O sistema deve permitir o gerenciamento dos dados dos comunicados.
- RF-10-02 - O sistema deve permitir segmentar destinatários.

### RF-11 - Assembleias

- RF-11-01 - O sistema deve permitir o gerenciamento dos dados das assembleias.
- RF-11-02 - O sistema deve permitir registrar presença em assembleias.
- RF-11-02 - O sistema deve permitir a realização de votações eletrônicas.
- RF-11-03 - O sistema deve permitir a apuração de votos.

### RF-12 - Financeiro

- RF-12-01 - O sistema deve permitir o gerenciamento das cobranças condominiais.

### RF-13 - Administração

- RF-13-01 - o sistema deve permitir o gerenciamento geral de condominios cadastrados no sistema.

## Requisitos não Funcionais

### RNF-01 - Segurança

- RNF-01-01 - O sistema deve utilizar autenticação de usuários.
- RNF-01-02 - O sistema deve armazenar os dados senssíveis utilizando algoritimos criptograficos seguros.
- RNF-01-03 - O sistema deve permitir multiplos fatores de altenticação.
- RNF-01-04 - O sistema deve implementar controle de acesso baseado em perfis e permissões.

### RNF-02 - Desempenho

- RNF-02-01 - O sistema deve responder às operações comuns em até 3 segundos.
- RNF-02-02 - O sistema deve suportar pelo menos 500 usuários simultâneos.
- RNF-02-03 - O sistema deve suportar o armazenamento de mais de 1 milhão de registros de acesso.

### RNF-03 - Disponibilidade

- RNF-03-01 - O sistema deve possuir disponibilidade mínima de 99,5%.
- RNF-03-02 - O sistema não pode ter sua operação suspensa pela falta de conexão com a internet.

### RNF-04 - Usabilidade

- RNF-04-01 - O sistema deve possuir interface responsiva.
- RNF-04-02 - O sistema deve ser utilizavel em smartphones tablets e desktops.
- RNF-04-03 - O sistema deve seguir padrões consistentes de navegação.

### RNF-05 - Escalabilidade

- RNF-05-01 - O sistema deve suportar múltiplos condomínios.
- RNF-05-02 - O sistema deve permitir crescimento sem necessidade de alterações estruturais no banco de dados.
- RNF-05-03 - O sistema deve suportar expansão de módulos.

### RNF-06 - Auditoria e Rastreabilidade

- RNF-06-01 - Todas as operações críticas devem ser auditáveis.
- RNF-06-02 - Nenhum registro auditado poderá ser removido fisicamente.
- RNF-06-03 - O sistema deve manter histórico das alterações relevantes.

### RNF-07 - Compatibilidade

- RNF-07-01 - O sistema deve ser compatível com os principais navegadores modernos.
- RNF-07-02 - O sistema deve disponibilizar API REST para integrações futuras.
