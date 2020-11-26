# Micro Sistema de Gestão



### OBJETIVO

Objetivo do  projeto...

### ESTUDO DE CASO

Estudo de caso 

## ANALISE DE REQUERIMENTOS

### REQUERIMENTOS DE FUNCIONALIDADES

Requerimentos...

### PLANEJAMENTO DE SEGURANÇA

Segurança....

### AMBIENTE DE PRODUÇÃO REQUERIDA

Servidor Linux
Sercidor Apache/Nginx
Servidor PHP 5 / 7
Servidor MySQL 5 / 8

### FUNCIONALIDADE ( MENUS / MÓDULOS )

### Portal Administração

* **Cadastros**
  * Ativos - *(Básico/Manutenções/Ocorrências)*
  * Clientes - *(Básico/Resumo de Vendas/Resumo/Financeiro/Contatos/Ocorrências)*
  * Fornecedores - *(Básico/Resumo de Compras/Resumo Financeiro/Contatos/Ocorrências)*
  * Funcionários - *(Básico/Registro/Ficha Financeira/Dependentes/Ocorrências)*
  * Motoristas - *(Básico/Entregas/Ocorrências)*
  * Produtos - *(Básico/Tributação/Estoques/Custos/Estrutura/Ocorrências)*
  * Veículos - *(Básico/Abastecimentos/Manutenções/Ocorrências)*
  * Vendedores - *(Básico/Resumo de Vendas/Metas/Clientes/Ocorrências)*
  * **Tabelas**
    * **Genérica**
      * Cor
      * NCM
      * País
      * Região (Rotas)
      * Segmento
      * Unidade
    * **Produto**
      * Armazêm
      * Grupo
      * Origem
      * Tipo
    * **Veículos**
      * Carroceria
      * Marca
      * Rodado
    * **Financeiro**
      * Contas
      * Condição de Pagamento
      * Tipo de Documento
    * **Vendas**
      * Tabela de Preços
      * Produtos
    * **RH**
      * Cargos 
      * Departamentos
      * Funções 
* **Ativos**
  * Check-List
  * Ordem de Serviço
  * Manutenção
  * **Comodato**
    * Movimentos 
    * Contrato
    * Anexo I 
    * Anexo II
    * Retirada 
* **Compras**
  * Cotação
  * Entradas
  * Pedidos 
  * Solicitações
* **Estoques**
  * Abaixo do Mínimo
  * Movimentos Internos
  * Saldos
  * Transferências
* **Expedição**
  * Cargas
  * Rotas
* **Faturamento**
  * Cotação
  * Pedidos 
  * Faturamento 
* **Financeiro**
  * Bancos
  * Receber 
  * Pagar
  * Movimento 
    * **Cobrança**
      * Liquidações
      * Cobranças
* **Frota**
  * Abastecimentos 
  * Manutenção
  * Pneus 
* **Produção**
  * Apontamento
  * Custos
  * Empenhos
  * Estrutura
  * Ordens de Produção
* **RH**
  * Cartão de Ponto Avulso
  * Movimento Financeiro
  * Ocorrências
  * Recibo de Pagamento Avulso
  * Resumo da Folha
  * Rescisão Avulsa
* **Vendas**
  * CRM
  * Metas
* **Configurações**
  * Empresas
  * Parametros



### Portal Cliente

**Menu**

* Dados Cadastrais - *(Consulta)*
* Lista de Produtos - *(Consulta)*
* Pedido de Compra - *(Consulta/Inclusão)*

### Portal Funcionários

**Menu**

* Dados Cadastrais - *(Consulta)*
* Extrato de Pagamento - *(Consulta)*



### Portal Fornecedores

**Menu**

* Dados Cadastrais - *(Consulta)*
* Pedidos - *(Consulta)*

##DIAGRAMA DE FLUXO DE DADOS

###PADRÃO DE NOMES DE CAMPOS E TABELAS

**Nome de Tabelas**
1)  CLIENTES
2)  PEDIDO_VENDAS
3)  PEDIDO_VENDAS_DETALHE

**Nome de Campos**
1)  CLIE_ID -> CLIENTES
2)  CLIE_NOME -> CLIENTES
3)  CLIE_DT_COMPRA -> CLIENTES  (DATA ULTIMA COMPRA)
4)  CLIE_VLR_COMPRA -> CLIENTES  (VALOR ULTIMA COMPRA)
5)  PEVE_NUMERO -> PEDIDO_VENDAS (NUMERO PEDIDO)
6)  PVD_QTD -> PEDIDO_VENDAS_DETALHE (QUANTIDADE)

**Abreviaturas**
DT = DATA
NRO = NUMERO
VLR = VALOR
QTD = QUANTIDADE
END = ENDERECO

##MODELO DE RELACIONAMENTO DE TABELAS

### ESTRUTURA DAS TABELAS UTILIZADAS




#### EMPRESA

Description: *Cadastro de Empresas/FIliais.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME             | T    | S    | D    | DESCRIPTION      | PK   | NN   | IN   | NOTE |
| ---------------- | ---- | ---- | ---- | ---------------- | ---- | ---- | ---- | ---- |
| EMPR_ID          | I    |      |      | ID               | X    |      |      |      |
| EMPR_RAZAO       | V    | 100  |      | Razão Social     |      | X    |      |      |
| EMPR_NOME        | V    | 50   |      | Nome de Fantasia |      | X    |      |      |
| EMPR_ENDERECO    | V    | 100  |      | Endereço         |      |      |      |      |
| EMPR_COMPLEMENTO | V    | 50   |      | Complemento      |      |      |      |      |
| EMPR_UF          | C    | 02   |      | UF               |      |      |      |      |
| EMPR_MUNICIPIO   | V    | 50   |      | Cidade/Municipio |      |      |      |      |
| EMPR_BAIRRO      | V    | 30   |      | Bairro           |      |      |      |      |
| EMPR_CEP         | V    | 10   |      | CEP              |      |      |      |      |
| EMPR_TELEFONE    | V    | 15   |      | Telefone         |      |      |      |      |
| EMPR_CNPJCPF     | V    | 20   |      | CNPJ/CPF         |      |      |      |      |
| EMPR_IERG        | V    | 20   |      | IE / RG          |      |      |      |      |
| EMPR_LOGO        | B    |      |      | Logo             |      |      |      |      |
| EMPR_OBS         | M    |      |      | Observação       |      |      |      |      |



#### EMPRESA_SOCIOS

Description: *Cadastro de Sócios das Empresas/FIliais.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME       | T    | S    | D    | DESCRIPTION | PK   | NN   | IN   | NOTE |
| ---------- | ---- | ---- | ---- | ----------- | ---- | ---- | ---- | ---- |
| EMSO_ID    | I    |      |      | ID          | X    |      |      |      |
| -> EMPR_ID | I    |      |      | ID Empresa  |      | X    |      |      |
| EMSO_CPF   | V    | 20   |      | CPF         | X    | X    |      |      |
| EMSO_NOME  | V    | 100  |      | Nome        |      | X    |      |      |
| EMSO_QUOTA | N    | 05   | 02   | % Quota     |      |      |      |      |






#### REGIAO

Description: *Cadastro de Região de Venda.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION      | PK   | NN   | IN   | NOTE   |
| -------------- | ---- | ---- | ---- | ---------------- | ---- | ---- | ---- | ------ |
| REGI_ID        | I    |      |      | ID               | X    |      |      |        |
| -> EMPR_ID     | I    |      |      | ID Empresa       |      | X    |      |        |
| REGI_CODIGO    | I    |      |      | Código da Região |      | X    |      |        |
| REGI_DESCRICAO | V    | 50   |      | Descrição        |      | X    |      |        |
| REGI_OBS       | M    |      |      | Observação       |      |      |      |        |
| REGI_ATIVO     | C    | 01   |      | Ativo            |      |      |      | S ou N |


> ATIVO = (S=Sim, N=Não)




#### PAIS (SYA)

Description: *Tabela de Países.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME       | T    | S    | D    | DESCRIPTION | PK   | NN   | IN   | NOTE |
| ---------- | ---- | ---- | ---- | ----------- | ---- | ---- | ---- | ---- |
| PAIS_ID    | I    |      |      | ID          | X    |      |      |      |
| PAIS_NOME  | V    | 50   |      | Nome        |      | X    |      |      |
| PAIS_SIGLA | C    | 03   |      | Sigla       |      | X    |      |      |






#### VENDEDORES (SA3)

