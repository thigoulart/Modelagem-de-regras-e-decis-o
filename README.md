# Atividade Ponderada: Modelagem de regras e decisão

## Regras de Negócio

| **Identificador** | **Nome**                | **Descrição**                                                                                     | **Módulo**     | **Data de Criação** | **Ator**                | **Data da Última Alteração** | **Autor**         | **Versão** | **Dependências**           |
|-------------------|-------------------------|---------------------------------------------------------------------------------------------------|----------------|---------------------|-------------------------|-----------------------------|-------------------|------------|----------------------------|
| VE001             | Aprovação de Crédito     | Se o crédito do cliente for aprovado, emita a fatura. Caso contrário, formalize o contrato.       | Vendas         | 23/08/2024          | Gerente de Vendas        | 23/08/2024                  | Thiago Goulart     | 1.0        | Processo de Avaliação de Crédito |
| VE002             | Conformidade Fiscal      | Após a análise de conformidade fiscal, configure o software. Se não estiver em conformidade, formalize o contrato. | Vendas         | 23/08/2024          | Analista Fiscal          | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão Fiscal   |
| VE003             | Solicitação ao Fornecedor| Quando o pedido for confirmado, solicite ao fornecedor. Se não, volte ao cliente para reconfirmação. | Vendas         | 23/08/2024          | Assistente de Compras    | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Pedidos|
| VE004             | Aprovação do Fornecedor  | Se o fornecedor aprovar a solicitação, prepare a entrega. Caso contrário, reavalie a solicitação. | Vendas         | 23/08/2024          | Coordenador de Logística | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Fornecedores |
| VE005             | Formalização de Contrato | Formalize ou revise o contrato sempre que houver impedimento na aprovação de crédito ou conformidade fiscal. | Vendas         | 23/08/2024          | Gerente de Contas        | 23/08/2024                  | Thiago Goulart     | 1.0        | Sistema de Gestão de Contratos |


