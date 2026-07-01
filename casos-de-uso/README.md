# Casos de Uso

> **Observação:** Todos os atores herdam as funcionalidades do ator **Usuário**.

## Usuário

### Conta

- Manter dados pessoais
- Alterar senha

---

## Administrador do Sistema

### Gestão da Plataforma

- Manter condomínios
- Manter gestores dos condomínios

### Administração

- Executar todas as funcionalidades disponíveis para os demais atores

---

## Gestor do Condomínio

### Estrutura do Condomínio

- Manter agrupamentos de unidades habitacionais
- Manter unidades habitacionais
- Manter moradores
- Manter equipe
- Consultar veículos cadastrados

### Comunicados

- Manter comunicados

### Ocorrências

- Manter ocorrências
- Atribuir responsável por ocorrências

### Manutenções

- Manter manutenções
- Atribuir manutencista

### Áreas Comuns

- Manter áreas comuns
- Aprovar reservas

---

## Morador

### Unidade Habitacional

- Manter membros da unidade habitacional
- Manter veículos da unidade habitacional

### Controle de Visitantes

- Manter visitantes
- Aprovar visitantes
- Gerenciar autorizações permanentes
- Consultar histórico de acessos

### Áreas Comuns

- Solicitar reserva de área comum

### Ocorrências

- Abrir ocorrências
- Acompanhar ocorrências

### Comunicados

- Consultar comunicados

### Encomendas

- Consultar encomendas

---

## Porteiro

### Controle de Acesso

- Registrar entrada e saída de moradores
- Registrar entrada e saída de visitantes
- Registrar entrada e saída de veículos

### Encomendas

- Registrar recebimento de encomendas
- Registrar entrega de encomendas

---

## Segurança

### Ocorrências

- Atender ocorrências
- Atualizar andamento das ocorrências
- Encerrar ocorrências

---

## Manutencista

### Manutenções

- Atender manutenções
- Atualizar andamento das manutenções
- Encerrar manutenções

---

# Premissas do Sistema

- O Administrador do Sistema possui acesso irrestrito à plataforma e pode executar todas as funcionalidades disponíveis aos demais atores.
- O Gestor do Condomínio é responsável pela administração do condomínio sob sua gestão.
- O Gestor cadastra as unidades habitacionais e o primeiro morador (titular) de cada unidade.
- Após o cadastro inicial, o morador titular torna-se responsável por manter os membros da unidade habitacional, os veículos vinculados à unidade e os visitantes autorizados.
- O Porteiro é responsável pelo controle operacional de acessos e encomendas.
- O Segurança atua apenas sobre ocorrências atribuídas a ele.
- O Manutencista atua apenas sobre manutenções atribuídas a ele.