Description: *Cadastro de Vendedores.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME             | T    | S    | D    | DESCRIPTION           | PK   | NN   | IN   | NOTE         |
| ---------------- | ---- | ---- | ---- | --------------------- | ---- | ---- | ---- | ------------ |
| VEND_ID          | I    |      |      | ID                    | X    |      |      |              |
| -> EMPR_ID       | I    |      |      | ID Empresa            |      | X    |      |              |
| VEND_CODIGO      | I    |      |      | ID Vendedor           |      | X    |      |              |
| VEND_ATIVO       | C    | 01   |      | Ativo                 |      |      |      | S=Sim, N=Nao |
| VEND_NOME        | V    | 100  |      | Nome                  |      | X    |      |              |
| VEND_APELIDO     | V    | 20   |      | Nome Social           |      |      |      |              |
| VEND_ENDERECO    | V    | 100  |      | Endereço              |      |      |      |              |
| VEND_BAIRRO      | V    | 30   |      | Bairro                |      |      |      |              |
| VEND_MUNICIPIO   | V    | 50   |      | CIdade/Municipio      |      |      |      |              |
| VEND_UF          | C    | 02   |      | UF                    |      |      |      |              |
| VEND_CEP         | V    | 10   |      | CEP                   |      |      |      |              |
| -> PAIS_ID       | I    |      |      | ID Pais               |      |      |      |              |
| VEND_TELEFONE    | V    | 15   |      | Telefone              |      |      |      |              |
| VEND_CNPJCPF     | V    | 20   |      | CNPJ/CPF              |      |      |      |              |
| VEND_IERG        | V    | 20   |      | Inscrição Estadual/RG |      |      |      |              |
| VEND_EMAIL       | V    | 100  |      | Email                 |      |      |      |              |
| VEND_FOTO        | B    |      |      | Foto                  |      |      |      |              |
| VEND_TIPO        | C    | 01   |      | Tipo                  |      |      |      | (A)          |
| <-  VEND_GERENTE | I    |      |      | Código Gerente        |      |      |      |              |
| -> REGI_CODIGO   | I    |      |      | ID Região Padrão      |      |      |      |              |
| VEND_COMISSAO    | N    | 05   | 02   | % Comissão            |      |      |      |              |
| VEND_EMISSAO     | N    | 03   |      | % Pago na Emissão     |      |      |      |              |
| VEND_BAIXA       | N    | 03   |      | % Pago na Baixa       |      |      |      |              |
| VEND_ICMS        | C    | 01   |      | Incide ICMS (S/N)     |      |      |      | S=Sim, N=Não |
| VEND_ICMS_ST     | C    | 01   |      | Incide ICMS-ST (S/N)  |      |      |      | S=Sim, N=Não |
| VEND_ISS         | C    | 01   |      | Incide ISS (S/N)      |      |      |      | S=Sim, N=Não |
| VEND_IPI         | C    | 01   |      | Incide IPI (S/N)      |      |      |      | S=Sim, N=Não |
| VEND_FRETE       | C    | 01   |      | Incide Frete (S/N)    |      |      |      | S=Sim, N=Não |


> VEND_TIPO = ( I=Interno, E=Externo, P=Parceiro )
>





#### ARM (NNR)

Description: *Tabela de Armazens/Depósitos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE           |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | -------------- |
| ID        | I    |      |      | ID              | X    |      |      |                |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    | (E)+NNR_FILIAL |
| CODARM    | C    | 03   |      | ID Armazem      |      | X    | X    | NNR_CODIGO     |
| DES       | V    | 50   |      | Descrição       |      | X    |      | NNR_DESCRI     |
| TIP       | C    | 01   |      | Tipo            |      |      |      | NNR_TIPO       |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |                |
| DATA      | D    |      |      | Data Alteração  |      |      |      |                |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |                |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |                |


> TIP = ( 1=Padrao, 2=Proprio, 3=Terceiro)



#### PROTIP (SX5.X5_TABELA=02)

