# 📘 Casos de Teste – Sistema AFA

Documentação completa de testes funcionais do sistema, organizada por módulos, contendo casos que dão certo e casos que dão errado, seguindo boas práticas e cenários realistas baseados no funcionamento do AFA.

## 🟦 CENÁRIO 01 – Inventário de Estoque
### ✅ Caso de Teste 01: Importar XML válido e gerar compra
ID	Descrição
C01-CT01	Importação de XML válida deve alimentar o estoque.
Pré-condições

XML válido.

Passos

DADO que o usuário acessa Pedidos > Importar XML de Compra

E preenche CFOP, Grupo e ST

E importa um XML válido

QUANDO clicar em Gerar Compra e finalizar

ENTÃO estoque é atualizado e compra fica CONFIRMADA

Critérios de Aceitação

Produtos adicionados ao estoque.

### ❌ Caso de Teste 02: Importar XML inválido
ID	Descrição
C01-CT02	Sistema deve rejeitar XML inválido.
Pré-condições

XML corrompido ou incompleto.

Passos

DADO que o usuário tenta importar XML inválido

QUANDO clicar em Importar

ENTÃO deve aparecer mensagem de erro

Critérios de Aceitação

Importação bloqueada.

### ❌ Caso de Teste 03: Importação sem preencher CFOP ou Grupo
ID	Descrição
C01-CT03	Sistema deve exigir CFOP e Grupo.
Passos

DADO que o usuário deixa campos obrigatórios vazios

QUANDO tentar importar

ENTÃO deve exibir erro “campo obrigatório”

### ⚠️ Caso de Teste 04: Gerar compra mas não confirmar entrada
ID	Descrição
C01-CT04	Compra sem confirmação não deve alterar estoque.
Passos

DADO que a compra foi gerada

QUANDO o usuário sair sem confirmar

ENTÃO estoque permanece inalterado

## 🟦 CENÁRIO 02 – Processamento de Venda (PDV)
### ✅ Caso de Teste 01: Venda completa com sucesso
ID	Descrição
C02-CT01	Venda deve ser registrada e alimentar o caixa.
Pré-condições

Cliente, funcionário e produtos cadastrados.

Passos

DADO que o usuário cria nova venda

E insere os produtos

QUANDO finalizar

ENTÃO venda aparece no Livro Caixa

### ❌ Caso de Teste 02: Produto sem estoque
ID	Descrição
C02-CT02	Sistema não deve permitir venda sem estoque.
Passos

DADO que o usuário seleciona um produto sem estoque

ENTÃO sistema deve exibir “estoque insuficiente”

### ❌ Caso de Teste 03: Desconto geral quando já existe desconto por item
ID	Descrição
C02-CT03	Sistema deve bloquear desconto total duplicado.
Passos

DADO que existe desconto no item

QUANDO tentar aplicar desconto total

ENTÃO sistema deve alertar e bloquear

### ❌ Caso de Teste 04: Finalizar venda sem selecionar tipo de documento
ID	Descrição
C02-CT04	Finalização deve ser bloqueada sem forma de pagamento.
Passos

DADO que a venda está pronta

QUANDO clicar em salvar sem tipo de documento

ENTÃO sistema deve exibir erro

## 🟦 CENÁRIO 03 – Compra por Fornecedor
### ✅ Caso de Teste 01: Compra concluída com sucesso
ID	Descrição
C03-CT01	Compra gera entrada no estoque.
Passos

DADO que uma compra é criada

E produtos são adicionados

ENTÃO estoque é atualizado após confirmar

### ❌ Caso de Teste 02: Fornecedor inexistente
ID	Descrição
C03-CT02	Compra deve exigir fornecedor.
Passos

DADO que o usuário tenta criar compra sem fornecedor

ENTÃO sistema bloqueia com mensagem

### ❌ Caso de Teste 03: Tipo de documento inválido em compra a prazo
ID	Descrição
C03-CT03	Documento que alimenta caixa não deve ser aceito na compra a prazo.
Passos

DADO que compra é “A Prazo”

QUANDO usuário tenta inserir documento inválido

ENTÃO sistema exibe alerta

## 🟦 CENÁRIO 04 – Gestão de Clientes
### ✅ Caso de Teste 01: Cadastro de cliente PF
ID	Descrição
C04-CT01	Cadastro deve ser salvo com sucesso.
Passos

DADO que o usuário preenche nome, tipo e endereço

QUANDO clicar em salvar

ENTÃO cliente aparece na listagem

### ❌ Caso de Teste 02: Falta de campos obrigatórios
ID	Descrição
C04-CT02	Sistema deve impedir cadastro incompleto.
Passos

DADO que o usuário não preenche nome/CEP

ENTÃO sistema exibe erro e não salva

### ⚠️ Caso de Teste 03: Venda acima do limite de crédito
ID	Descrição
C04-CT03	Sistema deve alertar e redirecionar para Contas a Receber.
Passos

DADO cliente com limite de crédito

QUANDO venda ultrapassar esse valor

ENTÃO exibir alerta e continuar fluxo financeiro

### ✅ Caso de Teste 04: Cadastro de dependente
ID	Descrição
C04-CT04	Dependente vinculado corretamente.
Passos

DADO que o usuário acessa aba Dependentes

QUANDO cadastrar dependente

ENTÃO dependente aparece listado

## 🟦 CENÁRIO 05 – Fechamento de Caixa
### ✅ Caso de Teste 01: Fechar caixa com sucesso
ID	Descrição
C05-CT01	Caixa do dia deve ser finalizado.
Passos

DADO que há vendas no dia

QUANDO o usuário clicar em Fechar Caixa

ENTÃO caixa fica bloqueado para novas ações

### ❌ Caso de Teste 02: Tentar fechar caixa sem vendas
ID	Descrição
C05-CT02	Sistema deve impedir fechamento vazio.
Passos

DADO que não houve vendas

QUANDO tentar fechar

ENTÃO sistema exibe erro

### ✅ Caso de Teste 03: Retirada de valores
ID	Descrição
C05-CT03	Retirada registrada no Livro Caixa.
Passos

DADO que usuário acessa Retirar Valores

QUANDO preencher campos obrigatórios

ENTÃO retirada é registrada

### ❌ Caso de Teste 04: Retirada sem preencher campos obrigatórios
ID	Descrição
C05-CT04	Sistema deve bloquear retirada incompleta.
Passos

DADO que o usuário tenta salvar sem valor ou documento

ENTÃO sistema exibe erro
