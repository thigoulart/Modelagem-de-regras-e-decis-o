# Atividade Ponderada: Modelagem de regras e decisão

As regras de negócio e as decisões estão associadas ao processo de vendas, conforme modelado pelo grupo Hermes na Sprint 1. As regras e decisões foram desenvolvidas com base no desenho da solução, levando em consideração os gateways e fluxos identificados. 

## Regras de Negócio

| **Identificador** | **Nome**                | **Descrição**                                                                                     | **Módulo**     | **Data de Criação** | **Data da Última Alteração** | **Autor**         | **Versão** | **Dependências**           |
|-------------------|-------------------------|---------------------------------------------------------------------------------------------------|----------------|---------------------|-----------------------------|-------------------|------------|----------------------------|
| VE001             | Aprovação de Crédito     | Se o crédito do cliente for aprovado, emita a fatura. Caso contrário, formalize o contrato.       | Vendas         | 23/08/2024          | 23/08/2024                  | Thiago Goulart     | 1.0        | Processo de Avaliação de Crédito |
| VE002             | Conformidade Fiscal      | Após a análise de conformidade fiscal, configure o software. Se não estiver em conformidade, formalize o contrato. | Vendas         | 23/08/2024          | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão Fiscal   |
| VE003             | Solicitação ao Fornecedor| Quando o pedido for confirmado, solicite ao fornecedor. Se não, volte ao cliente para reconfirmação. | Vendas         | 23/08/2024          | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Pedidos|
| VE004             | Aprovação do Fornecedor  | Se o fornecedor aprovar a solicitação, prepare a entrega. Caso contrário, reavalie a solicitação. | Vendas         | 23/08/2024          | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Fornecedores |
| VE005             | Formalização de Contrato | Formalize ou revise o contrato sempre que houver impedimento na aprovação de crédito ou conformidade fiscal. | Vendas         | 23/08/2024          | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Contratos |


## Decisões de Negócio (DMN)

As tabelas a seguir mostram as decisões de negócio modeladas com base nas regras estabelecidas. Cada tabela DMN reflete uma parte específica do processo de vendas e ajuda a visualizar as decisões que precisam ser tomadas com base nas condições especificadas. Abaixo, há as decisões do processo de vendas resumido do Grupo Hermes (a maioria de acordo com os gateways do BPMN produzido durante a sprint 1):

<div align="center">
<sub>Figura 1 - DMN Geral</sub>
<img src="/imagens/processo.png" width="100%" >
<sup>Fonte: Material produzido Thiago Goulart (2024)</sup>
</div>

#### 1. Tabela DMN: Aprovação de Crédito

Esta tabela DMN detalha a decisão sobre a aprovação de crédito do cliente. Dependendo da resposta sobre a aprovação do crédito, a ação apropriada é tomada.

<div align="center">
<sub>Figura 2 - Aprovação de Crédito</sub>
<img src="/imagens/decisao1.png" width="100%" >
<sup>Fonte: Material produzido Thiago Goulart (2024)</sup>
</div>


### 2. Tabela DMN: Conformidade Fiscal

Esta tabela DMN mostra a decisão sobre a conformidade fiscal. A ação a ser tomada depende de a conformidade fiscal estar ou não adequada.

<div align="center">
<sub>Figura 3 - Conformidade Fiscal</sub>
<img src="/imagens/decisao2.png" width="100%" >
<sup>Fonte: Material produzido Thiago Goulart (2024)</sup>
</div>

### 3. Tabela DMN: Confirmação de Pedido

Esta tabela DMN trata da decisão sobre a confirmação de pedidos. Dependendo da confirmação do pedido, a ação apropriada é tomada.

<div align="center">
<sub>Figura 4 - Confirmação de Pedido</sub>
<img src="/imagens/decisao3.png" width="100%" >
<sup>Fonte: Material produzido Thiago Goulart (2024)</sup>
</div>

### 4. Tabela DMN: Aprovação pelo Fornecedor

Esta tabela DMN mostra a decisão sobre a aprovação pelo fornecedor. Dependendo da resposta do fornecedor, a ação apropriada é tomada.

<div align="center">
<sub>Figura 5 - Aprovação pelo Fornecedor</sub>
<img src="/imagens/decisao4.png" width="100%" >
<sup>Fonte: Material produzido Thiago Goulart (2024)</sup>
</div>

### 5. Tabela DMN: Formalização de Contrato

<div align="center">
<sub>Figura 6 - Formalização de Contrato</sub>
<img src="/imagens/decisao4.png" width="100%" >
<sup>Fonte: Material produzido Thiago Goulart (2024)</sup>
</div>