Description: *Tabela de Tipos de Produtos (Matéria Prima, Embalagem.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| ID        | I    |      |      | ID              | X    |      |      |           |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    |           |
| CODTP     | V    | 06   |      | ID              |      | X    | X    | X5_CHAVE  |
| DES       | V    | 100  |      | Descrição       |      | X    |      | X5_DESCRI |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |           |
| DATA      | D    |      |      | Data Alteração  |      |      |      |           |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |           |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |           |






#### PROORI (SX5=S0)

Description: *Tabela de Origem do Produto (Nacional, Importado).*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| ID        | I    |      |      | ID              | X    |      |      |           |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    |           |
| CODOP     | V    | 06   |      | ID              |      | X    | X    | X5_CHAVE  |
| DES       | V    | 100  |      | Descrição       |      | X    |      | X5_DESCRI |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |           |
| DATA      | D    |      |      | Data Alteração  |      |      |      |           |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |           |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |           |





#### PROGRU (SBM)

Description: *Tabela de Grupo de Produtos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION      | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ---------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID               | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa       |      | X    | X    | (E)+BM_FILIAL |
| CODGP     | V    | 06   |      | ID Grupo Produto |      | X    | X    | BM_GRUPO      |
| DES       | V    | 50   |      | Descrição        |      | X    |      | BM_DESC       |
| HORA      | T    |      |      | Hora Alteração   |      |      |      |               |
| DATA      | D    |      |      | Data Alteração   |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro  |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5        |      |      |      |               |






#### UNI (SAH)

Description: *Tabela de Unidades de Produtos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID              | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    | (E)+AH_FILIAL |
| CODUNI    | C    | 02   |      | ID              |      | X    | X    | AH_UNIMED     |
| NOM       | V    | 20   |      | Nome            |      | X    |      | AH_UMRES      |
| DES       | V    | 50   |      | Descrição       |      |      |      | AH_DESCPO     |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |               |
| DATA      | D    |      |      | Data Alteração  |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |               |





#### NCM ( SYD)

Description: *Tabela de NCM.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE       |
| ------ | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| ID     | I    |      |      | ID              | X    |      |      |            |
| CODNCM | V    | 10   |      | ID              |      | X    | X    | YD_TEC     |
| DES    | V    | 50   |      | Descrição       |      | X    |      | YD_DESC_P  |
| OBS    | V    | 100  |      | Observação      |      |      |      | YD_VM_TEXT |
| HORA   | T    |      |      | Hora Alteração  |      |      |      |            |
| DATA   | D    |      |      | Data Alteração  |      |      |      |            |
| STATUS | C    | 01   |      | Status Registro |      |      |      |            |
| MD5    | C    | 32   |      | Chave MD5       |      |      |      |            |






#### PRO (SB1)

Description: *Cadastro de Produtos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION               | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ------------------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID                        | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa                |      | X    | X    | (E)+B1_FILIAL |
| CODPRO    | V    | 30   |      | ID Produto                |      | X    | X    | B1_COD        |
| DES       | V    | 100  |      | Descrição                 |      | X    |      | B1_DESC       |
| ATI       | C    | 01   |      | Ativo (1=Sim, 2=Não)      |      |      |      | B1_MSBLQL     |
| -> CODTP  | V    | 06   |      | ID Tipo de Produto        |      |      |      | B1_TIPO       |
| -> CODGP  | V    | 06   |      | ID Grupo de Produto       |      |      |      | B1_GRUPO      |
| -> CODUNI | V    | 02   |      | ID Unidade                |      |      |      | B1_UM         |
| -> CODARM | V    | 03   |      | ID Armazem                |      |      |      | B1_LOCPAD     |
| FATCON    | N    | 05   | 02   | Fator de Conversão        |      |      |      | B1_CONV       |
| TIPCON    | C    | 01   |      | Tipo de Conversao         |      |      |      | B1_TIPCONV    |
| PROALT    | V    | 30   |      | Produto Alternativo       |      |      |      | B1_ALTER      |
| VLRVDA    | N    | 14   | 02   | Valor de Venda            |      |      |      | B1_PRV1       |
| VLRCUSST  | N    | 14   | 02   | Valor de Custo Padrão     |      |      |      | B1_CUST       |
| DTCUSST   | D    |      |      | Data de Custo Padrão      |      |      |      | B1_UCALSTD    |
| VLRCOM    | N    | 14   | 02   | Ultimo Preço de Compra    |      |      |      | B1_UPRC       |
| DTCOM     | D    |      |      | Ultima Data de Compa      |      |      |      | B1_UCOM       |
| PESLIQ    | N    | 10   | 04   | Peso Liquido              |      |      |      | B1_PESO       |
| PESBRU    | N    | 10   | 04   | Peso Bruto                |      |      |      | B1_PESBRU     |
| BASEST    | N    | 07   |      | Qtd. Base de Estrutura    |      |      |      | B1_QB         |
| ULTREV    | D    |      |      | Ultima Revisão            |      |      |      | B1_UREV       |
| COM       | N    | 05   | 02   | % Comissão do Produto     |      |      |      | B1_COMIS      |
| CODBAR    | V    | 30   |      | Código de Barra           |      |      |      | B1_CODBAR     |
| ALIICM    | N    | 05   | 02   | % Aliquota de ICMS        |      |      |      | B1_PICM       |
| ALIIPI    | N    | 05   | 02   | % Aliquota de IPI         |      |      |      | B1_IPI        |
| ALIISS    | N    | 05   | 02   | % Aliquota de ISSQN       |      |      |      | B1_ALIQISS    |
| BASST     | N    | 05   | 02   | % Base Vlr. Agregado (ST) |      |      |      | B1_PICMRET    |
| -> CODNCM | V    | 10   |      | ID ICM                    |      |      |      | B1_POSIPI     |
| -> CODOP  | V    | 06   |      | ID Origem                 |      |      |      | B1_ORIGEM     |
| QTDEMB    | N    | 06   |      | Qtd. Embalagem            |      |      |      | B1_QE         |
| ESTMIN    | N    | 12   | 04   | Qtd. Estoque Minimo       |      |      |      | B1_EMIN       |
| ESTMAX    | N    | 12   | 04   | Qtd. Estoque Maximo       |      |      |      | B1_MAX        |
| FOT       | B    |      |      | Foto                      |      |      |      | B1_BITMAP     |
| OBS       | M    |      |      | Observação                |      |      |      | B1_OBS        |
| HORA      | T    |      |      | Hora Alteração            |      |      |      |               |
| DATA      | D    |      |      | Data Alteração            |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro           |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5                 |      |      |      |               |


> TIPCON = ( M=Multiplicação, D=Divisão )




#### SEG (AOV)

Description: *Tabela de Segmentos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE           |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | -------------- |
| ID        | I    |      |      | ID              | X    |      |      |                |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    | (E)+AOV_FILIAL |
| CODSEG    | V    | 06   |      | ID Segmento     |      | X    | X    | AOV_CODSEG     |
| DES       | V    | 50   |      | Descrição       |      | X    |      | AOV_DESCRI     |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |                |
| DATA      | D    |      |      | Data Alteração  |      |      |      |                |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |                |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |                |





#### CONPAG (SE4)

Description: *Tabela de Condições de Pagamento.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION              | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ------------------------ | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID                       | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empres                |      | X    | X    | (E)+E4_FILIAL |
| CODCP     | C    | 03   |      | ID Condição de Pagamento |      | X    | X    | E4_CODIGO     |
| DES       | V    | 50   |      | Descrição                |      | X    |      | E4_DESCRI     |
| HORA      | T    |      |      | Hora Alteração           |      |      |      |               |
| DATA      | D    |      |      | Data Alteração           |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro          |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5                |      |      |      |               |






#### TABPRE (DA0)

Description: *Tabela de Preços.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME       | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE           |
| ---------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | -------------- |
| ID         | I    |      |      | ID                   | X    |      |      |                |
| --> CODEMP | V    | 09   |      | ID Empresa           |      | X    | X    | (E)+DA0_FILIAL |
| CODTP      | V    | 03   |      | ID Tabela Preço      |      | X    | X    | DA0_CODTAB     |
| DES        | V    | 50   |      | Descrição            |      | X    |      | DA0_DESCRI     |
| ATI        | C    | 01   |      | Ativa (1=Sim, 2=Nao) |      |      |      | DA0_ATIVO      |
| DTVALINI   | D    |      |      | Validade Inicial     |      |      |      | DA0_DATDE      |
| DTVALFIM   | D    |      |      | Validade Final       |      |      |      | DA0_DATATE     |
| HORA       | T    |      |      | Hora Alteração       |      |      |      |                |
| DATA       | D    |      |      | Data Alteração       |      |      |      |                |
| STATUS     | C    | 01   |      | Status Registro      |      |      |      |                |
| MD5        | C    | 32   |      | Chave MD5            |      |      |      |                |







#### TABPREIT (DA1)

Description: *Itens da Tabela de Preços.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION           | PK   | NN   | UN   | NOTE           |
| --------- | ---- | ---- | ---- | --------------------- | ---- | ---- | ---- | -------------- |
| ID        | I    |      |      | ID                    | X    |      |      | TABPRE->ID     |
| -> CODEMP | V    | 09   |      | ID Empresa            |      | X    | X    | (E)+DA1_FILIAL |
| -> CODTP  | V    | 03   |      | ID Tabela de Preço    |      | X    | X    | DA1_CODTAB     |
| SEQ       | V    | 04   |      | Sequencia             |      | X    | X    | DA1_ITEM       |
| -> CODPRO | V    | 30   |      | ID Produto            |      | X    |      | DA1_CODPRO     |
| PREVDA    | N    | 14   | 02   | Preço de Venda        |      | X    |      | DA1_PRCVEN     |
| VLRDES    | N    | 14   | 02   | Valor de Desconto     |      |      |      | DA1_VLRDES     |
| ATI       | C    | 01   |      | Ativo (1=Sim, 2=Não)  |      |      |      | DA1_ATIVO      |
| PREMAX    | N    | 14   | 02   | Preço de Venda Máximo |      |      |      | DA1_PRCMAX     |
| HORA      | T    |      |      | Hora Alteração        |      |      |      |                |
| DATA      | D    |      |      | Data Alteração        |      |      |      |                |
| STATUS    | C    | 01   |      | Status Registro       |      |      |      |                |
| MD5       | C    | 32   |      | Chave MD5             |      |      |      |                |







#### MUN (CC2)

Description: *Tabela de Municipios do IBGE.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION      | PK   | NN   | UN   | NOTE       |
| ------ | ---- | ---- | ---- | ---------------- | ---- | ---- | ---- | ---------- |
| ID     | I    |      |      | ID               | X    |      |      |            |
| CODMUN | V    | 05   |      | Código Municipio |      | X    | X    | CC2_CODMUN |
| UF     | C    | 02   |      | UF               |      | X    |      | CC2_EST    |
| NOM    | V    | 60   |      | Nome             |      | X    |      | CC2_MUN    |
| HORA   | T    |      |      | Hora Alteração   |      |      |      |            |
| DATA   | D    |      |      | Data Alteração   |      |      |      |            |
| STATUS | C    | 01   |      | Status Registro  |      |      |      |            |
| MD5    | C    | 32   |      | Chave MD5        |      |      |      |            |






#### CLI (SA1)

Description: *Cadastro de Clientes.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION                  | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ---------------------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID                           | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa                   |      | X    | X    | (E)+A1_FILIAL |
| CODCLI    | V    | 06   |      | ID Cliente                   |      | X    | X    | A1_COD        |
| LOJCLI    | C    | 02   |      | ID Loja                      |      | X    | X    | A1_LOJA       |
| ATI       | C    | 01   |      | Ativo (1=Inativo, 2=Ativo)   |      |      |      | A1_MSBLQL     |
| RAZSOC    | V    | 100  |      | Nome/Razão Social            |      | X    |      | A1_NOME       |
| NOMFAN    | V    | 50   |      | Nome de Fantasia             |      |      |      | A1_NREDUZ     |
| END       | V    | 100  |      | Endereço                     |      |      |      | A1_END        |
| COM       | V    | 50   |      | Complemento                  |      |      |      | A1_COMPLEM    |
| UF        | C    | 02   |      | UF                           |      |      |      | A1_EST        |
| -> CODMUN | V    | 05   |      | ID Municipio                 |      |      |      | A1_COD_MUN    |
| BAI       | V    | 50   |      | Bairro                       |      |      |      | A1_BAIRRO     |
| CEP       | V    | 10   |      | CEP                          |      |      |      | A1_CEP        |
| DDD       | C    | 03   |      | DDD                          |      |      |      | A1_DDD        |
| TEL       | V    | 15   |      | Telefone                     |      |      |      | A1_TEL        |
| FAX       | V    | 15   |      | Fax                          |      |      |      | A1_FAX        |
| CON       | V    | 30   |      | Contato                      |      |      |      | A1_CONTATO    |
| CNPJCPF   | V    | 20   |      | CNPJ/CPF                     |      |      |      | A1_CGC        |
| IE        | V    | 20   |      | Inscrição Estadual/RG        |      |      |      | A1_INSCR      |
| RG        | V    | 20   |      | RG                           |      |      |      | A1_PFISICA    |
| IM        | V    | 20   |      | Inscrição Municipal          |      |      |      | A1_INSCRM     |
| DTNAS     | D    |      |      | Data Nascimento/Abertura     |      |      |      | A1_DTNASC     |
| EMA       | V    | 100  |      | Email                        |      |      |      | A1_EMAIL      |
| URL       | V    | 100  |      | Home Page                    |      |      |      | A1_HPAGE      |
| -> CODSEG | V    | 06   |      | ID Segmento                  |      |      |      | A1_CODSEG     |
| -> CODVEN | V    | 06   |      | ID Vendedor                  |      |      |      | A1_VEND       |
| PERCOM    | N    | 05   | 02   | % Comissão                   |      |      |      | A1_COMISS     |
| TIPFRE    | C    | 01   |      | Tipo Frete (C-CIF, F=FOB)    |      |      |      | A1_TPFRET     |
| PERDES    | N    | 05   | 02   | % Desconto Sugerido          |      |      |      | A1_DESC       |
| -> CODCP  | V    | 03   |      | ID Condição de Pagamento     |      |      |      | A1_COND       |
| -> CODTP  | V    | 03   |      | ID Tabela de Preço           |      |      |      | A1_TABELA     |
| -> CODREG | V    | 04   |      | ID Região                    |      |      |      | A1_REGIAO     |
| LIMCR     | N    | 14   | 02   | Limite de Credito            |      |      |      | A1_LC         |
| VCTLIMCR  | D    |      |      | Vencimento LImite de Credito |      |      |      | A1_VENCLC     |
| DTPRICOM  | D    |      |      | Primeira Compra              |      |      |      | A1_PRICOM     |
| ULTVIS    | D    |      |      | Ultima Visita                |      |      |      | A1_ULTVIS     |
| HORA      | T    |      |      | Hora Alteração               |      |      |      |               |
| DATA      | D    |      |      | Data Alteração               |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro              |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5                    |      |      |      |               |







#### MOT (DA4)

Description: *Cadastro de Motoristas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE           |
| --------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | -------------- |
| ID        | I    |      |      | ID                   | X    |      |      |                |
| -> CODEMP | V    | 09   |      | ID Empresa           |      | X    | X    | (E)+DA4_FILIAL |
| CODMOT    | V    | 06   |      | ID Motorista         |      | X    | X    | DA4_COD        |
| TIP       | C    | 01   |      | Tipo                 |      |      |      | DA4_TIPOMOT    |
| ATI       | C    | 01   |      | Ativo (1=Sim, 2=Nao) |      |      |      | DA4_BLQMOT     |
| NOM       | V    | 100  |      | Nome                 |      | X    |      | DA4_NOME       |
| APE       | V    | 50   |      | Apelido              |      |      |      | DA4_NREDUZ     |
| END       | V    | 100  |      | Endereço             |      |      |      | DA4_END        |
| BAI       | V    | 50   |      | Bairro               |      |      |      | DA4_BAIRRO     |
| UF        | C    | 02   |      | UF                   |      |      |      | DA4_EST        |
| -> CODMUN | V    | 05   |      | ID Municipio         |      |      |      | DA4_CODMUN     |
| CEP       | V    | 10   |      | CEP                  |      |      |      | DA4_CEP        |
| DDD       | C    | 03   |      | DDD                  |      |      |      | DA4_DDD        |
| TEL       | V    | 15   |      | Telefone             |      |      |      | DA4_TEL        |
| CNPJCPF   | V    | 20   |      | CNPJ/CPF             |      |      |      | DA4_CGC        |
| CNH       | V    | 20   |      | CNH                  |      |      |      | DA4_NUMCHN     |
| HORA      | T    |      |      | Hora Alteração       |      |      |      |                |
| DATA      | D    |      |      | Data Alteração       |      |      |      |                |
| STATUS    | C    | 01   |      | Status Registro      |      |      |      |                |
| MD5       | C    | 32   |      | Chave MD5            |      |      |      |                |


> TIP = (1=Proprio, 2=Terceiro, 4=Agregado )



#### VEIMAR (SX5=M6)

Description: *Tabela de Marcas de Veiculo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| ID        | I    |      |      | ID              | X    |      |      |           |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    |           |
| CODMAR    | V    | 06   |      | ID Marca        |      | X    | X    | X5_CHAVE  |
| DES       | V    | 100  |      | Descrição       |      | X    |      | X4_DESCRI |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |           |
| DATA      | D    |      |      | Data Alteração  |      |      |      |           |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |           |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |           |






#### VEITIP (DUT)

Description: *Tabela de TIpo de Carroceria de Veículo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION        | PK   | NN   | UN   | NOTE           |
| --------- | ---- | ---- | ---- | ------------------ | ---- | ---- | ---- | -------------- |
| ID        | I    |      |      | ID                 | X    |      |      |                |
| -> CODEMP | V    | 09   |      | ID Empresa         |      | X    | X    | (E)+DUT_FILIAL |
| CODTV     | C    | 02   |      | ID Carroceria      |      | X    | X    | DUT_TIPVEI     |
| DES       | V    | 100  |      | Descrição          |      | X    |      | DUT_DESCRI     |
| CATVEI    | C    | 02   |      | Categoria Veiculo  |      |      |      | DUT_CATVEI     |
| TIPROD    | C    | 02   |      | Tipo de Rodado     |      |      |      | DUT_TIPROD     |
| TIPCAR    | C    | 02   |      | Tipo de Carroceria |      |      |      | DUT_TIPCAR     |
| HORA      | T    |      |      | Hora Alteração     |      |      |      |                |
| DATA      | D    |      |      | Data Alteração     |      |      |      |                |
| STATUS    | C    | 01   |      | Status Registro    |      |      |      |                |
| MD5       | C    | 32   |      | Chave MD5          |      |      |      |                |



> CATVEI = (1-Comum, 2-Cavalo, 3-Carreta, 4-Especial, 5-Utilitário, 6-Composição )
>
> TIPROD = ( 00-Nao Aplicavel, 02-Truck, 02-Toco, 03-Cavalo Mecanico, 04-VAN, 05-Utilitario, 06-Outros )
>
> TIPCAR = ( 00-Nao Aplicavel, 01-Aberta, 02-Fechada/Bau, 03-Granelera, 04-Porta Container, 05-Sider )



#### VEICOR (SX5=M7)

Description: *Tabela de Cor de Veículo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| ID        | I    |      |      | ID              | X    |      |      |      |
| -> CODEMP | V    | 09   |      | ID Empresa      |      | X    | X    |      |
| CODCOR    | V    | 06   |      | ID Cor          |      | X    | X    |      |
| DES       | V    | 100  |      | Descrição       |      | X    |      |      |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA      | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |      |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |      |






#### VEI (DA3)

Description: *Cadastro de Veículos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION           | PK   | NN   | UN   | NOTE           |
| --------- | ---- | ---- | ---- | --------------------- | ---- | ---- | ---- | -------------- |
| ID        | I    |      |      | ID                    | X    |      |      |                |
| -> CODEMP | V    | 09   |      | ID Empresa            |      | X    | X    | DA3_FILIAL (+) |
| CODVEI    | V    | 10   |      | ID Veiculo            |      | X    | X    | DA3_COD        |
| ATI       | C    | 01   |      | Ativo (1=Sim, 2=Não)  |      |      |      | DA3_ATIVO      |
| DES       | V    | 100  |      | Descrição             |      | X    |      | DA3_DESC       |
| -> CODMAR | V    | 06   |      | ID Marca              |      |      |      | DA3_MARVEI     |
| -> CODCOR | V    | 06   |      | ID Cor                |      |      |      | DA3_CORVEI     |
| ANOFAB    | N    | 04   |      | Ano de Fabricação     |      |      |      | DA3_ANOFAB     |
| ANOMOD    | N    | 04   |      | Ano de Modelo         |      |      |      | DA3_ANOMOD     |
| PLA       | V    | 08   |      | Numero de Placa       |      |      |      | DA3_PLACA      |
| UF        | C    | 02   |      | UF da Placa           |      |      |      | DA3_ESTPLA     |
| MUNPLA    | V    | 50   |      | Municipio da Placa    |      |      |      | DA3_MUNPLA     |
| NROCHA    | V    | 20   |      | Numero Chassi         |      |      |      | DA3_CHASSI     |
| CODREN    | V    | 11   |      | Código Renavam        |      |      |      | DA3_RENAVA     |
| CAPNOM    | N    | 09   | 02   | Capacidade Nominativa |      |      |      | DA3_CAPACIN    |
| VOLMAX    | N    | 06   | 02   | Volume Maximo M3      |      |      |      | DA3_VOMAX      |
| TAR       | N    | 09   | 02   | Tara                  |      |      |      | DA3_TARA       |
| -> CODMOT | V    | 06   |      | ID Motorista          |      |      |      | DA3_MOTORI     |
| FRO       | C    | 01   |      | Frota                 |      |      |      | DA3_FROVEI     |
| -> CODTV  | C    | 02   |      | ID Rodado             |      |      |      | DA3_TPROD      |
| DTINISEG  | D    |      |      | Data Inicio do Seguro |      |      |      | DA3_DTIVSG     |
| DTFIMSEG  | D    |      |      | Data Final do Seguro  |      |      |      | DA3_DTFVSG     |
| FOT       | B    |      |      | Foto                  |      |      |      | DA3_BITMAP     |
| OBS       | M    |      |      | Observação            |      |      |      |                |
| HORA      | T    |      |      | Hora Alteração        |      |      |      |                |
| DATA      | D    |      |      | Data Alteração        |      |      |      |                |
| STATUS    | C    | 01   |      | Status Registro       |      |      |      |                |
| MD5       | C    | 32   |      | Chave MD5             |      |      |      |                |


> FRO = (1=Propria, 2=Terceiro, 3=Agregado )



#### PEDVEN (SC5)

Description: *Movimento de Pedidos de Vendas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION              | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ------------------------ | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID                       | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa               |      | X    | X    | C5_FILIAL (+) |
| NROPED    | V    | 06   |      | Numero do Pedido         |      | X    | X    | C5_NUM        |
| -> CODCLI | V    | 06   |      | ID Cliente               |      | X    |      | C5_CLIENTE    |
| -> LOJCLI | C    | 02   |      | LJ Cliente               |      | X    |      | C5_LOJA       |
| MSG       | V    | 100  |      | Mensagem da Nota         |      |      |      | C5_MENNOTA    |
| -> CODVEN | V    | 06   |      | ID Vendedor              |      |      |      | C5_VEND1      |
| -> CODCP  | V    | 03   |      | ID Condição de Pagamento |      |      |      | C5_CONDPAG    |
| -> CODTP  | V    | 03   |      | ID Tabela de Preço       |      |      |      | C5_TABELA     |
| COM       | N    | 05   | 02   | % Comissao               |      |      |      | C5_COMIS1     |
| DTEMI     | D    |      |      | Data de Emissao          |      |      |      | C5_EMISSAO    |
| DTSAI     | D    |      |      | Data de Saida            |      |      |      | C5_FECENT     |
| -> CODVEI | V    | 10   |      | ID Veiculo               |      |      |      | C5_VEICULO    |
| IMP       | C    | 01   |      | Importado (1=Sim, 2=Nao) |      |      |      | C5_IMP        |
| DTIMP     | D    |      |      | Data de Importação       |      |      |      | C5_DTTR       |
| HRIMP     | T    |      |      | Hora de Importação       |      |      |      | C5_HRTR       |
| TIPVDA    | C    | 01   |      | Tipo de Venda            |      |      |      | C5_TPVNJFS    |
| NRONOT    | V    | 10   |      | Nota (Faturado)          |      |      |      | C5_NOTA       |
| HORA      | T    |      |      | Hora Alteração           |      |      |      |               |
| DATA      | D    |      |      | Data Alteração           |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro          |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5                |      |      |      |               |



>TIPVDA = (001=Venda, 002=Bonificação, 003=Troca/Devolução)




#### PEDVENIT (SC6)

Description: *Itens do movimento de Pedido de Vendas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID                   | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa           |      | X    | X    | C6_FILIAL (+) |
| -> NROPED | V    | 06   |      | Numero Pedido        |      | X    | X    | C6_NUM        |
| SEQ       | V    | 03   |      | Sequencia            |      | X    | X    | C6_ITEM       |
| -> CODPRO | V    | 30   |      | ID Produto           |      | X    |      | C6_PRODUTO    |
| QTD       | N    | 09   | 02   | Quantidade           |      | X    |      | C6_QTDVEN     |
| VLRUN     | N    | 14   | 02   | Valor UN             |      | X    |      | C6_VALOR      |
| TES       | V    | 03   |      | TES                  |      |      |      | C6_TES        |
| -> CODARM | C    | 03   |      | ID Armazem           |      |      |      | C6_LOCAL      |
| PERDES    | N    | 08   | 06   | % Desconto           |      |      |      | C6_DESCONT    |
| VLRDES    | N    | 14   | 05   | Valor de Desconto    |      |      |      | C6_VALDESC    |
| PERCOM    | N    | 05   | 02   | % Comissao Produto   |      |      |      | C6_COMISS1    |
| VLRTAB    | N    | 12   | 02   | Preço Venda (Tabela) |      |      |      | C6_PRUNIT     |
| HORA      | T    |      |      | Hora Alteração       |      |      |      |               |
| DATA      | D    |      |      | Data Alteração       |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro      |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5            |      |      |      |               |





#### SALPRO (SB2)

Description: *Saldo de Produtos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID              | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa      |      |      | X    | C6_FILIAL (+) |
| -> CODPRO | V    | 30   |      | ID Produto      |      |      | X    | B2_COD        |
| QTD       | N    | 14   | 02   | Quantidade      |      |      | X    | B2_QATU       |
| -> CODARM | C    | 03   |      | ID Armazem      |      |      | X    | B2_LOCAL      |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |               |
| DATA      | D    |      |      | Data Alteração  |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |               |



#### CON (SU5)

Description: *Cadastro de Contatos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION                | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | -------------------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      | ID                         | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa                 |      | X    | X    | U5_FILIAL (+) |
| CODCON    | V    | 06   |      | ID Contato                 |      | X    | X    | U5_CODCON     |
| NOM       | V    | 100  |      | Nome                       |      | X    |      | U5_CONTAT     |
| TEL1      | V    | 15   |      | Telefone 1                 |      |      |      | U5_FCOM1      |
| TEL2      | V    | 15   |      | Telefone 2                 |      |      |      | U5_FCOM2      |
| EMA       | V    | 100  |      | EMail                      |      |      |      | U5_EMAIL      |
| URL       | V    | 100  |      | URL                        |      |      |      | U5_URL        |
| STA       | C    | 01   |      | Status                     |      |      |      | U5_STATUS     |
| ATI       | C    | 01   |      | Ativo (1=Inativo, 2=Ativo) |      |      |      | U5_MSBLQL     |
| HORA      | T    |      |      | Hora Alteração             |      |      |      |               |
| DATA      | D    |      |      | Data Alteração             |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro            |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5                  |      |      |      |               |



> STA = (1=Desatualizado, 2=Atualizado, 3=Em Desenvolvimento)



#### BAN (SA6)

Description: *Cadastro de Bancos/Agências.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE         |
| --------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | ------------ |
| ID        | I    |      |      | ID                   | X    |      |      |              |
| -> CODEMP | V    | 09   |      | ID Empresa           |      |      | X    | (+)A6_FILIAL |
| COD       | C    | 03   |      | ID Banco             |      |      | X    | A6_COD       |
| AGE       | V    | 05   |      | Nro. Agencia         |      |      | X    | A6_AGENCIA   |
| DVAGEN    | C    | 01   |      | DV da Agencia        |      |      |      | A6_DVAG      |
| NROCTA    | V    | 10   |      | Número da Conta      |      |      | X    | A6_NUMCON    |
| DVCTA     | C    | 01   |      | DV da Conta          |      |      |      | A6_DVCTA     |
| NOM       | V    | 100  |      | Nome                 |      |      |      | A6_NOME      |
| NOMRED    | V    | 50   |      | Nome Reduzido        |      |      |      | A6_NREDUZ    |
| ATI       | C    | 01   |      | Ativo (1=Sim, 2=Não) |      |      |      | A6_BLOKED    |
| END       | V    | 100  |      | Endereço             |      |      |      | A6_END       |
| BAI       | V    | 50   |      | Bairro               |      |      |      | A6_BAIRRO    |
| MUN       | V    | 50   |      | Municipio            |      |      |      | A6_MUN       |
| UF        | C    | 02   |      | UF                   |      |      |      | A6_EST       |
| TEL       | V    | 15   |      | Telefone             |      |      |      | A6_TEL       |
| CON       | V    | 50   |      | Contato              |      |      |      | A6_CONTATO   |
| HORA      | T    |      |      | Hora Alteração       |      |      |      |              |
| DATA      | D    |      |      | Data Alteração       |      |      |      |              |
| STATUS    | C    | 01   |      | Status Registro      |      |      |      |              |
| MD5       | C    | 32   |      | Chave MD5            |      |      |      |              |






#### TITREC (SE1)

Description: *Movimento de Titulos a Receber.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME       | T    | S    | D    | DESCRIPTION             | PK   | NN   | UN   | NOTE         |
| ---------- | ---- | ---- | ---- | ----------------------- | ---- | ---- | ---- | ------------ |
| ID         | I    |      |      | ID                      | X    |      |      |              |
| -> CODEMP  | V    | 09   |      | ID Empresa              |      |      | X    | (+)E1_FILIAL |
| PRE        | C    | 03   |      | Prefixo                 |      |      | X    | E1_PREFIXO   |
| TIT        | V    | 10   |      | Titulo                  |      |      | X    | E1_NUM       |
| PAR        | C    | 01   |      | Parcela                 |      |      | X    | E1_PARCELA   |
| TIP        | V    | 03   |      | Tipo                    |      |      | X    | E1_TIPO      |
| -> CLIE_ID | V    | 06   |      | ID Cliente              |      | X    |      | E1_CLIENTE   |
| -> CLIE_LJ | C    | 02   |      | Loja Cliente            |      | X    |      | E1_LOJA      |
| DTEMI      | D    |      |      | Data de Emissão         |      | X    |      | E1_EMISSAO   |
| DTVCT      | D    |      |      | Data de Vencimento      |      | X    |      | E1_VCTO      |
| DTVCTRE    | D    |      |      | Data de Vencimento Real |      |      |      | E1_VENCREA   |
| VLRTIT     | N    | 18   | 02   | Valor do Titulo         |      | X    |      | E1_VALOR     |
| VLRSLD     | N    | 18   | 02   | Saldo do Titulo         |      |      |      | E1_SALDO     |
| HIS        | V    | 50   |      | Historico               |      |      |      | E1_HIST      |
| NROPED     | V    | 06   |      | Número do Pedido        |      |      |      | E1_PEDIDO    |
| -> CODVEN  | V    | 06   |      | ID Vendedor             |      |      |      | E1_VEND1     |
| -> BANC_ID | C    | 03   |      | ID Banco/Portador       |      |      |      | E1_PORTADO   |
| HORA       | T    |      |      | Hora Alteração          |      |      |      |              |
| DATA       | D    |      |      | Data Alteração          |      |      |      |              |
| STATUS     | C    | 01   |      | Status Registro         |      |      |      |              |
| MD5        | C    | 32   |      | Chave MD5               |      |      |      |              |








#### FORN (SA2)

Description: *Cadastro de Fornecedores.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE         |
| --------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | ------------ |
| ID        | I    |      |      |                      | X    |      |      |              |
| -> CODEMP | V    | 09   |      | ID Empresa           |      |      |      | (+)A2_FILIAL |
| CODFOR    | V    | 06   |      | ID Fornecedor        |      |      | X    | A2_COD       |
| LOJFOR    | C    | 02   |      | Loja Fornecedor      |      |      | X    | A2_LOJA      |
| ATI       | C    | 01   |      | Ativo (1=Sim, 2=Não) |      |      |      | A2_MSBLQL    |
| NOM       | V    | 100  |      | Nome/Razão Sociali   |      | X    |      | A2_NOME      |
| NOMRED    | V    | 50   |      | Nome de Fantasia     |      |      |      | A2_NREDUZ    |
| END       | V    | 100  |      | Endereço             |      |      |      | A2_END       |
| COM       | V    | 50   |      | Complemento          |      |      |      | A2_COMPLEM   |
| BAI       | V    | 50   |      | Bairro               |      |      |      | A2_BAIRRO    |
| UF        | C    | 02   |      | UF                   |      |      |      | A2_EST       |
| -> CODMUN | V    | 05   |      | ID Municipio         |      |      |      | A2_COD_MUN   |
| CEP       | v    | 10   |      | CEP                  |      |      |      | A2_CEP       |
| DDD       | C    |      |      | DDD                  |      |      |      | A2_DDD       |
| TEL       | V    | 15   |      | Telefone             |      |      |      | A2_TEL       |
| FAX       | V    | 15   |      | FAX                  |      |      |      | A2_FAX       |
| CON       | V    | 50   |      | Contato              |      |      |      | A2_CONTATO   |
| CNPJCPF   | V    | 20   |      | CNPJ/CPF             |      |      |      | A2_CGC       |
| IE        | V    | 20   |      | Inscrição Estadual   |      |      |      | A2_INSCR     |
| RG        | V    | 20   |      | RG                   |      |      |      | A2_PFISICA   |
| OBS       | M    |      |      | Observação           |      |      |      |              |
| HORA      | T    |      |      | Hora Alteração       |      |      |      |              |
| DATA      | D    |      |      | Data Alteração       |      |      |      |              |
| STATUS    | C    | 01   |      | Status Registro      |      |      |      |              |
| MD5       | C    | 32   |      | Chave MD5            |      |      |      |              |





#### TITPAG (SE2)

Description: *Movimento de Titulos a Pagar.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION             | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ----------------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      |                         | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa              |      |      | X    | E2_FILIAL (+) |
| PRE       | C    | 03   |      | Prefixo                 |      |      | X    | E2_PREFIXO    |
| TIT       | V    | 10   |      | Numero                  |      |      | X    | W2_NUM        |
| PAR       | C    | 01   |      | Parcela                 |      |      | X    | E2_PARCELA    |
| TIP       | V    | 03   |      | Tipo                    |      |      | X    | E2_TIPO       |
| -> CODFOR | V    | 06   |      | ID Fornecedor           |      | X    |      | E2_FORNECE    |
| -> LOJFOR | C    | 02   |      | Loja Fornecedor         |      | X    |      | E2_LOJA       |
| DTEMI     | D    |      |      | Data de Emissão         |      | X    |      | E2_EMISSAO    |
| DTVCT     | D    |      |      | Data de Vencimento      |      | X    |      | E2_VENCTO     |
| DTVCTRE   | D    |      |      | Data de Vencimento Real |      |      |      | E2_VENCREA    |
| VLRTIT    | N    | 18   | 02   | Valor do Titulo         |      | X    |      | E2_VALOR      |
| VLRSLD    | N    | 18   | 02   | Saldo do Titulo         |      |      |      | E2_SALDO      |
| HIS       | V    | 50   |      | Histórico               |      |      |      | E2_HIST       |
| HORA      | T    |      |      | Hora Alteração          |      |      |      |               |
| DATA      | D    |      |      | Data Alteração          |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro         |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5               |      |      |      |               |









#### NAT (SED)

Description: *Lançamentos Bancario/Caixas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION       | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ----------------- | ---- | ---- | ---- | ------------- |
| ID        |      |      |      | ID                | X    |      |      |               |
| -> CODEMP | V    | 09   |      | ID Empresa        |      |      | X    | ED_FILIAL (+) |
| CODNAT    | V    | 10   |      | ID Natureza       |      |      | X    | ED_CODIGO     |
| DES       | V    | 50   |      | Descrição         |      | X    |      | ED_DESCRIC    |
| -> CODGN  | C    | 03   |      | ID Grupo Natureza |      |      |      | ED_GRUPO      |
| HORA      | T    |      |      | Hora Alteração    |      |      |      |               |
| DATA      | D    |      |      | Data Alteração    |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro   |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5         |      |      |      |               |





#### MOVBAN (SE5)

Description: *Lançamentos Bancario/Caixas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION               | PK   | NN   | UN   | NOTE          |
| --------- | ---- | ---- | ---- | ------------------------- | ---- | ---- | ---- | ------------- |
| ID        | I    |      |      |                           | X    |      |      |               |
| -> CODEMP | V    | 06   |      | ID Empresa                |      |      | X    | E5_FILIAL (+) |
| DT        | D    |      |      | Data                      |      |      | X    | E5_DATA       |
| BCO       | C    | 03   |      | Banco                     |      |      | X    | E5_BANCO      |
| AGE       | V    | 05   |      | Agencia                   |      |      | X    | E5_AGENCIA    |
| CON       | V    | 10   |      | Conta                     |      |      | X    | E5_CONTA      |
| VLR       | N    | 18   | 02   | Valor                     |      |      |      | E5_VALOR      |
| TIP       | C    | 01   |      | Tipo                      |      |      |      | E5_TIPOLAN    |
| -> CODNAT | V    | 10   |      | ID Natureza               |      |      |      | E5_NATUREZ    |
| NROCH     | V    | 15   |      | Nro. Cheque               |      |      | X    | E5_NUMCHEQ    |
| DOC       | V    | 50   |      | Documento                 |      |      |      | E5_DOCUMEN    |
| HIS       | V    | 50   |      | Histórico                 |      |      |      | E5_HISTOR     |
| PRE       | C    | 03   |      | Prefixo                   |      |      |      | E5_PREFIXO    |
| TIT       | V    | 10   |      | Titulo                    |      |      |      | E5_NUMERO     |
| PAR       | C    | 01   |      | Parcela                   |      |      |      | E5_PARCELA    |
| CLIFOR    | V    | 06   |      | Cliente/Fornecedor        |      |      |      | E5_CLIFOR     |
| LJCLIFOR  | C    | 02   |      | Cliente/Fornecedor - Loja |      |      |      | E5_LOJA       |
| HORA      | T    |      |      | Hora Alteração            |      |      |      |               |
| DATA      | D    |      |      | Data Alteração            |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro           |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5                 |      |      |      |               |



> TIP = (D=Débito, C=Crédito, X=Partida Dobrada)



#### FAT (SF2)

Description: *Movimento de Faturamento.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME       | T    | S    | D    | DESCRIPTION              | PK   | NN   | UN   | NOTE       |
| ---------- | ---- | ---- | ---- | ------------------------ | ---- | ---- | ---- | ---------- |
| ID         | I    |      |      |                          | X    |      |      |            |
| -> CODEMP  | V    | 09   |      | Empresa ID               |      |      | X    | F2_FILIAL  |
| SER        | C    | 03   |      | Série                    |      |      | X    | F2_SERIE   |
| NRO        | V    | 09   |      | Número                   |      |      | X    | F2_DOC     |
| -> CODCLI  | V    | 06   |      | Cliente                  |      | X    |      | F2_CLIENTE |
| -> LOJCLI  | C    | 02   |      | Cliente - Loja           |      | X    |      | F2_LOJA    |
| MSG        | V    | 100  |      | Mensagem da Nota         |      |      |      | F2_MENNOTA |
| -> CODVEN  | V    | 06   |      | ID Veiculo               |      |      |      | F2_VEND1   |
| -> COPA_ID | V    | 03   |      | ID Condição de Pagamento |      |      |      | F2_COND    |
| DTEMI      | D    |      |      | Data de Emissao          |      |      |      | F2_EMISSAO |
| DTSAI      | D    |      |      | Data de Saida            |      |      |      | F2_DTENTR  |
| -> CODVEI  | V    | 10   |      | ID Veiculo               |      |      |      | F2_VEICUL1 |
| HORA       | T    |      |      | Hora Alteração           |      |      |      |            |
| DATA       | D    |      |      | Data Alteração           |      |      |      |            |
| STATUS     | C    | 01   |      | Status Registro          |      |      |      |            |
| MD5        | C    | 32   |      | Chave MD5                |      |      |      |            |







#### FATITE (SD2)

Description: *Itens do Movimento de Faturamento.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME      | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE          |
| --------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ------------- |
| -> CODEMP | V    | 09   |      | ID Empresa      | X    |      |      | C6_FILIAL (+) |
|           |      |      |      |                 |      |      |      |               |
|           |      |      |      |                 |      |      |      |               |
| HORA      | T    |      |      | Hora Alteração  |      |      |      |               |
| DATA      | D    |      |      | Data Alteração  |      |      |      |               |
| STATUS    | C    | 01   |      | Status Registro |      |      |      |               |
| MD5       | C    | 32   |      | Chave MD5       |      |      |      |               |





#### DEPARTAMENTOS (SQB)

Description: *Tabela de Departamentos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE          |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ------------- |
| -> CODEMP      | V    | 09   |      | ID Empresa      | X    |      |      | QB_FILIAL (+) |
| DEPA_ID        | V    | 10   |      | ID Departamento | X    |      |      | QB_DEPTO      |
| DEPA_DESCRICAO | V    | 50   |      | Descrição       |      | X    |      | QB_DESCRIC    |
| HORA           | T    |      |      | Hora Alteração  |      |      |      |               |
| DATA           | D    |      |      | Data Alteração  |      |      |      |               |
| STATUS         | C    | 01   |      | Status Registro |      |      |      |               |
| MD5            | C    | 32   |      | Chave MD5       |      |      |      |               |





#### SINDICATOS (RCE)

Description: *Cadastro de Sindicatos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME              | T    | S    | D    | DESCRIPTION      | PK   | NN   | IN   | NOTE           |
| ----------------- | ---- | ---- | ---- | ---------------- | ---- | ---- | ---- | -------------- |
| -> CODEMP         | V    | 09   |      | ID Empresa       | X    |      |      | RCE_FILIAL (+) |
| SIND_ID           | V    | 10   |      | ID Sindicato     | X    |      |      | RCE_CODIGO     |
| SIND_DESCRI       | V    | 100  |      | Descrição        |      | X    |      | RCE_DESCRI     |
| SIND_END          | V    | 100  |      | Endereço         |      |      |      | RCE_ENDER      |
| SIND_COMPL        | V    | 50   |      | Complemento      |      |      |      | RCE_COMPLE     |
| SIND_BAIRRO       | V    | 50   |      | Bairro           |      |      |      | RCE_BAIRRO     |
| SIND_MUNICIPIO    | V    | 50   |      | Municipio        |      |      |      | RCE_MUNIC      |
| SIND_UF           | C    | 02   |      | UF               |      |      |      | RCE_UF         |
| SIND_CEP          | V    | 10   |      | CEP              |      |      |      | RCE_CEP        |
| SIND_COD_ENTIDADE | V    | 15   |      | Código Eentidade |      |      |      | RCE_ENTSIN     |
| SIND_TEL          | V    | 15   |      | Telefone         |      |      |      | RCE_FONE       |
| SIND_EMAIL        | V    | 100  |      | Email            |      |      |      | RCE_EMAIL      |
| HORA              | T    |      |      | Hora Alteração   |      |      |      |                |
| DATA              | D    |      |      | Data Alteração   |      |      |      |                |
| STATUS            | C    | 01   |      | Status Registro  |      |      |      |                |
| MD5               | C    | 32   |      | Chave MD5        |      |      |      |                |





#### CARGOS (SQ3)

Description: *Tabela de Cargos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE          |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ------------- |
| -> CODEMP      | V    | 09   |      | ID Empresa      |      |      |      | Q3_FILIAL (+) |
| CARG_ID        | V    | 06   |      | ID Cargo        |      |      |      | Q3_CARGO      |
| CARG_DESCRICAO | V    | 50   |      | Descrição       |      |      |      | Q3_DESCSUM    |
| CARG_DETALHE   | M    |      |      | Detalhe         |      |      |      | Q3_MEMO       |
| -> DEPA_ID     | V    | 10   |      | ID Departamento |      |      |      | Q3_DEPTO      |
| HORA           | T    |      |      | Hora Alteração  |      |      |      |               |
| DATA           | D    |      |      | Data Alteração  |      |      |      |               |
| STATUS         | C    | 01   |      | Status Registro |      |      |      |               |
| MD5            | C    | 32   |      | Chave MD5       |      |      |      |               |



 

#### FUNCOES (SRJ)

Description: *Tabela de Funções.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE          |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ------------- |
| -> CODEMP      | V    | 09   |      | ID Empresa      | X    |      |      | RJ_FILIAL (+) |
| FUNC_ID        | V    | 06   |      | ID Função       | X    |      |      | RJ_FUNCAO     |
| FUNC_DESCRICAO | V    | 50   |      | Descrição       |      | X    |      | RJ_DESC       |
| -> CARG_ID     | V    | 06   |      | ID Cargo        |      | X    |      | RJ_CARGO      |
| FUNC_SALARIO   | N    | 14   | 02   | Salario         |      |      |      | RJ_SALARIO    |
| HORA           | T    |      |      | Hora Alteração  |      |      |      |               |
| DATA           | D    |      |      | Data Alteração  |      |      |      |               |
| STATUS         | C    | 01   |      | Status Registro |      |      |      |               |
| MD5            | C    | 32   |      | Chave MD5       |      |      |      |               |



 

#### VERBAS (SRV)

Description: *Cadastro de Verbas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE       |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| -> CODEMP      | V    | 09   |      | ID Empresa      | X    |      |      | RV_FILIAL  |
| VERB_ID        | V    | 03   |      | ID Verba        | X    |      |      | RV_COD     |
| VERB_DESCRICAO | V    | 50   |      | Descrição       |      | X    |      | RV_DESC    |
| VERB_TIPO      | C    | 01   |      | Tipo            |      |      |      | RV_TIPOCOD |
| HORA           | T    |      |      | Hora Alteração  |      |      |      |            |
| DATA           | D    |      |      | Data Alteração  |      |      |      |            |
| STATUS         | C    | 01   |      | Status Registro |      |      |      |            |
| MD5            | C    | 32   |      | Chave MD5       |      |      |      |            |



> VERB\_TIPO = (1=Provento, 2=Desconto)



#### FUNCIONARIO (SRA)

Description: *Cadastro de Funcionários.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME                | T    | S    | D    | DESCRIPTION        | PK   | NN   | IN   | NOTE       |
| ------------------- | ---- | ---- | ---- | ------------------ | ---- | ---- | ---- | ---------- |
| -> CODEMP           | V    | 09   |      | ID Empresa         | X    |      |      | RA_FILIAL  |
| FUNC_ID             | V    | 06   |      | ID Funcionário     | X    |      |      | RA_MAT     |
| FUNC_NM             | V    | 100  |      | Nome               |      | X    |      | RA_NOME    |
| FUNC_APELIDO        | V    | 30   |      | Apelido            |      |      |      | RA_NSOCIAL |
| FUNC_END            | V    | 100  |      | Endereço           |      |      |      | RA_ENDEREC |
| FUNC_COMPL          | V    | 50   |      | Complemento        |      |      |      | RA_COMPLEM |
| FUNC_BAIRRO         | V    | 50   |      | Bairro             |      |      |      | RA_BAIRRO  |
| FUNC_MUNICIPIO      | V    | 50   |      | Municipio          |      |      |      | RA_MUNICIP |
| FUNC_UF             | C    | 02   |      | UF                 |      |      |      | RA_ESTADO  |
| FUNC_CEP            | V    | 10   |      | CE)                |      |      |      | RA_CEP     |
| FUNC_CPF            | V    | 20   |      | CPF                |      |      |      | RA_CIC     |
| FUNC_RG             | V    | 20   |      | RG                 |      |      |      | RA_RG      |
| FUNC_PIS            | V    | 20   |      | PIS                |      |      |      | RA_PIS     |
| FUNC_DT_NASC        | D    |      |      | Data de Nascimento |      |      |      | RA_NASC    |
| RUNC_CTPS_NRO       | V    | 20   |      | Numero CTPS        |      |      |      | RA_NUMCP   |
| FUNC_CTPS_SR        | V    | 10   |      | Série CTPS         |      |      |      | RA_SERCP   |
| FUNC_CTPS_UF        | C    | 02   |      | UF CTPS            |      |      |      | RA_UFCP    |
| FUNC_CNH            | V    | 20   |      | CNH                |      |      |      | RA_HABILIT |
| FUNC_RESERVISTA     | V    | 20   |      | Reservista         |      |      |      | RA_RESERVI |
| FUNC_TIT_ELEITOR    | V    | 20   |      | Titulo de Eleitor  |      |      |      | RA_TITULOE |
| FUNC_TIT_ELEITOR_ZN | V    | 05   |      | Zona Eleitoral     |      |      |      | RA_ZONASEC |
| FUNC_TIT_ELEITOR_SC | V    | 05   |      | Seção Eleitoral    |      |      |      | RA_SECAO   |
| FUNC_SEXO           | C    | 01   |      | Sexo               |      |      |      | RA_SEXO    |
| FUNC_ESTADO_CIVIL   | C    | 01   |      | Estado Civil       |      |      |      | RA_ESTCIVI |
| FUNC_TEL            | V    | 15   |      | Telefone           |      |      |      | RA_TELEFON |
| FUNC_NATURALIDADE   | V    | 50   |      | Naturalidade       |      |      |      | RA_NATURAL |
| FUNC_NM_MAE         | V    | 50   |      | Nome da Mae        |      |      |      | RA_MAE     |
| FUNC_NM_PAI         | V    | 50   |      | Nome do Pai        |      |      |      | RA_PAI     |
| FUNC_DT_ADMISSAO    | D    |      |      | Data de Admissao   |      |      |      | RA_ADMISSA |
| FUNC_DT_DEMISSAO    | D    |      |      | Data de Demisao    |      |      |      | RA_DEMISSA |
| -> FUNC_ID          |      |      |      | ID Função          |      |      |      | RA_CODFUNC |
| -> CARG_ID          |      |      |      | ID Cargo           |      |      |      | RA_CARGO   |
| -> SIND_ID          |      |      |      | ID Sindicato       |      |      |      | RA_SINDICA |
| FUNC_FOTO           | B    |      |      | Foto               |      |      |      | RA_BITMAP  |
| FUNC_OBS            | M    |      |      | Observação         |      |      |      |            |
| HORA                | T    |      |      | Hora Alteração     |      |      |      |            |
| DATA                | D    |      |      | Data Alteração     |      |      |      |            |
| STATUS              | C    | 01   |      | Status Registro    |      |      |      |            |
| MD5                 | C    | 32   |      | Chave MD5          |      |      |      |            |





