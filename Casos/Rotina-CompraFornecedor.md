-------------------------------------------
## ✅ CENÁRIO 03 – COMPRA POR FORNECEDOR
-------------------------------------------
### Caso de Teste 01: Compra concluída com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT01	 | Compra lançada, estoque atualizado e caixa alimentado.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Fornecedor cadastrado.|
|Produto cadastrado.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário cria nova compra
E adiciona produtos
QUANDO finalizar compra

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Compra CONFIRMADA.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1rX7AnjNAykIMzZIeQk48FN95bRTkd-Mv/view?usp=drive_link)|

### Caso de Teste 02: Fornecedor inexistente
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT02	 | Deve impedir compra sem fornecedor.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que usuário tenta criar compra sem fornecedor
QUANDO clicar em “Salvar”
ENTÃO sistema deve bloquear.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Mensagem “Fornecedor obrigatório”.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1ezbHxNDlMlLz-iLEqSowuPhbANsZj0P-/view?usp=drive_link)|

### Caso de Teste 03: Tipo de documento inválido para compra a prazo
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT03	 | Sistema deve recusar documento que não alimenta caixa.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Compra marcada como “A Prazo”.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário tenta inserir tipo de documento não que alimenta caixa
QUANDO selecionar a opção proibida
ENTÃO deve exibir alerta.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Documento não deve ser aceito.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video]()|