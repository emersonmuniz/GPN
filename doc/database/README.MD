# portalERP

## PADRÕES DE NOMES

**Nomes de Tabelas (Exemplos)**
1) cliente
2) pedido_venda
3) pedido_venda_item


**Nomes de Campos (Exemplos)**
1)  id 		// Identificador 
2)  nome
3)  dt_compra 	// Data de Compra
4)  vlr_compra 	// Valor de Compra
5)  nro		// Número
6)  qtd		// Quantidade


**Padrão para Abreviatura de Tabelas ou Campos**
- dt   = Data
- nro  = Número
- vlr  = Valor
- qtd  = Quantidade
- grp  = Grupo
- cod  = Código


_ _ _

## ESTRUTURA DAS TABELAS

### empresa
Descrição: *Cadastro de Empresas.*
- [ ] Desenho do BD 
- [ ] SQL Script
- [ ] Modelelo
- [ ] CRUD/MVC
- [ ] Relatório
- [ ] Rest Entrada
- [ ] Rest Saida

| NOME  | TIPO  | TITULO | DESCRIÇÃO |
| ----  | -----  | ----------- | ---- |
| id | integer - PK  | ID | |
| cod_erp | varchar(10) - NN | Código | |
| razao | varchar(100) - NN | Razão Social | |
| fantasia | varchar(50) - NN | Nome de Fantasia | |
| cep | varchar(10) | CEP | |
| endereco | varchar(100) | Endereço | |
| nro | varchar(10) | Número | |
| complemento | varchar(30) | Complemento | |
| bairro | varchar(50) | Bairro | |
| municipio | varchar(50) | Municipio | |
| uf | char(2) | Estado | |
| telefone | varchar(15) | Telefone | |
| cnpj | varchar(20) | CNPJ | |
| ie | varchar(20) | Inscrição Estadual | |
| email | varchar(100) | EMail | |
| url | varchar(100) | Página | |
| logo | text | Logo | |
| obs | text | Observação | |
| dt_inc | datetime | Inclusão | |
| dt_alt | datetime | Alteração | |
| dt_exc | datetime | Exclusão | |

```sql

```