#### FUNCIONARIO_DEPENDENTES (SRB)

Description: *Cadastro de Dependentes por Funcionário.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME               | T    | S    | D    | DESCRIPTION        | PK   | NN   | IN   | NOTE          |
| ------------------ | ---- | ---- | ---- | ------------------ | ---- | ---- | ---- | ------------- |
| -> CODEMP          | V    | 09   |      | ID Empresa         | X    |      |      | RB_FILIAL (+) |
| -> FUNC_ID         | V    | 06   |      | ID Funcionário     | X    |      |      | RB_MAT        |
| FUDE_NM            | V    | 100  |      | Nome               |      | X    |      | RB_NOME       |
| FUDE_DT_NASC       | D    |      |      | Data de Nascimento |      |      |      | RB_DTNASC     |
| FUDE_SEXO          | C    | 01   |      | Sexo               |      |      |      | RB_SEXO       |
| FUDE_GR_PARENTESCO | C    | 01   |      | Grau de Parentesco |      |      |      | RB_GRAUPAR    |
| FUDE_CPF           | V    | 20   |      | CPF                |      |      |      | RB_CIC        |
| HORA               | T    |      |      | Hora Alteração     |      |      |      |               |
| DATA               | D    |      |      | Data Alteração     |      |      |      |               |
| STATUS             | C    | 01   |      | Status Registro    |      |      |      |               |
| MD5                | C    | 32   |      | Chave MD5          |      |      |      |               |



 

