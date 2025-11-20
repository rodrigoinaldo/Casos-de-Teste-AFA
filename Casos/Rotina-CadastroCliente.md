-------------------------------------------
## ✅ CENÁRIO 04 – GESTÃO DE CLIENTES
-------------------------------------------
### Caso de Teste 01: Cadastro de cliente PF com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT01	 | Cadastro básico deve ser salvo corretamente.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que usuário clica em “Novo”
E preenche os campos obrigatórios
QUANDO clicar em Salvar
ENTÃO cliente deve aparecer na lista.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Cadastro salvo.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1u0Ir-83EU1kye06pfUDOYomo8gMrsAcr/view?usp=drive_link)|

### Caso de Teste 02: Tentativa de salvar cliente sem campos obrigatórios
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT02	 | Sistema deve impedir cadastro incompleto.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário deixa Nome ou CEP vazio
QUANDO tentar salvar
ENTÃO deve exibir alerta.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Cadastro bloqueado.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/11WFJx6mwnntQj7kaSU9FAXfNBjExIf4m/view?usp=drive_link)|

### Caso de Teste 03: Venda acima do limite de crédito
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT03	 | Sistema alerta e redireciona para Contas a Receber.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente com limite de crédito.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o cliente tem limite de R$100
QUANDO a venda ultrapassar esse valor
ENTÃO sistema alerta e abre fluxo de contas a receber.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Alerta exibido.|
|Venda permitida após confirmação.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video]()|

### Caso de Teste 04: Cadastrar dependente corretamente
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT04	 | Dependente deve ser vinculado ao cliente.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente principal já cadastrado.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que usuário acessa aba Dependentes
E clica em “Novo”
QUANDO selecionar cliente dependente
ENTÃO ele deve ser vinculado.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Dependente aparece listado.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1kzgifWJPTEOtMCtc9gknRgcpJpY3pKhD/view?usp=drive_link)|