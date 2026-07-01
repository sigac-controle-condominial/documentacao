# UC-024 – Abrir Ocorrências

## Objetivo
Permitir que o morador registre uma ocorrência para comunicar problemas, incidentes ou solicitações de providência relacionados ao condomínio.

## Atores
- Morador

## Interessados e Interesses
- Morador: registrar a demanda com clareza e acompanhar sua tratativa.
- Gestor do Condomínio: receber informações suficientes para triagem e encaminhamento.
- Equipe responsável: obter detalhes que viabilizem o atendimento.
- Sistema: manter rastreabilidade completa do ciclo de vida da ocorrência.

## Gatilho
O caso de uso é iniciado quando o morador identifica uma situação que precisa ser tratada pela administração ou equipe operacional.

## Pré-condições
- Usuário autenticado.
- Morador vinculado a unidade habitacional ativa.
- Morador possui permissão para abrir ocorrências.

## Pós-condições
### Em caso de sucesso
- A ocorrência é registrada com identificação, classificação inicial e status compatível com a triagem.
- O histórico inicial da abertura fica disponível para acompanhamento.
- O gestor ou fila responsável pode visualizar a nova ocorrência para providências.

### Em caso de falha
- Nenhuma ocorrência é criada enquanto houver campos obrigatórios inválidos ou ausentes.
- Arquivos ou dados válidos previamente informados são preservados, quando aplicável.

## Fluxo Principal
1. O morador acessa a funcionalidade de abertura de ocorrências.
2. O sistema apresenta o formulário para registro da demanda.
3. O morador informa categoria, assunto, descrição, local, prioridade percebida e anexos, quando aplicável.
4. O sistema valida os campos obrigatórios e a consistência das informações.
5. O morador confirma o registro.
6. O sistema gera a ocorrência, registra a data de abertura e apresenta o protocolo ao morador.

## Fluxos Alternativos
### FA-01 – Anexar evidências
1. O morador inclui imagens ou documentos para complementar a descrição.
2. O sistema valida formato e tamanho dos anexos.
3. Os anexos são associados ao registro da ocorrência.

### FA-02 – Ocorrência semelhante já aberta
1. O sistema identifica ocorrência em aberto com dados semelhantes.
2. O sistema informa o morador e permite continuar ou cancelar a abertura.
3. Se o morador optar por continuar, o fluxo segue normalmente.

## Fluxos de Exceção
### FE-01 – Falha ao registrar a ocorrência
1. O sistema não gera o protocolo da demanda.
2. O erro técnico é registrado para análise.
3. O morador é informado sobre a indisponibilidade temporária.

## Regras de Negócio
- A ocorrência deve ser vinculada à unidade habitacional do morador solicitante.
- Categorias e prioridades devem obedecer à tabela configurada pelo condomínio.
- Toda ocorrência aberta deve possuir histórico inicial com data, hora e autor do registro.

## Requisitos Especiais
- O formulário deve orientar o morador sobre como descrever a demanda de forma objetiva.
- O protocolo da ocorrência deve ficar disponível para consultas futuras.
- Anexos devem ser armazenados de forma segura e vinculados ao histórico da ocorrência.

## Requisitos Relacionados
- UC-011 – Manter Ocorrências
- UC-025 – Acompanhar Ocorrências
- UC-012 – Atribuir Responsável por Ocorrências