#### HOLERITE

Description: *Movimento de Holerite.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME       | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ---------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| -> CODEMP  | V    | 09   |      | ID Empresa      | X    |      |      |      |
| -> FUNC_ID | V    | 06   |      | ID Funcionário  | X    |      |      |      |
| HOLE_MES   | N    | 02   |      | Mes             | X    |      |      |      |
| HOLE_ANO   | N    | 04   |      | Ano             | X    |      |      |      |
| HORA       | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA       | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS     | C    | 01   |      | Status Registro |      |      |      |      |
| MD5        | C    | 32   |      | Chave MD5       |      |      |      |      |





#### HOLERITE_ITENS

Description: *Movimento do Holerite.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME        | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ----------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| -> CODEMP   | V    | 09   |      | ID Empresa      | X    |      |      |      |
| -> FUNC_ID  | V    | 06   |      | ID Funcionário  | X    |      |      |      |
| -> HOLE_MES | N    | 02   |      | Mes             | X    |      |      |      |
| -> HOLE_ANO | N    | 04   |      | Ano             | X    |      |      |      |
| HOIT_SEQ    | I    |      |      | Sequencia       | X    |      |      |      |
| -> VERB_ID  | V    | 03   |      | ID Verba        |      |      |      |      |
| HOIT_TIPO   | C    | 01   |      | Tipo            |      |      |      |      |
| HOIT_DT     | D    |      |      | Data            |      |      |      |      |
| HOIT_QTD    | N    | 09   | 02   | Quantidade      |      |      |      |      |
| HOIT_VLR    | N    | 14   | 02   | Valor           |      |      |      |      |
| HORA        | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA        | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS      | C    | 01   |      | Status Registro |      |      |      |      |
| MD5         | C    | 32   |      | Chave MD5       |      |      |      |      |



