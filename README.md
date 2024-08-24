# Atividade Ponderada: Modelagem de regras e decisão

Esta documentação descreve as regras de negócio e as decisões associadas ao processo de vendas, conforme modelado pelo grupo Hermes na Sprint 1. As regras e decisões foram desenvolvidas com base no desenho da solução, levando em consideração os gateways e fluxos identificados. O objetivo é garantir que o processo de vendas seja executado de acordo com os padrões estabelecidos e otimizar o fluxo de trabalho.

## Regras de Negócio

| **Identificador** | **Nome**                | **Descrição**                                                                                     | **Módulo**     | **Data de Criação** | **Ator**                | **Data da Última Alteração** | **Autor**         | **Versão** | **Dependências**           |
|-------------------|-------------------------|---------------------------------------------------------------------------------------------------|----------------|---------------------|-------------------------|-----------------------------|-------------------|------------|----------------------------|
| VE001             | Aprovação de Crédito     | Se o crédito do cliente for aprovado, emita a fatura. Caso contrário, formalize o contrato.       | Vendas         | 23/08/2024          | Gerente de Vendas        | 23/08/2024                  | Thiago Goulart     | 1.0        | Processo de Avaliação de Crédito |
| VE002             | Conformidade Fiscal      | Após a análise de conformidade fiscal, configure o software. Se não estiver em conformidade, formalize o contrato. | Vendas         | 23/08/2024          | Analista Fiscal          | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão Fiscal   |
| VE003             | Solicitação ao Fornecedor| Quando o pedido for confirmado, solicite ao fornecedor. Se não, volte ao cliente para reconfirmação. | Vendas         | 23/08/2024          | Assistente de Compras    | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Pedidos|
| VE004             | Aprovação do Fornecedor  | Se o fornecedor aprovar a solicitação, prepare a entrega. Caso contrário, reavalie a solicitação. | Vendas         | 23/08/2024          | Coordenador de Logística | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Fornecedores |
| VE005             | Formalização de Contrato | Formalize ou revise o contrato sempre que houver impedimento na aprovação de crédito ou conformidade fiscal. | Vendas         | 23/08/2024          | Gerente de Contas        | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Contratos |

## Decisões de Negócio (DMN)

As tabelas a seguir mostram as decisões de negócio modeladas com base nas regras estabelecidas. Cada tabela DMN reflete uma parte específica do processo de vendas e ajuda a visualizar as decisões que precisam ser tomadas com base nas condições especificadas.

#### 1. Tabela DMN: Aprovação de Crédito

Esta tabela DMN detalha a decisão sobre a aprovação de crédito do cliente. Dependendo da resposta sobre a aprovação do crédito, a ação apropriada é tomada.

| **Decisão 1: Aprovação de Crédito**  | **Hit policy:** First |
|--------------------------------------|-----------------------|
| **When**                             | **Then**              | **Annotations**                         |
| Crédito Aprovado == "Sim"            | Emitir Fatura         | Prosseguir com a venda                   |
| Crédito Aprovado == "Não"            | Formalizar Contrato   | Necessário formalizar contrato           |

![Tabela DMN: Aprovação de Crédito](link-para-imagem-tabela-dmn-1)


### 2. Tabela DMN: Conformidade Fiscal

Esta tabela DMN mostra a decisão sobre a conformidade fiscal. A ação a ser tomada depende de a conformidade fiscal estar ou não adequada.

| **Decisão 2: Conformidade Fiscal**   | **Hit policy:** First |
|-------------------------------------|-----------------------|
| **When**                            | **Then**              | **Annotations**                         |
| Conformidade Fiscal == "Sim"        | Configurar Software   | Prosseguir com a configuração            |
| Conformidade Fiscal == "Não"        | Formalizar Contrato   | Revisar conformidade fiscal              |

![Tabela DMN: Conformidade Fiscal](link-para-imagem-tabela-dmn-2)

### 3. Tabela DMN: Confirmação de Pedido

Esta tabela DMN trata da decisão sobre a confirmação de pedidos. Dependendo da confirmação do pedido, a ação apropriada é tomada.

| **Decisão 3: Confirmação de Pedido** | **Hit policy:** First |
|-------------------------------------|-----------------------|
| **When**                            | **Then**              | **Annotations**                         |
| Pedido Confirmado == "Sim"          | Solicitar ao Fornecedor | Pedido confirmado, prossiga              |
| Pedido Confirmado == "Não"          | Reconfirmar Pedido    | Reconfirmar pedido com o cliente         |

![Tabela DMN: Confirmação de Pedido](link-para-imagem-tabela-dmn-3)

### 4. Tabela DMN: Aprovação pelo Fornecedor

Esta tabela DMN mostra a decisão sobre a aprovação pelo fornecedor. Dependendo da resposta do fornecedor, a ação apropriada é tomada.

| **Decisão 4: Aprovação pelo Fornecedor**  | **Hit policy:** First |
|------------------------------------------|-----------------------|
| **When**                                 | **Then**              | **Annotations**                         |
| Aprovação do Fornecedor == "Sim"         | Preparar Entrega      | Pedido aprovado, prossiga com entrega   |
| Aprovação do Fornecedor == "Não"         | Reavaliar Pedido      | Reavaliar pedido com o fornecedor       |

![Tabela DMN: Aprovação pelo Fornecedor](link-para-imagem-tabela-dmn-4)

### 5. Tabela DMN: Formalização de Contrato

Esta tabela DMN detalha as decisões relacionadas à formalização de contratos, dependendo da aprovação de crédito e conformidade fiscal.

| **Decisão 5: Formalização de Contrato**   | **Hit policy:** First |
|------------------------------------------|-----------------------|
| **When**                                 | **Then**              | **Annotations**                         |
| Crédito Aprovado == "Não"                | Formalizar Contrato   | Crédito reprovado, formalizar contrato  |
| Crédito Aprovado == "Sim" AND Conformidade Fiscal == "Não" | Revisar Contrato | Revisar contrato devido à não conformidade fiscal |
| Crédito Aprovado == "Sim" AND Conformidade Fiscal == "Sim" | Concluir Venda   | Todas as condições validadas, concluir venda |

![Tabela DMN: Formalização de Contrato](link-para-imagem-tabela-dmn-5)

