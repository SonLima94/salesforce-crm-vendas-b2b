# Salesforce-CRM-Vendas-B2B
Projeto de implementação de CRM de Vendas B2B no Salesforce (Developer Org).

# 🚀 Projeto Salesforce: CRM de Vendas B2B

Projeto de configuração e automação de um fluxo de vendas B2B desenvolvido em ambiente Developer Org (Playground), focado na administração do Salesforce.

## 📌 Escopo do Negócio
- Padronização das etapas do funil de vendas.
- Automação da atualização do status do cliente após o fechamento da venda.
- Garantia de integridade de dados sobre os motivos de perda de negócios.
- Visibilidade dos indicadores de desempenho da equipe em tempo real.

---

## 🛠️ Configurações Técnicas Realizadas

### 1. Modelo de Dados & Objetos Customizados
- **Account (Conta):** Criados os campos `Tipo de Cliente` (Picklist) e `Segmento` (Picklist).
- **Opportunity (Oportunidade):** Criado o campo `Motivo da Perda` (Picklist) e configurado o tipo de registro `Venda B2B`.

### 2. Automação de Processo (Flow Builder)
- **Tipo:** Record-Triggered Flow (`Oportunidade - Atualizar Conta Ganha`).
- **Regra:** Quando uma oportunidade muda para o estágio **Closed Won**, o campo `Tipo de Cliente` na Conta associada é atualizado automaticamente para **Cliente Ativo**.

### 3. Regra de Validação (Validation Rule)
- **Regra:** `Motivo_Perda_Obrigatorio`.
- **Lógica:** Impede que o usuário salve uma Oportunidade como **Closed Lost** sem selecionar o campo `Motivo da Perda`.

### 4. Segurança e Visibilidade
- **Perfil:** Clonado o perfil `Standard User` para criar o perfil customizado `Representante de Vendas`.
- **Sharing Settings (OWD):** Acesso padrão de Oportunidades alterado para **Private**.

### 5. Relatórios e Dashboards
- Relatório de Oportunidades agrupadas por estágio (Funil de Vendas).
- Painel "Visão Geral de Vendas B2B" com o componente visual configurado.

---

## 📸 Evidências do Projeto

### Fluxo de Automação (Flow Builder)
![Flow Builder](01-flow-builder.png)

### Regra de Validação Bloqueando Registro Sem Motivo
![Validação de Erro](02-validacao-erro.png)

### Painel Executivo (Dashboard)
![Dashboard de Vendas](03-dashboard.png)