> HOIT\_TIPO = (H=Hora, V=Valor, D=Dias)



#### ESTRUTURA (SG1)

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ------ | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
|        |      |      |      |                 |      |      |      |      |
|        |      |      |      |                 |      |      |      |      |
| HORA   | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA   | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS | C    | 01   |      | Status Registro |      |      |      |      |
| MD5    | C    | 32   |      | Chave MD5       |      |      |      |      |





#### ESTRUTURA_ITENS (SG1)

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ------ | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
|        |      |      |      |                 |      |      |      |      |
|        |      |      |      |                 |      |      |      |      |
| HORA   | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA   | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS | C    | 01   |      | Status Registro |      |      |      |      |
| MD5    | C    | 32   |      | Chave MD5       |      |      |      |      |



​                                            





#### PRODUTO_SALDOS (SB2)

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ------ | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
|        |      |      |      |                 |      |      |      |      |
|        |      |      |      |                 |      |      |      |      |
| HORA   | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA   | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS | C    | 01   |      | Status Registro |      |      |      |      |
| MD5    | C    | 32   |      | Chave MD5       |      |      |      |      |





#### CONTAS_SALDOS (SE8)

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ------ | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
|        |      |      |      |                 |      |      |      |      |
|        |      |      |      |                 |      |      |      |      |
| HORA   | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA   | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS | C    | 01   |      | Status Registro |      |      |      |      |
| MD5    | C    | 32   |      | Chave MD5       |      |      |      |      |



   





