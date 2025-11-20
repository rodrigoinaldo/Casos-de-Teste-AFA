-------------------------------------------
## ✅ CENÁRIO 02 – PROCESSAMENTO DE VENDA (PDV)
-------------------------------------------
### Caso de Teste 01: Venda completa com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT01	 | Venda registrada, estoque reduzido e caixa alimentado.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente, funcionário e produtos cadastrados.|
|Produto com estoque suficiente.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário clica em “Novo” na tela de vendas
E escolhe cliente, funcionário e data
E insere produtos
QUANDO finalizar e salvar
ENTÃO a venda deve aparecer no Livro Caixa.

| **Critérios de Aceitação**                                         |
| :------------------------------------------------------------ |
|Estoque atualizado.|
|Caixa alimentado.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1_yNsav6wwFZB94xsF3bJZR41fmeDVMQe/view?usp=drive_link)|

### Caso de Teste 02: Produto sem estoque
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT02	 | Sistema deve permitir venda sem estoque.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Produto com quantidade = 0.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário tenta incluir o produto
QUANDO selecionar quantidade
O sistema deve permitir proceguir a venda.
Deve estar no Livro caixa

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Produto deve entrar na venda.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1FvoupSZmtUKGDB_QdOKaN9Qzxb9EraV9/view?usp=drive_link)|

### Caso de Teste 03: Permitir aplicar apenas desconto total na hora da venda 
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT03	 | Sistema deve permitir desconto na venda.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Venda com desconto total.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que a venda possui produto sem desconto
QUANDO tentar aplicar desconto geral
ENTÃO deve permitir.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Desconto total autoizado.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1HVLd__TIMdahcRPspC9NtnQzcIAVfbvm/view?usp=drive_link)|

### Caso de Teste 04: Finalizar venda sem selecionar tipo de documento
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT04	 | Sistema deve impedir finalização sem forma de pagamento.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Venda pronta para finalizar.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário está na tela final
QUANDO clicar em “Salvar” sem escolher tipo de documento
ENTÃO deve exibir erro.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Finalização bloqueada.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1lRhJPoKqw2ZBasUMv8YRhRINuo9Qnhnb/view?usp=drive_link)|