#### ATIVOS (ST9/SN1)

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME   | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ------ | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
|        |      |      |      |                 |      |      |      |      |
|        |      |      |      |                 |      |      |      |      |
| HORA   | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA   | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS | C    | 01   |      | Status Registro |      |      |      |      |
| MD5    | C    | 32   |      | Chave MD5       |      |      |      |      |





#### VEICULOS_ABASTECIMENTOS

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] CRUD/MVC
- [ ] Report

| NAME        | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| ----------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| -> CODEMP   | V    | 09   |      | ID Empresa      | X    |      |      |      |
| VEAB_ID     | I    |      |      | ID Lançamento   | X    |      |      |      |
| -> FORN_ID  | V    | 06   |      | ID Fornecedor   |      | X    |      |      |
| -> MOTO_ID  | V    | 06   |      | ID Motorista    |      | X    |      |      |
| -> VEIC_ID  | V    | 10   |      | ID Veiculo      |      | X    |      |      |
| VEAB_DT     | D    |      |      | Data            |      |      |      |      |
| VEAB_KM     | N    | 06   |      | KM              |      |      |      |      |
| VEAB_QTD_LT | N    | 06   | 02   | Qtd. Litros     |      |      |      |      |
| VEAB_VLR_TT | N    | 14   | 02   | Valor Total     |      |      |      |      |
| VEAB_TIPO   | C    | 01   |      | Tipo            |      |      |      |      |
| HORA        | T    |      |      | Hora Alteração  |      |      |      |      |
| DATA        | D    |      |      | Data Alteração  |      |      |      |      |
| STATUS      | C    | 01   |      | Status Registro |      |      |      |      |
| MD5         | C    | 32   |      | Chave MD5       |      |      |      |      |

|













