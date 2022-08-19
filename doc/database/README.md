# MicroSG - Micro Sistema de Gestão

### DEFINIÇÃO DE CAMPOS E TABELAS

**Nome de Tabelas**
1)  cliente
2)  pedido_venda
3)  pedido_venda_itens

**Nome de Campos**
1)  id 
2)  nome
3)  dt_compra ( Data de Compra )
4)  vlr_compra ( Valor de Compra )
5)  nro  ( Número )
6)  qtd ( Quantidade )
6)  dt ( Data )

_ _ _

### ESTRUTURA DAS TABELAS

#### configuracao

Description: *Configurações.*
- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP
- [ ] Rest Web (Rota: )
| NAME | FIELD | DESCRIPTION | NOTE |
| ---- | ----- | ----------- | ---- |
| id | integer | ID | |

```sql

```


- - -

#### uf

Description: *Estados/UF.*
- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP
- [ ] Rest Web (Rota: )
| NAME | FIELD | DESCRIPTION | NOTE |
| ---- | ----- | ----------- | ---- |
| id | integer - PK | ID | |
| uf | char(2) - NN | UF | |
| nome | varchar(100) - NN | Nome | |
| regiao | integer(2) | Região | |
| ibge | integer(2) | Código IBGE | |
| dt_inc | timestamp | Inclusão | |
| dt_alt | timestamp | Alteração | |
| dt_exc | timestamp | Exclusão | |

```sql
id, uf, nome, regiao, ibge, dt_inc, dt_alt, dt_exc

regiao = {
	10:NORTE
	20:NORDESTE
	30:SUDESTE
	40:SUL
	50:CENTRO-OESTE
	99:EXTERIOR
}
```

- - -


#### municipio

Description: *Tabela de Municipios.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP
- [ ] Rest Web (Rota: )
| NAME | FIELD | DESCRIPTION | NOTE |
| ---- | ----- | ----------- | ---- |
| id | integer | ID | |


| ibge   | integer   | 7    |      | Código IBGE |      | x    | x    | CC2_CODMUN |
| uf_id  | integer   |      |      | FK UF       |      | x    |      | CC2_EST    |
| nome   | varchar   | 120  |      | Nome        |      | x    |      | CC2_MUN    |
| dt_inc | timestamp |      |      | Inclusão    |      |      |      |            |
| dt_alt | timestamp |      |      | Alteração   |      |      |      |            |
| status | char      | 1    |      | Status      |      |      |      |            |

```sql
id, ibge, uf_id, nome, dt_inc, dt_alt, status
```

 

#### pais

Description: *Tabela de Países.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP ( Tabela: SYA )
- [ ] Rest Web

| NAME     | TYPE      | SIZE | DEC  | DESCRIPTION     | P    | N    | I    | U    | NOTE     |
| -------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- | -------- |
| id       | integer   |      |      | ID              | x    |      |      |      |          |
| nome     | varchar   | 100  |      | Nome            |      | x    |      |      | YA_DESCR |
| bacen    | integer   | 4    |      | Código BACEN    |      |      | x    |      |          |
| siscomex | integer   | 3    |      | Código Sixcomex |      |      | x    |      | YA_CODGI |
| dt_inc   | timestamp |      |      | Inclusão        |      |      |      |      |          |
| dt_alt   | timestamp |      |      | Alteração       |      |      |      |      |          |
| status   | char      | 1    |      | Status          |      |      |      |      |          |

```sql
id, nome, bacen, siscomex, dt_inc, dt_alt, status
```

  

#### empresa

Description: *Dados da empresa.*

-   [x] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME             | TYPE      | SIZE | D    | DESCRIPTION                   | P    | N    | U    | NOTE |
| ---------------- | --------- | ---- | ---- | ----------------------------- | ---- | ---- | ---- | ---- |
| id               | integer   |      |      | ID                            | x    |      |      |      |
| codigo           | varchar   | 10   |      | Código                        |      |      |      |      |
| id_unidade       | integer   |      |      | ID Unidade (FK)               |      | x    |      |      |
| pessoa           | char      | 1    |      | Pessoa                        |      | x    |      |      |
| razao_social     | varchar   | 100  |      | Razão Social                  |      | x    |      |      |
| nome_fantasia    | varchar   | 50   |      | Nome de Fantasia              |      | x    |      |      |
| cep              | integer   | 10   |      | CEP                           |      |      |      |      |
| endereco         | varchar   | 100  |      | Endereço                      |      |      |      |      |
| numero           | varchar   | 10   |      | Endereço - Número             |      |      |      |      |
| complemento      | varchar   | 30   |      | Complemento                   |      |      |      |      |
| bairro           | varchar   | 50   |      | Bairro                        |      |      |      |      |
| uf_id            | integer   |      |      | FK UF                         |      | x    |      |      |
| municipio_id     | integer   |      |      | FK Municipio                  |      | x    |      |      |
| pais_id          | integer   |      |      | FK Pais                       |      | x    |      |      |
| telefone         | varchar   | 15   |      | Telefone                      |      |      |      |      |
| cnpj_cpf         | varchar   | 20   |      | CNPJ                          |      |      |      |      |
| insc_estadual    | varchar   | 20   |      | Inscrição Estadual            |      |      |      |      |
| Insc_municipal   | varchar   | 20   |      | Inscrição Municipal           |      |      |      |      |
| cnae_primario    | integer   | 7    |      | CNAE Primário                 |      |      |      |      |
| dt_fundacao      | date      |      |      | Data de fundação              |      |      |      |      |
| simples_nacional | char      | 1    |      | Optante pelo Simples Nacional |      |      |      |      |
| nome_contador    | varchar   | 100  |      | Nome do Contador              |      |      |      |      |
| crc_contador     | varchar   | 20   |      | CRC do Contador               |      |      |      |      |
| cpf_contador     | varchar   | 20   |      | CPF do Contador               |      |      |      |      |
| email            | varchar   | 100  |      | E-Mail                        |      |      |      |      |
| url              | varchar   | 100  |      | URL                           |      |      |      |      |
| logo             | text      |      |      | Logo                          |      |      |      |      |
| dt_inc           | timestamp |      |      | Inclusão                      |      |      |      |      |
| dt_alt           | timestamp |      |      | Alteração                     |      |      |      |      |

> Pessoa = F:Fisica, J:Juridica



#### empresa_socio

Description: *Sócios da Empresa.*

-   [x] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME       | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE |
| ---------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | ---- |
| id         | integer   |      |      | ID          | x    |      |      |      |
| empresa_id | integer   |      |      | FK  Empresa |      |      |      |      |
| cpf        | varchar   | 20   |      | CPF         |      | x    |      |      |
| nome       | varchar   | 100  |      | Nome        |      | x    |      |      |
| quota      | double    | 5    | 2    | % Quota     |      |      |      |      |
| dt_inc     | timestamp |      |      | Inclusão    |      |      |      |      |
| dt_alt     | timestamp |      |      | Alteração   |      |      |      |      |

 

#### ctb_historico

Description: *Histórico Contábil.*

-   [x] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CTB)
-   [ ] Report

| NAME       | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE     |
| ---------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | -------- |
| id         | integer   |      |      | ID          | x    |      |      |          |
| empresa_id | integer   |      |      | ID Empresa  |      |      |      |          |
| codigo     | varchar   | 3    |      | Código      |      | x    | x    | CT8_HIST |
| descricao  | varchar   | 100  |      | Descrição   |      | x    |      | CT8_DESC |
| dt_inc     | timestamp |      |      | Inclusão    |      |      |      |          |
| dt_alt     | timestamp |      |      | Alteração   |      |      |      |          |
| status     | char      | 1    |      | Status      |      |      |      |          |

 

#### ctb_conta

Description: *Plano de Contas.*

-   [x] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CT1)
-   [ ] Report

| NAME             | TYPE      | SIZE | D    | DESCRIPTION         | P    | N    | U    | NOTE       |
| ---------------- | --------- | ---- | ---- | ------------------- | ---- | ---- | ---- | ---------- |
| id               | integer   |      |      | ID                  | x    |      |      |            |
| empresa_id       | integer   |      |      | ID Empresa          |      | x    |      |            |
| codigo           | varchar   | 20   |      | Conta               |      | x    | x    | CT1_CONTA  |
| codigo_superior  | varchar   | 20   |      | Conta Superior      |      |      |      | CT1_CTASUP |
| codigo_reduzido  | integer   | 4    |      | Código Reduzido     |      |      | x    | CT1_RES    |
| descricao        | varchar   | 100  |      | Descrição           |      | x    |      | CT1_DESC01 |
| ativa            | char      | 1    |      | Ativa               |      | x    |      | CT1_BLOQ   |
| classe           | char      | 1    |      | Classe              |      | x    |      | CT1_CLASSE |
| natureza         | char      | 1    |      | Natureza Normal     |      |      |      | CT1_NORMAL |
| ctb_historico_id | integer   |      |      | ID Historico Padrao |      |      |      | CT1_HP     |
| dt_inc           | timestamp |      |      | Inclusão            |      |      |      |            |
| dt_alt           | timestamp |      |      | Alteração           |      |      |      |            |
| status           | char      | 1    |      | Status              |      |      |      |            |

>   classe = A:Analitico (2), S:Sintético (1)
>
>   natureza =  R:Receita (2), D:Despesa (1)
>
>   ativa = S:Sim (2), N:Não (1)

 



#### contabil_lancamento_padrao

Description: *Lancamento Contabil Padrão.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CT5)
-   [ ] Report

| NAME                      | T    | S    | D    | DESCRIPTION        | PK   | NN   | IN   | NOTE        |
| ------------------------- | ---- | ---- | ---- | ------------------ | ---- | ---- | ---- | ----------- |
| id                        | i    |      |      | ID                 | x    |      |      |             |
| codigo                    | v    | 3    |      | Código             |      | x    |      | CT5_LANPAD  |
| descricao                 | v    | 100  |      | Descrição          |      | x    |      | CT5_DESC    |
| tipo                      | c    | 1    |      | Tipo               |      | x    |      | CT5_DC      |
| ativo                     | c    | 1    |      | Ativo              |      | x    |      | CT5_STATUS  |
| contabil_conta_id_credito | i    |      |      | ID Conta Crédito   |      |      |      | CT5_CREDITO |
| contabil_conta_id_debito  | i    |      |      | ID Conta  Débito   |      |      |      | CT5_DEBITO  |
| contabil_historico_id     | i    |      |      | Histórico Contábil |      |      |      |             |
| historico                 | t    |      |      | Histórico          |      |      |      | CT5_HIST    |
| observacao                | t    |      |      | Observacao         |      |      |      | CT5_OBS     |
| data_inclusao             | t    |      |      |                    |      |      |      |             |
| data_alteracao            | t    |      |      |                    |      |      |      |             |
| status                    | c    | 1    |      | Status             |      |      |      |             |

>   tipo - D:Débito (1), C:Crédito (2), X:Partida Dobrada (3)
>   
>ativo - S:Sim (1), N:Não (2)

 

#### contabil_periodo

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CTG)
-   [ ] Report

| NAME         | TYPE      | SIZE | D    | DESCRIPTION      | P    | N    | U    | NOTE       |
| ------------ | --------- | ---- | ---- | ---------------- | ---- | ---- | ---- | ---------- |
| id           | integer   |      |      | ID               | x    |      |      |            |
| empresa_id   | integer   |      |      | ID Empresa       |      | x    |      |            |
| codigo       | varchar   | 3    |      | Código           |      | x    | x    | CTG_CALEND |
| ano          | integer   | 4    |      | Ano de Exercicio |      | x    |      | CTG_EXERC  |
| dt_inicial   | date      |      |      | Data Incial      |      |      |      | CTG_DTINI  |
| dt_final     | date`     |      |      | Data Final       |      |      |      | CTG_DTFIM  |
| status_atual | char      | 1    |      | Status Atual     |      |      |      | CTG_STATUS |
| dat_inc      | timestamp |      |      | Inclusão         |      |      |      |            |
| dat_alt      | timestamp |      |      | Alteração        |      |      |      |            |
| status       | char      | 1    |      | Status           |      |      |      |            |

> sta_atu = A:Aberto (1), F:Fechado (2), T:Transportado (3), B:Bloqueado (4)

 

#### **ctb_centro_custo**

-   [x] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CTT)
-   [ ] Report

| NAME            | TYPE      | SIZE | D    | DESCRIPTION    | P    | N    | U    | NOTE       |
| --------------- | --------- | ---- | ---- | -------------- | ---- | ---- | ---- | ---------- |
| id              | integer   |      |      | ID             | x    |      |      |            |
| empresa_id      | integer   |      |      | FK Empresa     |      |      |      |            |
| codigo          | varchar   | 10   |      | Código         |      | x    | x    | CTT_CUSTO  |
| codigo_superior | varchar   | 10   |      | Conta Superior |      |      |      | CTT_CCSUP  |
| descricao       | varchar   | 100  |      | Descrição      |      | x    |      | CTT_DESC01 |
| ativo           | char      | 1    |      | Ativo          |      | x    |      | CTT_BLOQ   |
| classe          | char      | 1    |      | Classe         |      | x    |      | CT2_CLASSE |
| natureza        | char      | 1    |      | Condição       |      | x    |      | CTT_NORMAL |
| dt_inc          | timestamp |      |      | Inclusão       |      |      |      |            |
| dt_alt          | timestamp |      |      | Alteração      |      |      |      |            |
| status          | char      | 1    |      | Status         |      |      |      |            |

>   classe - S:Sintético (1), A:Analitico (2)
>
>   condicao = N:Nenhuma, D:Despesa (1), R:Receita (3)
>
>   ativo = S:Sim (2), N:Não (1)



#### contabil_movimento

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CT2)
-   [ ] Report

| NAME          | TYPE      | SIZE | D    | DESCRIPTION                | P    | N    | U    | NOTE       |
| ------------- | --------- | ---- | ---- | -------------------------- | ---- | ---- | ---- | ---------- |
| id            | integer   |      |      | ID                         | x    |      |      |            |
| empresa_id    | integer   |      |      | ID Empresa                 |      | x    |      |            |
| dt_lcto       | date      |      |      | Data                       |      | x    |      | CT2_DATA   |
| tipo          | char      | 1    |      | Tipo                       |      | x    |      | CT2_DC     |
| ct_cta_deb_id | iinteger  |      |      | FK Conta                   |      |      |      | CT2_DEBITO |
| ct_cta_cre_id | integer   |      |      | FK Conta                   |      |      |      | CT2_CREDIT |
| cc_deb_id     | integer   |      |      | FK Centro de Custo Debito  |      |      |      | CT2_CCD    |
| cc_cre_id     | integer   |      |      | FK Centro de Custo Credito |      |      |      | CT2_CCC    |
| valor         | double    | 18   | 2    | Valor                      |      | x    |      | CT2_VALOR  |
| ct_his_id     | integer   |      |      | FK Histórico               |      |      |      | CT2_HP     |
| historico     | text      |      |      | Histórico                  |      | x    |      | CT2_HIST   |
| dat_inc       | timestamp |      |      | Inclusão                   |      |      |      |            |
| dat_alt       | timestamp |      |      | Alteração                  |      |      |      |            |
| status        | char      | 1    |      | Status                     |      |      |      |            |

>   tipo - D:Débito (1), C:Crédito (2), P:Partida Dobrada (3), L:Lancamento Padrão (6)

 



#### contabil_saldo

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: CT7)
-   [ ] Report

| NAME        | TYPE      | SIZE | D    | DESCRIPTION            | P    | N    | U    | NOTE        |
| ----------- | --------- | ---- | ---- | ---------------------- | ---- | ---- | ---- | ----------- |
| id          | integer   |      |      | ID                     | x    |      |      |             |
| empresa_id  | integer   |      |      | ID Empresa             |      | x    |      |             |
| ct_cta_id   | integer   |      |      | FK Plano de Contas     |      | x    |      | CT7_CONTA   |
| dt_saldo    | date      |      |      | Data                   |      |      |      | CT7_DATA    |
| tt_deb      | double    | 18   | 2    | Total de Debito        |      |      |      | CT7_DEBITO  |
| tt_cre      | double    | 18   | 2    | Total de Credito       |      |      |      | CT7_CREDITO |
| status_sld  | char      | 1    |      | Status do Saldo        |      |      |      | CT7_STATUS  |
| sld_atu_dev | double    | 18   | 2    | Saldo Atual Devedor    |      |      |      | CT7_ATUDEB  |
| sld_atu_cre | double    | 18   | 2    | Saldo Atual Credor     |      |      |      | CT7_ATUCRD  |
| sld_ant_dev | double    | 18   | 2    | Saldo Anterior Devedor |      |      |      | CT7_ANTDEB  |
| sld_ant_cre | double    | 18   | 2    | Saldo Anterior Credor  |      |      |      | CT7_ANTCRD  |
| dat_inc     | timestamp |      |      |                        |      |      |      |             |
| dat_alt     | timestamp |      |      |                        |      |      |      |             |
| status      | char      | 1    |      |                        |      |      |      |             |

>   sta_sld = A:Aberto (1), E:Encerrado (2)





#### regiao_venda

Description: *Cadastro de Região de Venda.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Rest Web
- [ ] Rest ERP (Tabela: SZ4)
- [ ] Report

| NAME       | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE      |
| ---------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | --------- |
| id         | integer   |      |      | ID          | x    |      |      |           |
| empresa_id | integer   |      |      | FK Empresa  |      |      |      |           |
| codigo     | varchar   | 3    |      | Código      |      | x    | x    | Z4_CODIGO |
| descricao  | varchar   | 50   |      | Descrição   |      | x    |      | Z4_DESC   |
| ativo      | char      | 1    |      | Ativo       |      | x    |      | Z4_MSBLQL |
| observacao | text      |      |      | Observação  |      |      |      | Z4_OBS    |
| dt_inc     | timestamp |      |      |             |      |      |      |           |
| dt_alt     | timestamp |      |      |             |      |      |      |           |
| status     | char      | 1    |      | Status      |      |      |      |           |

> ativo = S:Sim (1), N:Não (2)

```sql

```

 

#### regiao_entrega

Description: *Cadastro de Região de Venda.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Rest Web
- [ ] Rest ERP (Tabela: SZ4)
- [ ] Report

| NAME       | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE |
| ---------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | ---- |
| id         | integer   |      |      | ID          | x    |      |      |      |
| empresa_id | integer   |      |      | FK Empresa  |      |      |      |      |
| codigo     | varchar   | 3    |      | Código      |      | x    | x    |      |
| descricao  | varchar   | 50   |      | Descrição   |      | x    |      |      |
| ativo      | char      | 1    |      | Ativo       |      |      |      |      |
| obs        | text      |      |      | Observação  |      |      |      |      |
| datinc     | timestamp |      |      |             |      |      |      |      |
| datalt     | timestamp |      |      |             |      |      |      |      |
| status     | char      | 1    |      | Status      |      |      |      |      |

> ativo = S:Sim (1), N:Não (2)

```sql

```

 

#### sindicato

Description: *Tabela de Sindicatos.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP ( RCE )
- [ ] Rest Web (  )

| NAME         | T        | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE       |
| ------------ | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id           | integer  |      |      | ID              | X    |      |      |            |
| empresa_id   | integer  |      |      | FK Empresa      |      |      |      | RCE_FILIAL |
| codigo       | varchar  | 06   |      | Código          |      |      |      | RCE_CODIGO |
| descricao    | varchar  | 100  |      | Descrição       |      | X    |      | RCE_DESCRI |
| cep          | varchar  | 10   |      | CEP             |      |      |      | RCE_CEP    |
| endereco     | varchar  | 100  |      | Endereço        |      |      |      | RCE_ENDER  |
| complemento  | varchar  | 30   |      | Complemento     |      |      |      | RCE_COMPLE |
| bairro       | varchar  | 50   |      | Bairro          |      |      |      | RCE_BAIRRO |
| municipio_id | integer  |      |      | FK Municipio    |      |      |      | RCE_DESCM  |
| uf_id        | integer  |      |      | FK UF           |      |      |      | RCE_UF     |
| cod_entidade | varchar  | 15   |      | Código Entidade |      |      |      | RCE_ENTSIN |
| telefone     | varchar  | 15   |      | Telefone        |      |      |      | RCE_FONE   |
| email        | varchar  | 100  |      | E-Mail          |      |      |      | RCE_EMAIL  |
| observacao   | text     |      |      | Observação      |      |      |      |            |
| dt_inc       | datetime |      |      | Inclusão        |      |      |      |            |
| dt_alt       | datetime |      |      | Alteração       |      |      |      |            |
| status       | char     | 1    |      | Registro        |      |      |      |            |

```sql
<chave> AS id, <DePara> AS empresa_id, RCE_CODIGO AS codigo_erp, RCE_DESCRI AS descricao, RCE_ENDER AS endereco, RCE_COMPLE AS complemento, RCE_BAIRRO AS bairro, RCE_DESCM AS municipio, RCE_UF AS <uf_id>, RCE_CEP AS cep, RCE_ENTSIN AS cod_entidade, RCE_FONE AS telefone, RCE_EMAIL AS email, dt_inc, dt_alt, status
```



#### departamento

Description: *Tabela de Departamentos.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: SQB)
- [ ] Rest Web

| NAME      | T        | S    | D    | DESCRIPTION | PK   | NN   | UN   | NOTE       |
| --------- | -------- | ---- | ---- | ----------- | ---- | ---- | ---- | ---------- |
| id        | integer  |      |      | ID          | X    |      |      |            |
| empresa   | integer  |      |      | FK Empresa  |      |      |      |            |
| codigo    | varchar  | 6    |      | Código      |      |      |      | QB_DEPTO   |
| descricao | varchar  | 50   |      | Descrição   |      | X    |      | QB_DESCRIC |
| dt_inc    | datetime |      |      | Inclusão    |      |      |      |            |
| dt_alt    | datetime |      |      | Alteração   |      |      |      |            |
| status    | char     | 1    |      | Status      |      |      |      |            |

```sql
<chave> AS id, <DePara> AS <empresa_id>, QB_DEPTO AS codigo, QB_DESCRIC AS descricao, dt_inc, dt_alt, status
```



####  cargo

Description: *Tabela de Cargos.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (SQ3)
- [ ] Rest Web

| NAME            | T        | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE       |
| --------------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id              | integer  |      |      | ID              | X    |      |      |            |
| empresa_id      | integer  |      |      | FK Empresa      |      |      |      | Q3_FILIAL  |
| codigo          | varchar  | 6    |      | Cargo           |      |      |      | Q3_CARGO   |
| descricao       | varchar  | 50   |      | Descrição       |      | X    |      | Q3_DESCSUM |
| detalhe         | text     |      |      | Detalhe         |      |      |      | Q3_MEMO    |
| departamento_id | integer  |      |      | FK Departamento |      | X    |      | Q3_DEPTO   |
| dt_inc          | datetime |      |      | Inclusão        |      |      |      |            |
| dt_alt          | datetime |      |      | Alteração       |      |      |      |            |
| status          | char     | 1    |      | Status          |      |      |      |            |

```sql
<chave> AS id, <DePara> AS empresa_id, Q3_CARGO AS codigo_erp, Q3_DESCSUM AS descricao, Q3_MEMO AS detalhe, Q3_DEPTO AS <departamento_id>, dt_inc, dt_alt, status
```

 

#### funcao

Description: *Tabela de Funções.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (SRJ)
- [ ] Rest Web

| NAME        | T        | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE       |
| ----------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id          | integer  |      |      | ID              | X    |      |      |            |
| empresa_id  | integer  |      |      | FK Empresa      |      |      |      | RJ_FILIAL  |
| codigo      | varchar  | 6    |      | Função          |      |      |      | RJ_FUNCAO  |
| descricao   | varchar  | 50   |      | Descrição       |      | X    |      | RJ_DESC    |
| cargo_id    | integer  |      |      | FK Cargo        |      |      |      | RJ_CARGO   |
| vlr_salario | double   | 14   | 2    | Salario         |      |      |      | RJ_SALARIO |
| dt_inc      | datetime |      |      | Data Alteração  |      |      |      |            |
| dt_alt      | datetime |      |      | Hora Alteração  |      |      |      |            |
| status      | char     | 1    |      | Status Registro |      |      |      |            |

```sql
<chave> AS id, <DePara> AS empresa_id, RJ_FUNCAO AS codigo_erp, RJ_DESC AS descricao, RJ_CARGO AS <cargo_id>, RJ_SALARIO AS vlr_salario, dt_inc, dt_alt, status
```

 

#### estado_civil

Description: *Tabela de Estado Civil.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (SX5 = 33)
- [ ] Rest Web

| NAME       | T        | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| ---------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| id         | integer  |      |      | ID              | X    |      |      |           |
| empresa_id | integer  |      |      | FK Empresa      |      |      |      |           |
| codigo     | varchar  | 6    |      | Código          |      | X    |      | X5_CHAVE  |
| descricao  | varchar  | 50   |      | Descrição       |      | X    |      | X5_DESCRI |
| dt_inc     | datetime |      |      | Data Alteração  |      |      |      |           |
| dt_alt     | datetime |      |      | Hora Alteração  |      |      |      |           |
| status     | char     | 1    |      | Status Registro |      |      |      |           |



```sql
<chave> AS id, <DePara> AS empresa_id, X5_CHAVE AS codigo_erp, X5_DESCRI AS descricao, dt_inc, dt_alt, status, WHERE X5_TABELA = '33'
```



####  funcionario

Description: *Cadastro de Funcionários.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP ( SRA )
- [ ] Rest Web

| NAME            | T        | S    | D    | DESCRIPTION        | PK   | UN   | IN   |            |
| --------------- | -------- | ---- | ---- | ------------------ | ---- | ---- | ---- | ---------- |
| id              | integer  |      |      | ID                 | X    |      |      |            |
| empresa_id      | integer  |      |      | FK Empresa         |      |      |      | RA_FILIAL  |
| codigo          | varchar  | 6    |      | Código             |      | X    |      | RA_MAT     |
| nome            | varchar  | 100  |      | Nome               |      | X    |      | RA_NOME    |
| nome_social     | varchar  | 50   |      | Nome Social        |      |      |      | RA_NSOCIAL |
| apelido         | varchar  | 30   |      | Apelido            |      |      |      |            |
| cep             | varchar  | 10   |      | CEP                |      |      |      | RA_CEP     |
| endereco        | varchar  | 100  |      | Endereço           |      |      |      | RA_ENDEREC |
| complemento     | varchar  | 30   |      | Complemento        |      |      |      | RA_COMPLEM |
| bairro          | varchar  | 50   |      | Bairro             |      |      |      | RA_BAIRRO  |
| uf_id           | integer  |      |      | FK UF              |      |      |      | RA_ESTADO  |
| municipio_id    | integer  |      |      | FK Municipio       |      |      |      | RA_CODMUN  |
| cpf             | varchar  | 20   |      | CPF                |      |      |      | RA_CIC     |
| rg              | varchar  | 20   |      | RG                 |      |      |      | RA_RG      |
| pis             | varchar  | 20   |      | PIS                |      |      |      | RA_PIS     |
| dt_nascimento   | date     |      |      | Data de Nascimento |      |      |      | RA_NASC    |
| ctps_nro        | varchar  | 20   |      | Numero CTPS        |      |      |      | RA_NUMCP   |
| ctps_serie      | varchar  | 10   |      | Série CTPS         |      |      |      | RA_SERCP   |
| ctps_uf_id      | char     | 2    |      | UF CTPS            |      |      |      | RA_UFCP    |
| cnh             | varchar  | 20   |      | CNH                |      |      |      | RA_HABILIT |
| reservista      | varchar  | 20   |      | Reservista         |      |      |      | RA_RESERVI |
| titulo_eleitor  | varchar  | 20   |      | Titulo de Eleitor  |      |      |      | RA_TITULOE |
| zona_eleitoral  | varchar  | 5    |      | Zona Eleitoral     |      |      |      | RA_ZONASEC |
| secao_eleitoral | varchar  | 5    |      | Seção Eleitoral    |      |      |      | RA_SECAO   |
| sexo            | char     | 1    |      | Sexo               |      |      |      | RA_SEXO    |
| estado_civil_id | integer  |      |      | FK Estado Civil    |      |      |      | RA_ESTCIVI |
| telefone        | varchar  | 15   |      | Telefone           |      |      |      | RA_TELEFON |
| naturalidade    | varchar  | 50   |      | Naturalidade       |      |      |      | RA_NATURAL |
| mae             | varchar  | 50   |      | Nome da Mae        |      |      |      | RA_MAE     |
| pai             | varchar  | 50   |      | Nome do Pai        |      |      |      | RA_PAI     |
| dt_admissao     | date     |      |      | Data de Admissao   |      |      |      | RA_ADMISSA |
| dt_demissao     | date     |      |      | Data de Demisao    |      |      |      | RA_DEMISSA |
| departamento_id | integer  |      |      | FK Departamento    |      |      |      | RA_DEPTO   |
| funcao_id       | integer  |      |      | FK Função          |      |      |      | RA_CODFUNC |
| cargo_id        | integer  |      |      | FK Cargo           |      |      |      | RA_CARGO   |
| sindicato_id    | integer  |      |      | FK Sindicato       |      |      |      | RA_SINDICA |
| vlr_salario     | double   | 14   | 2    | Salario            |      |      |      |            |
| foto            | text     |      |      | Foto               |      |      |      | RA_BITMAP  |
| observacao      | text     |      |      | Observação         |      |      |      |            |
| dt_inc          | datetime |      |      | Data Alteração     |      |      |      |            |
| dt_alt          | datetime |      |      | Hora Alteração     |      |      |      |            |
| status          | char     | 1    |      | Status Registro    |      |      |      |            |

sexo = M:Masculino, F:Feminino, O:Outro

```sql
<chave> AS id, <DePara> AS empresa_id, RA_MAT AS codigo_erp, RA_NOME AS nome, RA_NSOCIAL AS nome_social, <apelido> AS apelido, RA_CEP AS cep, RA_ENDEREC AS endereco, RA_COMPLEM AS complemento, RA_BAIRRO AS bairro, RA_ESTADO AS uf_id, RA_CODMUN AS municipio_id, RA_CIC AS cpf, RA_RG AS rg, RA_PIS AS pis, RA_NASC AS dt_nascimento, RA_NUMCP AS ctps_nro, RA_SERCP AS ctps_serie, RA_UFCP AS ctps_uf_id, RA_HABILIT AS cnh, RA_RESERVI AS reservista, RA_TITULOE AS titulo_eleitor, RA_ZONASEC AS zona_eleitoral, RA_SECAO AS secao_eleitoral, RA_SEXO AS sexo, RA_ESTCIVI AS <estado_civil_id>, RA_TELEFON AS telefone, RA_NATURAL AS naturalidade, RA_MAE AS mae, RA_PAI AS pae, RA_ADMISSA AS dt_admissao, RA_DEMISSA AS dt_demissao, RA_DEPTO AS <departamento_id>, RA_CODFUNC AS <funcao_id>, RA_CARGO AS <cargo_id>, RA_SINDICA AS <sindicato_id>, RA_BITMAP AS foto, obs, dt_inc, dt_alt, status
```



#### funcionario_dependente

Description: *Cadastro de Dependentes por Funcionário.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (SRB)
- [ ] Rest Web

| NAME            | T        | S    | D    | DESCRIPTION        | PK   | NN   | IN   | NOTE       |
| --------------- | -------- | ---- | ---- | ------------------ | ---- | ---- | ---- | ---------- |
| id              | integer  |      |      | ID                 | X    |      |      |            |
| funcionario_id  | integer  |      |      | FK Funcionario     |      |      |      |            |
| nome            | varchar  | 100  |      | Nome               |      | X    |      | RB_NOME    |
| dt_nascimento   | date     |      |      | Data de Nascimento |      | X    |      | RB_DTNASC  |
| sexo            | char     | 1    |      | Sexo               |      |      |      | RB_SEXO    |
| grau_parentesco | char     | 1    |      | Grau de Parentesco |      |      |      | RB_GRAUPAR |
| cpf             | varchar  | 20   |      | CPF                |      |      |      | RB_CIC     |
| dt_inc          | datetime |      |      | Data Alteração     |      |      |      |            |
| dt_alt          | datetime |      |      | Hora Alteração     |      |      |      |            |
| status          | char     | 1    |      | Status Registro    |      |      |      |            |

sexo = M:Masculino, F:Feminino, O:Outro

grau_parentesco = C:Conjuge/Companheiro, F:Filho, E:Enteado, P:Pai/Mãe, O:Agregado/Outros

```sql
<chave> AS id, <funcionario_id> AS funcionarios_id, RB_NOME AS nome, RB_DTNASC AS dt_nascimento, RB_SEXO As sexo, RB_GRAUPAR AS grau_parentesco, RB_CIC AS cpf, dt_inc, dt_alt, status
```

 



#### vendedor

Description: *Cadastro de Vendedores.*

- [x] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Rest Web
- [ ] Rest ERP (Tabela: SA3)
- [ ] Report

| NAME            | TYPE      | SIZE | D    | DESCRIPTION           | P    | N    | U    | NOTE       |
| --------------- | --------- | ---- | ---- | --------------------- | ---- | ---- | ---- | ---------- |
| id              | integer   |      |      | ID                    | x    |      |      |            |
| codigo          | varchar   | 6    |      | Código                |      | x    | x    | A3_COD     |
| ativo           | char      | 1    |      | Ativo                 |      | x    |      | A3_MSBLQL  |
| pessoa          | char      | 1    |      | Pessoa                |      |      |      |            |
| nome            | varchar   | 100  |      | Nome                  |      | x    |      | A3_NOME    |
| reduzido        | varchar   | 30   |      | Nome Reduzido         |      |      |      | A3_NREDUZ  |
| cep             | varchar   | 10   |      | CEP                   |      |      |      | A3_CEP     |
| endereco        | varchar   | 100  |      | Endereço              |      |      |      | A3_END     |
| nro             | varchar   | 10   |      | Endereço - Número     |      |      |      |            |
| complemento     | varchar   | 30   |      | Complemento           |      |      |      |            |
| bairro          | varchar   | 50   |      | Bairro                |      |      |      | A3_BAIRRO  |
| uf_id           | integer   |      |      | FK UF                 |      |      |      | A3_EST     |
| municipio_id    | integer   |      |      | FK Municipio          |      |      |      | A3_MUN     |
| pais_id         | integer   |      |      | FK Pais               |      |      |      | A3_PAIS    |
| telefone        | varchar   | 15   |      | Telefone              |      |      |      | A3_TEL     |
| celular         | varchar   | 15   |      | Celular               |      |      |      | A3_CEL     |
| cnpj_cpf        | varchar   | 20   |      | CNPJ/CPF              |      |      |      | A3_CGC     |
| ie_rg           | varchar   | 20   |      | Inscrição Estadual/RG |      |      |      | A3_INSCR   |
| email           | varchar   | 100  |      | Email                 |      |      |      | A3_EMAIL   |
| funcionario_id  | integer   |      |      | FK Funcionario        |      |      |      |            |
| dt_admissao     | date      |      |      | Data de Admissão      |      |      |      | A3_ADMISS  |
| dt_demissao     | date      |      |      | Data de Demissão      |      |      |      |            |
| tipo            | char      | 1    |      | Tipo                  |      | x    |      | A3_TIPO    |
| ven_sup_id      | integer   |      |      | ID Supervisor         |      |      |      | A3_SUPER   |
| ven_ger_id      | integer   |      |      | ID Gerente            |      |      |      | A3_GEREN   |
| regiao_venda_id | integer   |      |      | FK Regiao de Venda    |      |      |      | A3_REGIAO  |
| comissao        | double    | 5    | 2    | % Comissão            |      |      |      | A3_COMIS   |
| pg_emissao      | integer   | 3    |      | % Pago na Emissão     |      |      |      | A3_ALEMISS |
| pg_baixa        | integer   | 3    |      | % Pago na Baixa       |      |      |      | A3_ALBAIXA |
| base_comissao   | char      | 1    |      | Base Comissão         |      |      |      |            |
| observacao      | text      |      |      | Observação            |      |      |      |            |
| foto            | text      |      |      | Caminho Foto          |      |      |      |            |
| dt_inc          | timestamp |      |      |                       |      |      |      |            |
| dt_alt          | timestamp |      |      |                       |      |      |      |            |
| status          | char      | 1    |      | Status                |      |      |      |            |


> pessoa = F:Fisica, J:Juridica
>
> ativo = S:Sim (1), N:Não (2)
>
> tipo = ( I:Interno, E:Externo, P:Parceiro )
>
> base_comissao = (P:Total Produto, N:Total NF)

```sql

```

 



#### armazem

Description: *Tabela de Armazens/Depósitos.*

-   [x] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: NNR)
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE       |
| --------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | ---------- |
| id        | integer   |      |      | ID          | x    |      |      |            |
| codigo    | varchar   | 3    |      | Código      |      | x    | x    | NNR_CODIGO |
| descricao | varchar   | 50   |      | Descrição   |      | x    |      | NNR_DESCRI |
| tipo      | char      | 1    |      | Tipo        |      |      |      | NNR_TIPO   |
| dt_inc    | timestamp |      |      |             |      |      |      |            |
| dt_alt    | timestamp |      |      |             |      |      |      |            |
| status    | char      | 1    |      | Status      |      |      |      |            |

>   tipo = ( 1:Padrao, 2:Proprio, 3:Terceiro)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### classe_financeira

Description: *Lançamentos Bancario/Caixas.*

-   [x] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SED)
-   [ ] Rest Web

| NAME      | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE       |
| --------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id        | integer   |      |      | ID              | x    |      |      |            |
| codigo    | varchar   | 10   |      | Código          |      | x    |      | ED_CODIGO  |
| superior  | varchar   | 10   |      | Código Superior |      |      |      |            |
| descricao | varchar   | 50   |      | Descrição       |      | x    |      | ED_DESCRIC |
| dt_inc    | timestamp |      |      | Data Alteração  |      |      |      |            |
| dt_alt    | timestamp |      |      | Hora Alteração  |      |      |      |            |
| status    | char      | 1    |      | Status Registro |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



#### produto_tipo

Description: *Tabelas Genéricas - Tipo de Produto.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SX5, Chave: 02)
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE      |
| --------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| id        | integer   |      |      | ID              | x    |      |      |           |
| codigo    | varchar   | 3    |      | Chave           |      | x    | x    | X5_CHAVE  |
| descricao | varchar   | 100  |      | Descrição       |      | x    |      | X5_DESCRI |
| datinc    | timestamp |      |      | Data Alteração  |      |      |      |           |
| datalt    | timestamp |      |      | Hora Alteração  |      |      |      |           |
| status    | char      | 1    |      | Status Registro |      |      |      |           |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
MC:Material de Consumo
MP:Materia Prima
PA:Produto Acabado
PF:Produto Fabricado
SR:Servicos
CO:Consignacao
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### produto_origem

Description: *Tabelas Genéricas.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD?MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SX5, Chave: S0)
-   [ ] Report

| NAME      | TYPE | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE      |
| --------- | ---- | ---- | ---- | ----------- | ---- | ---- | ---- | --------- |
| Id        | i    |      |      | ID          | x    |      |      |           |
| codigo    | v    | 3    |      | Chave       |      | x    | x    | X5_CHAVE  |
| descricao | v    | 100  |      | Descrição   |      | x    |      | X5_DESCRI |
| datinc    | t    |      |      |             |      |      |      |           |
| datalt    | t    |      |      |             |      |      |      |           |
| status    | c    | 1    |      | Status      |      |      |      |           |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### produto_familia

Description: *Tabela de Familia de Produtos.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE     |
| --------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | -------- |
| id        | integer   |      |      | ID          | x    |      |      |          |
| codigo    | varchar   | 3    |      | Código      |      | x    | x    | BM_GRUPO |
| descricao | varchar   | 50   |      | Descrição   |      | x    |      | BM_DESC  |
| datinc    | timestamp |      |      |             |      |      |      |          |
| datalt    | timestamp |      |      |             |      |      |      |          |
| status    | Char      | 1    |      | Status      |      |      |      |          |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### produto_grupo

Description: *Tabela de Grupo de Produtos.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SBM)
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE     |
| --------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | -------- |
| id        | integer   |      |      | ID          | x    |      |      |          |
| codigo    | varchar   | 3    |      | Código      |      | x    | x    | BM_GRUPO |
| descricao | varchar   | 50   |      | Descrição   |      | x    |      | BM_DESC  |
| datnc     | timestamp |      |      |             |      |      |      |          |
| datalt    | timestamp |      |      |             |      |      |      |          |
| status    | Char      | 1    |      | Status      |      |      |      |          |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### unidade_medida

Description: *Tabela de Unidades de Produtos.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SAH)
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION   | P    | N    | U    | NOTE      |
| --------- | --------- | ---- | ---- | ------------- | ---- | ---- | ---- | --------- |
| id        | integer   |      |      | ID            | x    |      |      |           |
| codigo    | char      | 2    |      | Un. Medida    |      | x    | x    | AH_UNIMED |
| descricao | varchar   | 20   |      | Nome Resumido |      | x    |      | AH_UMRES  |
| datinc    | timestamp |      |      |               |      |      |      |           |
| datalt    | timestamp |      |      |               |      |      |      |           |
| status    | Char      | 1    |      | Status        |      |      |      |           |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### ncm

Description: *Tabela de NCM.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: NCM)
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION         | P    | N    | U    | NOTE       |
| --------- | --------- | ---- | ---- | ------------------- | ---- | ---- | ---- | ---------- |
| id        | integer   |      |      | ID                  | x    |      |      |            |
| codigo    | varchar   | 10   |      | Código (9999.99.99) |      | x    | x    | YD_TEC     |
| descricao | varchar   | 100  |      | Descrição           |      | x    |      | YD_DESC_P  |
| obs       | text      |      |      | Observação          |      |      |      | YD_VM_TEXT |
| datinc    | timestamp |      |      | Data Alteração      |      |      |      |            |
| datalt    | timestamp |      |      | Hora Alteração      |      |      |      |            |
| status    | char      | 1    |      | Status Registro     |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~







#### condicao_pagamento

Description: *Tabela de Condições de Pagamento.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SE4)
-   [ ] Report

| NAME           | TYPE      | SIZE | D    | DESCRIPTION                  | P    | N    | U    | NOTE      |
| -------------- | --------- | ---- | ---- | ---------------------------- | ---- | ---- | ---- | --------- |
| id             | integer   |      |      | ID                           | x    |      |      |           |
| codigo         | varchar   | 3    |      | Código                       |      | x    | x    | E4_CODIGO |
| descricao      | varchar   | 50   |      | Descrição                    |      | x    |      | E4_DESCRI |
| condicao       | varchar   | 50   |      | Condição ( Dias )            |      | x    |      |           |
| forma          | char      | 2    |      | Forma de Pagamento           |      | x    |      |           |
| entrada        | char      | 1    |      | Entrada                      |      | x    |      |           |
| boleto_entrada | char      | 1    |      | Geral Boleto de Entrada (00) |      | x    |      |           |
| adiantamento   | char      | 1    |      | Adiantamento (RA)            |      | x    |      |           |
| acrescimo      | double    | 5    |      | % Acréscimo                  |      |      |      |           |
| datinc         | timestamp |      |      | Data Alteração               |      |      |      |           |
| datalt         | timestamp |      |      | Hora Alteração               |      |      |      |           |
| status         | char      | 1    |      | Status Registro              |      |      |      |           |

> condicao = 00,14,28 (Dias entre parcelas, 00 a vista)
>
> forma = 1:Dinheiro (001), 2:Cheque (002), 3:Boleto (003), 4:Devolucao (997), 5:Troca (998), 6:Bonificacao (999), 7:Consumo Interno (CI), 8:Recebimento Antecipado (RA)
>
> boleto_entrada = S:Sim, N:Não
>
> adiantamento = S:Sim, N:Não
>
> entrada = S:Sim, N:Não

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

  

#### Transportadora

Description: *Transportadoras.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SA4)
-   [ ] Rest Web

| NAME     | TYPE      | SIZE | D    | DESCRIPTION       | P    | N    | U    | NOTE       |
| -------- | --------- | ---- | ---- | ----------------- | ---- | ---- | ---- | ---------- |
| id       | integer   |      |      | ID                | x    |      |      |            |
| codigo   | varchar   | 6    |      | Código            |      | x    | x    | A4_COD     |
| ativo    | char      | 1    |      | Ativo             |      |      |      |            |
| pessoa   | char      | 1    |      | Pessoa            |      | x    |      |            |
| razao    | varchar   | 100  |      | Razão Social      |      | x    |      | A4_NOME    |
| fantasia | varchar   | 50   |      | Nome de Fantasia  |      |      |      | A4_NREDUZ  |
| end      | varchar   | 100  |      | Endereco          |      |      |      | A4_END     |
| nro      | varchar   | 10   |      | Endereço - Número |      |      |      |            |
| bairro   | varchar   | 50   |      | Bairro            |      |      |      | A4_BAIRRO  |
| compl    | varchar   | 30   |      | Complemento       |      |      |      | A4_COMPLEM |
| mun_id   | integer   |      |      | FK Municipio      |      | x    |      | A4_COD_MUN |
| uf_id    | integer   |      |      | FK UF             |      | x    |      | A4_EST     |
| pais_id  | integer   |      |      | FK Pais           |      | x    |      |            |
| cep      | varchar   | 10   |      | CEP               |      |      |      | A4_CEP     |
| cnpj_cpf | varchar   | 20   |      | CNPJ/CPF          |      |      |      | A4_CGC     |
| ie_rg    | varchar   | 20   |      | I.E./RG           |      |      |      | A4_INSEST  |
| fone     | varchar   | 15   |      | Telefone          |      |      |      | A4_TEL     |
| contato  | varchar   | 20   |      | Contato           |      |      |      | A4_CONTATO |
| rntc     | varchar   | 15   |      | RNTC              |      |      |      | A4_ANTT    |
| email    | varchar   | 100  |      | E-Mail            |      |      |      | A4_EMAIL   |
| url      | varchar   | 100  |      | Home              |      |      |      | A4_HPAGE   |
| datinc   | timestamp |      |      |                   |      |      |      |            |
| datalt   | timestamp |      |      |                   |      |      |      |            |
| status   | char      | 1    |      | Status Registro   |      |      |      |            |

>   ativo = S:Sim, N:Não
>
>   pessoa = F:Fisica, J:Juridica

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



#### fornecedor_grupo

Description: *Tabela de NCM.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SX5, Chave: Y7)
-   [ ] Report

| NAME      | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE      |
| --------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| id        | integer   |      |      | ID              | x    |      |      |           |
| codigo    | varchar   | 3    |      | Código          |      | x    | x    | X5_CHAVE  |
| descricao | varchar   | 50   |      | Descrição       |      | x    |      | X5_DESCRI |
| datinc    | timestamp |      |      | Data Alteração  |      |      |      |           |
| datalt    | timestamp |      |      | Hora Alteração  |      |      |      |           |
| status    | char      | 1    |      | Status Registro |      |      |      |           |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~







#### fornecedor

Description: *Cadastro de Fornecedores.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SA2)
-   [ ] Report

| NAME         | TYPE      | SIZE | D    | DESCRIPTION           | P    | N    | U    | NOTE           |
| ------------ | --------- | ---- | ---- | --------------------- | ---- | ---- | ---- | -------------- |
| id           | integer   |      |      |                       | x    |      |      |                |
| codigo       | varchar   | 6    |      | Código                |      | x    |      | A2_COD-A2_LOJA |
| ativo        | char      | 1    |      | Ativo                 |      | x    |      | A2_MSBLQL      |
| pessoa       | char      | 1    |      | Tipo (F,J)            |      |      |      | A2_TIPO        |
| razao        | varchar   | 100  |      | Razão Social          |      |      |      | A2_NOME        |
| fantasia     | varchar   | 50   |      | Nome de Fantasia      |      |      |      | A2_NREDUZ      |
| grp_forn_id  | integer   |      |      | FK Grupo Fornecedor   |      |      |      | A2_GRUPO       |
| end          | varchar   | 100  |      | Endereço              |      |      |      | A2_END         |
| nro          | varchar   | 10   |      | Endereço - Numero     |      |      |      | A2_NR_END      |
| compl        | varchar   | 30   |      | Complemento           |      |      |      | A2_COMPLEM     |
| bairro       | varchar   | 50   |      | Bairro                |      |      |      | A2_BAIRRO      |
| uf_id        | integer   |      |      | FK UF                 |      |      |      | A2_EST         |
| mun_id       | integer   |      |      | FK Municipio          |      |      |      | A2_COD_MUN     |
| pais_id      | integer   |      |      | Fk Pais               |      |      |      |                |
| cep          | varchar   | 10   |      | CEP                   |      |      |      | A2_CEP         |
| fone1        | varchar   | 15   |      | Telefone 1            |      |      |      | A2_TEL         |
| fone2        | varchar   | 15   |      | Telefone 2            |      |      |      | A2_FAX         |
| cnpj_cpf     | varchar   | 20   |      | CNPJ/CPF              |      |      |      | A2_CGC         |
| ie_rg        | varchar   | 20   |      | Inscrição Estadual    |      |      |      | A2_INSCR       |
| banco        | varchar   | 3    |      | Banco                 |      |      |      | A2_BANCO       |
| agencia      | varchar   | 5    |      | Agencia               |      |      |      | A2_AGENCIA     |
| dv_agencia   | char      | 1    |      | Agencia - DV          |      |      |      | A2_DVAGE       |
| conta        | varchar   | 10   |      | Conta                 |      |      |      | A2_NUMCON      |
| dv_conta     | char      | 1    |      | Conta - DV            |      |      |      | A2_DVCTA       |
| conta_tipo   | char      | 1    |      | Tipo Conta            |      |      |      | A3_TIPCTA      |
| classe_id    | integer   |      |      | FK Classe Financeira  |      |      |      | A2_NATUREZ     |
| cond_pgto_id | integer   |      |      | FK Condicao Pagamento |      |      |      | A2_COND        |
| ct_conta_id  | integer   |      |      | FK Conta Contabil     |      |      |      | A2_CONTA       |
| transp_id    | integer   |      |      | FK Transportadora     |      |      |      | A2_TRANSP      |
| dt_primeira  | data      |      |      | Data Primeira Compra  |      |      |      | A2_PRICOM      |
| dt_ultima    | data      |      |      | Data Ultima Compra    |      |      |      | A2_ULTCOM      |
| credito      | double    | 14   | 2    | Limite de Crédito     |      |      |      | A2_LC          |
| email        | varchar   | 100  |      | E-Mail                |      |      |      | A2_EMAIL       |
| url          | varchar   | 100  |      | Home Page             |      |      |      | A2_HPAGE       |
| datinc       | timestamp |      |      |                       |      |      |      |                |
| datalt       | timestamp |      |      |                       |      |      |      |                |
| status       | Char      | 1    |      | Status Registro       |      |      |      |                |

> ativo = S:Sim (2), N:Não (1)
>
> pessoa = (F:Fisica, J:Juridica)
>
> conta_tipo = 1:Conta Corrente, 2:Conta Poupança

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### fornecedor_contato

Description: *Cadastro de Fornecedores.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME    | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE     |
| ------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | -------- |
| id      | integer   |      |      | ID              | x    |      |      |          |
| forn_id | integer   |      |      | FK Fornecedor   |      | x    |      |          |
| tipo    | char      | 1    |      | Tipo            |      | x    |      |          |
| nome    | varchar   | 50   |      | Nome            |      | x    |      |          |
| cargo   | varchar   | 20   |      | Cargo           |      |      |      |          |
| fone    | varchar   | 15   |      |                 |      |      |      |          |
| email   | varchar   | 100  |      | E-Mail          |      |      |      | A2_EMAIL |
| datinc  | timestamp |      |      |                 |      |      |      |          |
| datalt  | timestamp |      |      |                 |      |      |      |          |
| status  | Char      | 1    |      | Status Registro |      |      |      |          |

> tipo = (V:Vendedor, P:Proprietario, F:Financeiro, E:Expedidor, R:Representante, O:Outro)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### tributacao (SF4 COMPLETAR)

Description: *Tipo de Entrada e Saida.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME             | T    | S    | D    | DESCRIPTION            | PK   | NN   | UN   | NOTE       |
| ---------------- | ---- | ---- | ---- | ---------------------- | ---- | ---- | ---- | ---------- |
| id               | I    |      |      | ID                     | X    |      |      |            |
| cofigo           | v    | 3    |      | Código                 |      |      |      | F4_CODIGO  |
| ativo            | c    | 1    |      | Ativo                  |      |      |      | F4_MSBLQL  |
| tipo             | c    | 1    |      | Tipo                   |      |      |      | F4_TIPO    |
| descricao        | v    | 50   |      | Descrição              |      |      |      | F4_TEXTO   |
| cfop_id          | i    |      |      | FK CFOP                |      |      |      | F4_CF      |
| gera_financeiro  | c    | 1    |      | Gera Duplicata (S,N)   |      |      |      | F4_DUPLIC  |
| atualiza_estoque | c    | 1    |      | Atualiza Estoque (S/N) |      |      |      | F4_ESTOQUE |
| poder_terceiro   | c    | 1    |      | Poder Terceiro (S/N)   |      |      |      | F4_PODER3  |
| calcula_icms     | c    | 1    |      | Calcula ICMS (S/N)     |      |      |      | F4_ICM     |
| calcula_ipi      | c    | 1    |      | Calcula IPI (S/N)      |      |      |      | F4_IPI     |
| calcula_st       | c    | 1    |      | Agrega ST (S,N,A,D)    |      |      |      | F4_INCSOL  |
| data_inclusao    | t    |      |      |                        |      |      |      |            |
| data_alteracao   | t    |      |      |                        |      |      |      |            |
| status           | c    | 1    |      | Status Registro        |      |      |      |            |

>   ativo = S:Sim (2), N:Não (1)
>
>   tipo = (E:Entrada, S:Saida )
>
>   calcula_st = (S-Sim, N-Não, A-Embutido Mercadoria, D-Deduzido Duplicata)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~





#### produto

Description: *Cadastro de Produtos.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SB1)
-   [ ] Report

| NAME         | T         | S    | D    | DESCRIPTION               | PK   | NN   | UN   | NOTE       |
| ------------ | --------- | ---- | ---- | ------------------------- | ---- | ---- | ---- | ---------- |
| id           | integer   |      |      | ID                        | x    |      |      |            |
| codigo       | varchar   | 30   |      | Código                    |      | x    | x    | B1_COD     |
| descricao    | varchar   | 100  |      | Descrição                 |      | x    |      | B1_DESC    |
| ativo        | char      | 1    |      | Ativo                     |      | x    |      | B1_MSBLQL  |
| tipo_id      | integer   |      |      | FK Tipo de Produto        |      | x    |      | B1_TIPO    |
| familia_id   | integer   |      |      | FK Familia Produto        |      | x    |      |            |
| grupo_id     | integer   |      |      | FK Grupo de Produto       |      | x    |      | B1_GRUPO   |
| un_id        | integer   |      |      | FK Unidade                |      | x    |      | B1_UM      |
| armazem_id   | integer   |      |      | FK Armazem                |      | x    |      | B1_LOCPAD  |
| conv_fator   | double    | 5    | 2    | Fator de Conversão        |      |      |      | B1_CONV    |
| conv_tipo    | char      | 1    |      | Tipo de Conversao         |      |      |      | B1_TIPCONV |
| conv_un_id   | integer   |      |      | FK Unidade Fator          |      |      |      |            |
| vlr_venda    | double    | 14   | 2    | Valor de Venda            |      |      |      | B1_PRV1    |
| vlr_custo    | double    | 14   | 2    | Valor de Custo Padrão     |      |      |      | B1_CUST    |
| dt_custo     | date      |      |      | Data de Custo Padrão      |      |      |      | B1_UCALSTD |
| custo_calc   | double    | 14   | 2    | Valor de Custo Calculado  |      |      |      |            |
| dt_calc      | date      |      |      | Data de Custo Calculado   |      |      |      |            |
| vlr_compra   | double    | 14   | 2    | Ultimo Preço de Compra    |      |      |      | B1_UPRC    |
| dt_compra    | date      |      |      | Ultima Data de Compa      |      |      |      | B1_UCOM    |
| peso_liquido | double    | 10   | 4    | Peso Liquido              |      |      |      | B1_PESO    |
| peso_bruto   | double    | 10   | 4    | Peso Bruto                |      |      |      | B1_PESBRU  |
| comissao     | double    | 5    | 2    | % Comissão do Produto     |      |      |      | B1_COMIS   |
| barras       | varchar   | 30   |      | Código de Barra           |      |      |      | B1_CODBAR  |
| icms         | double    | 5    | 2    | % Aliquota de ICMS        |      |      |      | B1_PICM    |
| ipi          | double    | 5    | 2    | % Aliquota de IPI         |      |      |      | B1_IPI     |
| iss          | double    | 5    | 2    | % Aliquota de ISSQN       |      |      |      | B1_ALIQISS |
| mva_st       | double    | 5    | 2    | % Base Vlr. Agregado (ST) |      |      |      | B1_PICMRET |
| ncm_id       | Integer   |      |      | FK NCM                    |      | x    |      | B1_POSIPI  |
| origem_id    | Integer   |      |      | FK Origem                 |      | x    |      | B1_ORIGEM  |
| qtd_emb      | integer   | 6    |      | Qtd. Embalagem            |      |      |      | B1_QE      |
| est_minimo   | double    | 12   | 4    | Qtd. Estoque Minimo       |      |      |      | B1_EMIN    |
| est_maximo   | double    | 12   | 4    | Qtd. Estoque Maximo       |      |      |      | B1_MAX     |
| foto         | text      |      |      | Caminho da Foto           |      |      |      | B1_BITMAP  |
| obs          | text      |      |      | Observação                |      |      |      | B1_OBS     |
| ct_conta_id  | integer   |      |      | FK Conta Contabil         |      |      |      | B1_CONTA   |
| cc_id        | integer   |      |      | FK Centro de Custo        |      |      |      | B1_CC      |
| datinc       | timestamp |      |      | Data Alteração            |      |      |      |            |
| datalt       | timestamp |      |      | Hora Alteração            |      |      |      |            |
| status       | char      | 1    |      | Status Registro           |      |      |      |            |

>   ativo = S:Sim (2), N:Não (1)
>
>   conv_tipo = ( M=Multiplicação, D=Divisão )

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### produto_fornecedor

Description: *Movimento de Estoque de  Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME       | TYPE      | SIZE | D    | DESCRIPTION       | P    | N    | U    | NOTE |
| ---------- | --------- | ---- | ---- | ----------------- | ---- | ---- | ---- | ---- |
| id         | integer   |      |      | ID                | x    |      |      |      |
| produto_id | integer   |      |      | FK Produto        |      | x    |      |      |
| forn_id    | integer   |      |      | FK Fornecedor     |      | x    | x    |      |
| codigo     | varchar   | 30   |      | Código do Produto |      |      |      |      |
| dias       | integer   | 3    |      | Dias para Entrega |      |      |      |      |
| datinc     | timestamp |      |      | Data Alteração    |      |      |      |      |
| datalt     | timestamp |      |      | Hora Alteração    |      |      |      |      |
| status     | char      | 1    |      | Status Registro   |      |      |      |      |

> 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### produto_alternativo

Description: *Movimento de Estoque de  Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME        | TYPE      | SIZE | D    | DESCRIPTION            | P    | N    | U    | NOTE |
| ----------- | --------- | ---- | ---- | ---------------------- | ---- | ---- | ---- | ---- |
| id          | integer   |      |      | ID                     | x    |      |      |      |
| produto_id  | integer   |      |      | FK Produto             |      | x    |      |      |
| prod_alt_id | integer   |      |      | FK Produto Alternativo |      | x    |      |      |
| datinc      | timestamp |      |      | Data Alteração         |      |      |      |      |
| datalt      | timestamp |      |      | Hora Alteração         |      |      |      |      |
| status      | char      | 1    |      | Status Registro        |      |      |      |      |

> 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~







#### estoque_saldo

Description: *Saldo de Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SB2)
-   [ ] Rest Web

| NAME         | TYPE      | SIZE | D    | DESCRIPTION                         | P    | N    | U    | NOTE       |
| ------------ | --------- | ---- | ---- | ----------------------------------- | ---- | ---- | ---- | ---------- |
| id           | integer   |      |      | ID                                  | x    |      |      |            |
| produto_id   | integer   |      |      | FK Produto                          |      | x    | x    | B2_COD     |
| qtd          | double    | 14   | 2    | Quantidade                          |      |      |      | B2_QATU    |
| qtd_pedidos  | double    | 14   | 2    | Qtd - Pedidos de Venda              |      |      |      | B2_QPEDVEN |
| qtd_empenho  | double    | 14   | 2    | Qtd - Empenho Producao              |      |      |      | B2_QEMP    |
| qtd_prevista | double    | 14   | 2    | Qtd - Prevista (Compra ou Producao) |      |      |      | B2_SALPEDI |
| armazem_id   | integer   |      |      | GK Armazem                          |      | x    |      | B2_LOCAL   |
| datinc       | timestamp |      |      | Data Alteração                      |      |      |      |            |
| datalt       | timestamp |      |      | Hora Alteração                      |      |      |      |            |
| status       | char      | 1    |      | Status Registro                     |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### estoque_movimento

Description: *Movimento de Estoque de  Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SD3)
-   [ ] Rest Web

| NAME        | TYPE      | SIZE | D    | DESCRIPTION        | P    | N    | U    | NOTE       |
| ----------- | --------- | ---- | ---- | ------------------ | ---- | ---- | ---- | ---------- |
| id          | integer   |      |      | ID                 | X    |      |      |            |
| emissao     | data      |      |      | Data de Emissão    |      | x    |      | D3_EMISSAO |
| tipo        | char      | 1    |      | Tipo Movimento     |      | x    |      | D3_TM      |
| op          | varchar   | 20   |      | Ordem de Produção  |      |      |      | D3_OP      |
| op_enc      | char      | 1    |      | Encerramento da OP |      |      |      | D3_PARCTOT |
| produto_id  | integer   |      |      | FK Produto         |      | x    |      | D3_COD     |
| qtd         | double    | 12   | 2    | Quantidade         |      | x    |      | D3_QUANT   |
| doc         | varchar   | 10   |      | Documento          |      |      |      | D3_DOC     |
| custo_tt    | double    | 14   | 2    | Total de Custo     |      |      |      | D3_CUSTO1  |
| ct_conta_id | integer   |      |      | FK Conta Contabil  |      |      |      | D3_CONTA   |
| cc_id       | integer   |      |      | FK Centro de Custo |      |      |      | D3_CC      |
| datinc      | timestamp |      |      | Data Alteração     |      |      |      |            |
| datalt      | timestamp |      |      | Hora Alteração     |      |      |      |            |
| status      | char      | 1    |      | Status Registro    |      |      |      |            |

> tipo = E:Entrada, S:Saida, P:Produção, T:Transferencia
>
> op_enc = P:Parcial, T:Total

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### estoque_transferencia

Description: *Transferencia de Estoque de  Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SD3)
-   [ ] Rest Web

| NAME           | TYPE      | SIZE | D    | DESCRIPTION        | PK   | NN   | UN   | NOTE |
| -------------- | --------- | ---- | ---- | ------------------ | ---- | ---- | ---- | ---- |
| id             | integer   |      |      | ID                 | X    |      |      |      |
| emissao        | date      |      |      | Data de Emissão    |      |      |      |      |
| pro_id_origem  | integer   |      |      | FK Produto         |      |      |      |      |
| arm_id_origem  | integer   |      |      | FK Armazem         |      |      |      |      |
| pro_id_destino | integer   |      |      | FK Produto         |      |      |      |      |
| arm_id_destino | integer   |      |      | FK Armazem         |      |      |      |      |
| qtd            | double    | 12   | 2    | Quantidade         |      |      |      |      |
| doc            | varchar   | 10   |      | Documento          |      |      |      |      |
| custo_tt       | double    | 14   | 2    | Total de Custo     |      |      |      |      |
| ct_conta_id    | integer   |      |      | FK Conta Contabil  |      |      |      |      |
| cc_id          | integer   |      |      | FK Centro de Custo |      |      |      |      |
| datinc         | timestamp |      |      | Data Alteração     |      |      |      |      |
| datalt         | timestamp |      |      | Hora Alteração     |      |      |      |      |
| status         | char      | 1    |      | Status Registro    |      |      |      |      |

> 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### estoque_desmontagem

Description: *Desmontagem de Estoque de  Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SD3)
-   [ ] Rest Web

| NAME          | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE |
| ------------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id            | integer   |      |      | ID              | X    |      |      |      |
| emissao       | date      |      |      | Data de Emissão |      | x    |      |      |
| pro_id_origem | integer   |      |      | FK Produto      |      | x    |      |      |
| arm_id_origem | integer   |      |      | FK Armazem      |      | x    |      |      |
| qtd           | double    | 12   | 2    | Quantidade      |      | x    |      |      |
| doc           | varchar   | 10   |      | Documento       |      |      |      |      |
| datinc        | timestamp |      |      | Data Alteração  |      |      |      |      |
| datalt        | timestamp |      |      | Hora Alteração  |      |      |      |      |
| status        | Char      | 1    |      | Status Registro |      |      |      |      |

> 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



#### estoque_desmontagem_item

Description: *Desmontagem de Estoque de  Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP (Tabela: SD3)
-   [ ] Rest Web

| NAME        | TYPE      | SIZE | D    | DESCRIPTION        | P    | N    | U    | NOTE |
| ----------- | --------- | ---- | ---- | ------------------ | ---- | ---- | ---- | ---- |
| id          | integer   |      |      | ID                 | x    |      |      |      |
| est_desm_id | integer   |      |      | Desmontagem        |      | x    |      |      |
| pro_id      | integer   |      |      | FK Produto         |      | x    |      |      |
| arm_id      | integer   |      |      | FK Armazem         |      | x    |      |      |
| qtd         | double    | 12   | 2    | Quantidade         |      | x    |      |      |
| ct_conta_id | integer   |      |      | FK Conta Contabil  |      |      |      |      |
| cc_id       | integer   |      |      | FK Centro de Custo |      |      |      |      |
| datinc      | timestamp |      |      | Data Alteração     |      |      |      |      |
| datalt      | timestamp |      |      | Hora Alteração     |      |      |      |      |
| status      | char      | 1    |      | Status Registro    |      |      |      |      |

> 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~











#### tabela_preco

Description: *Tabela de Preços.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: DA0)
-   [ ] Report

| NAME         | TYPE      | SIZE | D    | DESCRIPTION                     | P    | N    | U    | NOTE       |
| ------------ | --------- | ---- | ---- | ------------------------------- | ---- | ---- | ---- | ---------- |
| id           | integer   |      |      | ID                              | x    |      |      |            |
| codigo       | varchar   | 3    |      | Código                          |      | x    |      | DA0_CODTAB |
| descricao    | varchar   | 50   |      | Descrição                       |      | x    |      | DA0_DESCRI |
| ativa        | char      | 1    |      | Ativa                           |      | x    |      | DA0_ATIVO  |
| dt_inicial   | date      |      |      | Data de Validade Inicial        |      |      |      | DA0_DATDE  |
| hr_inicial   | time      |      |      | Hora de Validade Inicial        |      |      |      |            |
| dt_final     | date      |      |      | Data de Validade Final          |      |      |      | DA0_DATATE |
| hr_final     | time      |      |      | Hora de Validade Final          |      |      |      |            |
| cond_pgto_id | integer   |      |      | FK Condição de Pagamento Padrao |      |      |      | DA0_CONDPG |
| datinc       | timestamp |      |      |                                 |      |      |      |            |
| datalt       | timestamp |      |      |                                 |      |      |      |            |
| status       | char      | 1    |      | Status                          |      |      |      |            |

> ativa = S:Sim (1), N:Não (2)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### tabela_preco_item

Description: *Itens da Tabela de Preços.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: DA1)
-   [ ] Report

| NAME         | TYPE      | SIZE | D    | DESCRIPTION           | P    | N    | U    | NOTE       |
| ------------ | --------- | ---- | ---- | --------------------- | ---- | ---- | ---- | ---------- |
| id           | integer   |      |      | ID                    | x    |      |      |            |
| tab_preco_id | integer   |      |      | FK Tabela de Preço    |      | x    |      |            |
| produto_id   | integer   |      |      | FK Produto            |      | x    |      | DA1_CODPRO |
| vlr_venda    | double    | 14   | 2    | Preço de Venda        |      | x    |      | DA1_PRCVEN |
| vlr_desconto | double    | 14   | 2    | Valor de Desconto     |      |      |      | DA1_VLRDES |
| ativo        | char      | 1    |      | Ativo                 |      | x    |      | DA1_ATIVO  |
| vlr_maximo   | double    | 14   | 2    | Preço de Venda Máximo |      |      |      | DA1_PRCMAX |
| datinc       | timestamp |      |      |                       |      |      |      |            |
| datalt       | timestamp |      |      |                       |      |      |      |            |
| status       | char      | 01   |      | Status                |      |      |      |            |

> ativo = S:Sim (1), N:Não (2)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### cliente_grupo

Description: *Tabela de Segmentos.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: AOV)
-   [ ] Report

| NAME           | TYPE      | SIZE | D    | DESCRIPTION | P    | N    | U    | NOTE       |
| -------------- | --------- | ---- | ---- | ----------- | ---- | ---- | ---- | ---------- |
| id             | integer   |      |      | ID          | x    |      |      |            |
| codigo         | varchar   | 3    |      | Código      |      | x    |      | AOV_CODSEG |
| descricao      | varchar   | 50   |      | Descrição   |      | x    |      | AOV_DESSEG |
| ativo          | char      | 1    |      | Ativo       |      |      |      | AOV_MSBLQL |
| data_inclusao  | timestamp |      |      |             |      |      |      |            |
| data_alteracao | timestamp |      |      |             |      |      |      |            |
| status         | char      | 1    |      | Status      |      |      |      |            |

> ativo = S:Sim (2), N:Não (1)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



#### cliente

Description: *Cadastro de Clientes.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP (Tabela: SA1)
-   [ ] Report

| NAME           | TYPE      | SIZE | D    | DESCRIPTION                       | P    | N    | U    | NOTE                |
| -------------- | --------- | ---- | ---- | --------------------------------- | ---- | ---- | ---- | ------------------- |
| id             | uuid      |      |      | ID                                | x    |      |      |                     |
| codigo         | varchar   | 6    |      | Código                            |      | x    |      | A1_COD-A1_LOJA      |
| ativo          | char      | 1    |      | Ativo                             |      | x    |      | A1_MSBLQL           |
| pessoa         | char      | 1    |      | Tipo Pessoa (F=Fisica/J=Juridica) |      | x    |      | A1_PESSOA           |
| razao          | varchar   | 100  |      | Razão Social                      |      | x    |      | A1_NOME             |
| fantasia       | varchar   | 50   |      | Nome de Fantasia                  |      |      |      | A1_NREDUZ           |
| end            | varchar   | 100  |      | Endereço                          |      |      |      | A1_END              |
| nro            | varchar   | 10   |      | Endereço - Numero                 |      |      |      |                     |
| compl          | varchar   | 30   |      | Complemento                       |      |      |      | A1_COMPLEM          |
| uf_id          | integer   |      |      | FK UF                             |      |      |      | A1_EST              |
| mun_id         | integer   |      |      | FK Municipio                      |      |      |      | A1_COD_MUN          |
| bairro         | varchar   | 30   |      | Bairro                            |      |      |      | A1_BAIRRO           |
| cep            | varchar   | 10   |      | CEP                               |      |      |      | A1_CEP              |
| fone1          | varchar   | 15   |      | Telefone 1                        |      |      |      | A1_TEL              |
| fone2          | varchar   | 15   |      | Telefone 2                        |      |      |      | A1_FAX              |
| cnpj_cpf       | varchar   | 20   |      | CNPJ/CPF                          |      |      |      | A1_CGC              |
| ie_rg          | varchar   | 20   |      | Inscrição Estadual                |      |      |      | A1_INSCR/A1_PFISICA |
| nascimento     | date      |      |      | Data Nascimento                   |      |      |      | A1_DTNASC           |
| url            | varchar   | 100  |      | Home Page                         |      |      |      | A1_HPAGE            |
| grp_cliente_id | integer   |      |      | FK Segmento                       |      |      |      | A1_CODSEG           |
| vendedor_id    | integer   |      |      | FK Vendedor                       |      |      |      | A1_VEND             |
| comissao       | double    | 05   | 2    | % Comissão                        |      |      |      | A1_COMISS           |
| frete          | char      | 01   |      | Tipo Frete (C-CIF, F=FOB)         |      |      |      | A1_TPFRET           |
| desconto       | double    | 05   | 2    | % Desconto Sugerido               |      |      |      | A1_DESC             |
| cond_pgto_id   | integer   |      |      | FK Condição de Pagamento          |      |      |      | A1_COND             |
| tab_preco_id   | integer   |      |      | FK Tabela de Preço                |      |      |      | A1_TABELA           |
| reg_venda_id   | integer   |      |      | FK Região                         |      |      |      | A1_REGIAO           |
| vlr_limite     | double    | 14   | 2    | Limite de Credito                 |      |      |      | A1_LC               |
| vcto_limite    | date      |      |      | Vencimento Limite de Credito      |      |      |      | A1_VENCLC           |
| risco          | char      | 1    |      | Risco                             |      |      |      | A1_RISCO            |
| dt_pri_compra  | date      |      |      | Primeira Compra                   |      |      |      | A1_PRICOM           |
| dt_ult_visita  | date      |      |      | Ultima Visita                     |      |      |      | A1_ULTVIS           |
| dt_cadastro    | date      |      |      | Data do Cadastro                  |      |      |      | A1_DTCAD            |
| ct_conta_id    | integer   |      |      | FK Conta Contabil                 |      |      |      | A1_CONTA            |
| obs            | text      |      |      | Observação                        |      |      |      | A1_OBSERV           |
| transp_id      | integer   |      |      | FK Transportador                  |      |      |      | A1_TRANSP           |
| cob_cep        | varchar   | 10   |      | Cobranca - CEP                    |      |      |      |                     |
| cob_end        | varchar   | 100  |      | Cobranca - Endereco               |      |      |      | A1_ENDCOB           |
| cob_nro        | varchar   | 10   |      | Cobranca - Endereco - Nro         |      |      |      |                     |
| cob_compl      | varchar   | 30   |      | Cobranca - Complemento            |      |      |      |                     |
| cob_bairro     | varchar   | 30   |      | Cobranca - Bairro                 |      |      |      | A1_BAIRROC          |
| cob_uf_id      | integer   |      |      | Cobranca - UF                     |      |      |      |                     |
| cob_mun_id     | integer   |      |      | Cobranca - Municipio              |      |      |      |                     |
| cob_pais_id    | integer   |      |      | Cobranca - Pais                   |      |      |      |                     |
| latitude       | double    | 10   | 8    | Latitude                          |      |      |      |                     |
| longitude      | double    | 11   | 8    | Longitude                         |      |      |      |                     |
| datincl        | timestamp |      |      |                                   |      |      |      |                     |
| datalt         | timestamp |      |      |                                   |      |      |      |                     |
| status         | char      | 1    |      | Status Registro                   |      |      |      |                     |

> ativo = S:Sim (2), N:Não (1)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### cliente_contato

Description: *Cadastro de Fornecedores.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME       | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE       |
| ---------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id         | integer   |      |      | ID              | x    |      |      |            |
| cliente_id | integer   |      |      | FK Fornecedor   |      | x    |      |            |
| tipo       | char      | 1    |      | Tipo            |      | x    |      |            |
| nome       | varchar   | 50   |      | Nome            |      | x    |      | A1_CONTATO |
| cargo      | varchar   | 20   |      | Cargo           |      |      |      |            |
| fone       | varchar   | 15   |      |                 |      |      |      |            |
| email      | varchar   | 100  |      | E-Mail          |      |      |      | A1_EMAIL   |
| datinc     | timestamp |      |      |                 |      |      |      |            |
| datalt     | timestamp |      |      |                 |      |      |      |            |
| status     | Char      | 1    |      | Status Registro |      |      |      |            |

> tipo = (C:Comprador, P:Proprietario, F:Financeiro, A:Almoxarife  O:Outro)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### cliente_entrega

Description: *Cadastro de Fornecedores.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME       | TYPE      | SIZE | D    | DESCRIPTION     | P    | N    | U    | NOTE |
| ---------- | --------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id         | integer   |      |      | ID              | x    |      |      |      |
| cliente_id | integer   |      |      | FK Fornecedor   |      | x    |      |      |
| cep        | varchar   | 10   |      | CEP             |      | x    |      |      |
| end        | varchar   | 100  |      | Endereco        |      | x    |      |      |
| nro        | varchar   | 10   |      | Número          |      | x    |      |      |
| compl      | varchar   | 30   |      | Complemento     |      |      |      |      |
| bairro     | varchar   | 50   |      | Bairro          |      |      |      |      |
| uf_id      | integer   |      |      | FK UF           |      |      |      |      |
| mun_id     | integer   |      |      | FK Municipio    |      |      |      |      |
| datinc     | timestamp |      |      |                 |      |      |      |      |
| datalt     | timestamp |      |      |                 |      |      |      |      |
| status     | Char      | 1    |      | Status Registro |      |      |      |      |

> tipo = (C:Comprador, P:Proprietario, F:Financeiro, A:Almoxarife  O:Outro)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~





#### ativo_grupo

Description: *Grupo de Ativo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: SNG)
- [ ] Rest Web (Rota: grupoativo)

| NAME       | TYPE     | SIZE | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE    |
| ---------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | ------- |
| id         | integer  |      |      | ID              | X    |      |      |         |
| empresa_id | integer  |      |      | FK Empresa      |      |      |      |         |
| codigo_erp | varchar  | 10   |      | Chave           |      |      |      | NG_COD  |
| descricao  | varchar  | 100  |      | Descrição       |      | X    |      | NG_DESC |
| dt_inc     | datetime |      |      | Inclusão        |      |      |      |         |
| dt_alt     | datetime |      |      | Alteração       |      |      |      |         |
| status     | char     | 1    |      | Status Registro |      |      |      |         |

```sql
<chave> AS id, <DePara> AS empresa_id, BG_ATIVO AS codigo_erp, BG_DESC AS descricao, dt_inc, dt_alt, status
```



#### ativo

Description: *Ativo Fixo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: SN1)
- [ ] Rest Web (Rota: ativo)

| NAME           | TYPE     | SIZE | D    | DESCRIPTION            | PK   | NN   | UN   | NOTE       |
| -------------- | -------- | ---- | ---- | ---------------------- | ---- | ---- | ---- | ---------- |
| id             | integer  |      |      | ID                     | X    |      |      |            |
| empresa_id     | integer  |      |      | FK Empresa             |      |      |      |            |
| codigo_erp     | varchar  | 10   |      | Chave                  |      |      |      | N1_CBASE   |
| ativo_grupo_id | integer  |      |      | Grupo de Ativo         |      |      |      | N1_GRUPO   |
| descricao      | varchar  | 100  |      | Descricao              |      | X    |      | N1_DESCRIC |
| plaqueta       | varchar  | 20   |      | Plaqueta               |      |      |      | N1_CHAPA   |
| codigo_barras  | varchar  | 30   |      | Cödigo de Barras       |      |      |      | N1_CODBAR  |
| produto_id     | integer  |      |      | FK Produto             |      |      |      | N1_PRODUTO |
| classificacao  | char     | 1    |      | Classificacao          |      |      |      | N1_PATRIM  |
| status_ativo   | char     | 1    |      | Status do Ativo        |      |      |      | N1_STATUS  |
| dt_compra      | date     |      |      | Data de Aquisição      |      |      |      | N1_AQUISIC |
| cliente_id     | integer  |      |      | FK Cliente             |      |      |      |            |
| fornecedor_id  | integer  |      |      | FK Fornecedor          |      |      |      | N1_FORNEC  |
| documento      | varchar  | 15   |      | Nota Fiscal            |      |      |      | N1_NFISCAL |
| vlr_compra     | double   | 14   | 2    | Valor de Compra        |      |      |      | N1_VLAQUIS |
| dt_garantia    | date     |      |      | Data Final da Garantia |      |      |      | N1_DTVENC  |
| dt_baixa       | date     |      |      | Data da Baixa          |      |      |      | N1_BAIXA   |
| motivo_baixa   | char     | 1    |      | Motivo da Baixa        |      |      |      |            |
| vlr_baixa      | double   | 14   | 2    | Valor da Baixa         |      |      |      |            |
| foto           | text     |      |      | Foto                   |      |      |      |            |
| observacao     | text     |      |      | Observação             |      |      |      |            |
| dt_inc         | datetime |      |      | Inclusão               |      |      |      |            |
| dt_alt         | datetime |      |      | Alteração              |      |      |      |            |
| status         | char     | 1    |      | Status                 |      |      |      |            |

> status_ativo =  A:Ativo, C:Comodatado, M:Manutenção, B:Bloqueado, D:Desativado  
>
> classificacao =  I:Imovel, V:Veiculo, M:Maquina/Equipamento
>
> motivo_baixa = V:Venda, D:Descarte, E:Extravio

```sql
<chave> AS id, <DePara> AS empresa_id, N1_CBASE AS codigo_erp
```





#### motorista

Description: *Cadastro de Motoristas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: DA4)
- [ ] Rest Web (Rota: motorista)

| NAME          | TYPE     | SIZE | D    | DESCRIPTION      | PK   | NN   | UN   | NOTE       |
| ------------- | -------- | ---- | ---- | ---------------- | ---- | ---- | ---- | ---------- |
| id            | integer  |      |      | ID               | X    |      |      |            |
| empresa_id    | integer  |      |      | FK Empresa       |      |      |      | DA4_FILIAL |
| codigo_erp    | varchar  | 6    |      | Motorista        |      |      |      | DA4_COD    |
| tipo          | char     | 1    |      | Tipo             |      |      |      | DA4_TIPMOT |
| ativo         | char     | 1    |      | Ativo            |      |      |      | DA4_BLQMOT |
| nome          | varchar  | 100  |      | Nome             |      | X    |      | DA4_NOME   |
| nome_reduzido | varchar  | 50   |      | Nome Reduzido    |      |      |      | DA4_NREDUZ |
| endereco      | varchar  | 100  |      | Endereço         |      |      |      | DA4_END    |
| complemento   | varchar  | 50   |      | Complemento      |      |      |      |            |
| bairro        | varchar  | 50   |      | Bairro           |      |      |      | DA4_BAIRRO |
| uf_id         | integer  |      |      | UF               |      |      |      | DA4_EST    |
| municipio_id  | integer  |      |      | Municipio        |      |      |      | DA4_CODMUN |
| cep           | varchar  | 10   |      | CEP              |      |      |      | DA4_CEP    |
| telefone      | varchar  | 15   |      | Telefone         |      |      |      | DA4_TEL    |
| cpf           | varchar  | 20   |      | CPF              |      |      |      | DA4_CGC    |
| dt_admissao   | date     |      |      | Data de Admissao |      |      |      |            |
| dt_demissao   | date     |      |      | Data de Demissao |      |      |      |            |
| cnh           | varchar  | 20   |      | CNH              |      |      |      | DA4_NUMCHN |
| foto          | text     |      |      | Caminho da Foto  |      |      |      |            |
| observacao    | text     |      |      | Obsevação        |      |      |      |            |
| dt_inc        | datetime |      |      | Inclusão         |      |      |      |            |
| dt_alt        | datetime |      |      | Alteração        |      |      |      |            |
| status        | char     | 1    |      | Status Registro  |      |      |      |            |


> ativo = S:Sim, N:Não (Protheus Bloqueado 1=Sim, 2=Não)
>
> tipo = P:Próprio, T:Terceiro, A:Agregado (Protheus 1=Proprio, 2=Terceiro, 4=Agregado )

```sql
<chave> AS id, <DePara> AS empresa_id, DA4_COD AS codigo_erp, DA4_TIPMOT AS tipo, DA4_BLQMOT AS ativo, DA4_NOME AS nome, DA4_NREDUZ AS nome_reduzido, DA4_END AS endereco, <complement> AS complemento, DA4_BAIRRO AS bairro, DA4_EST AS <uf_id>, DA4_CODMUN AS <municipio_id>, DA4_CEP AS cep, DA4_TEL AS telefone, DA4_CGC AS cpf, DA4_NUMCHN AS cnh, foto, observacao, dt_inc, dt_alt, status
```





#### veiculo_tipo

Description: *Tabela de TIpo de Carroceria de Veículo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: DUT)
- [ ] Rest Web (Rota: tipoveiculo)

| NAME       | TYPE     | SIZE | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE       |
| ---------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id         | integer  |      |      | ID              | X    |      |      |            |
| empresa_id | integer  |      |      | FK Empresa      |      |      |      |            |
| codigo_erp | char     | 10   |      | Código          |      |      |      | DUT_TIPVEI |
| descricao  | varchar  | 50   |      | Descrição       |      | X    |      | DUT_DESCRI |
| dt_inc     | datetime |      |      | Inclusão        |      |      |      |            |
| dt_alt     | datetime |      |      | Alteração       |      |      |      |            |
| status     | char     | 1    |      | Status Registro |      |      |      |            |

> 

```sql
<chave> AS id, <DePara> AS empresa_id, DUT_TIPVEI AS codigo_erp, DUT_DESCRI AS descricao, dt_inc, dt_alt, status
```





#### veiculo_marca

Description: *Tabelas Genéricas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: SX5 -> Chave: M6)
- [ ] Rest Web (Rota: marcaveiculo)

| NAME       | TYPE     | SIZE | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| ---------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| id         | integer  |      |      | ID              | X    |      |      |           |
| empresa_id | integer  |      |      | FK Empresa      |      |      |      |           |
| codigo_erp | varchar  | 10   |      | Chave           |      |      |      | X5_CHAVE  |
| descricao  | varchar  | 100  |      | Descrição       |      | X    |      | X5_DESCRI |
| dt_inc     | datetime |      |      | Inclusão        |      |      |      |           |
| dt_alt     | datetime |      |      | Alteração       |      |      |      |           |
| status     | char     | 1    |      | Status Registro |      |      |      |           |

```sql
<chave> AS id, <DePara> AS empresa_id, X5_CHAVE AS codigo_erp, X5_DESCRI AS descricao, dt_inc, dt_alt, status WHERE X5_TABELA = 'M6'
```

 

#### veiculo_cor (SX5_M7)

Description: *Tabelas Genéricas.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| id             | i    |      |      | ID              | X    |      |      |           |
| codigo         | v    | 3    |      | Chave           |      | X    |      | X5_CHAVE  |
| descricao      | v    | 100  |      | Descrição       |      | X    |      | X5_DESCRI |
| data_inclusao  | t    |      |      |                 |      |      |      |           |
| data_alteracao | t    |      |      |                 |      |      |      |           |
| status         | c    | 1    |      | Status Registro |      |      |      |           |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### veiculo

Description: *Cadastro de Veículos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: DA3)
- [ ] Rest Web (Rota: veiculo)

| NAME             | TYPE     | SIZE | D    | DESCRIPTION           | PK   | NN   | UN   | NOTE       |
| ---------------- | -------- | ---- | ---- | --------------------- | ---- | ---- | ---- | ---------- |
| id               | integer  |      |      | ID                    | X    |      |      |            |
| empresa_id       | integer  |      |      | FK Empresa            |      |      |      |            |
| codigo_erp       | varchar  | 10   |      | Veiculo               |      |      |      | DA3_COD    |
| ativo            | char     | 1    |      | Ativo                 |      |      |      | DA3_ATIVO  |
| descricao        | varchar  | 100  |      | Descrição             |      | X    |      | DA3_DESC   |
| veiculo_marca_id | integer  |      |      | FK Marca              |      |      |      | DA3_MARVEI |
| ano_fabricacao   | integer  | 4    |      | Ano de Fabricação     |      |      |      | DA3_ANOFAB |
| ano_modelo       | integer  | 4    |      | Ano de Modelo         |      |      |      | DA3_ANOMOD |
| placa            | varchar  | 10   |      | Numero de Placa       |      |      |      | DA3_PLACA  |
| uf_id            | integer  |      |      | FK UF da Placa        |      |      |      | DA3_ESTPLA |
| municipio_id     | integer  |      |      | FK Municipio da Placa |      |      |      | DA3_MUNPLA |
| chassis          | varchar  | 20   |      | Numero Chassi         |      |      |      | DA3_CHASSI |
| renavam          | varchar  | 11   |      | Código Renavam        |      |      |      | DA3_RENAVA |
| capacidade       | double   | 9    | 2    | Capacidade Nominativa |      |      |      | DA3_CAPACN |
| volume           | double   | 6    | 2    | Volume Maximo M3      |      |      |      | DA3_VOLMAX |
| tara             | double   | 9    | 2    | Tara                  |      |      |      | DA3_TARA   |
| motorista_id     | integer  |      |      | FK Motorista          |      |      |      | DA3_MOTORI |
| veiculo_tipo_id  | integer  |      |      | FK Tipo Veiculo       |      |      |      | DA3_TIPVEI |
| ativo_id         | integer  |      |      | FK Ativo              |      |      |      |            |
| frota            | char     | 1    |      | Frota                 |      |      |      | DA3_FROVEI |
| dt_inicio_seguro | date     |      |      | Data Inicio do Seguro |      |      |      | DA3_DTIVSG |
| dt_final_seguro  | date     |      |      | Data Final do Seguro  |      |      |      | DA3_DTFVSG |
| foto             | text     |      |      | Caminho da Foto       |      |      |      | DA3_BITMAP |
| observacao       | text     |      |      | Observação            |      |      |      |            |
| dt_inc           | datetime |      |      | Inclusão              |      |      |      |            |
| dt_alt           | datetime |      |      | Alteração             |      |      |      |            |
| status           | char     | 1    |      | Status Registro       |      |      |      |            |


> ativo = S:Sim, N:Não ( Protheus Ativo 1=Sim, 2=Não)
>
> frota = P:Própria, T:Terceiro, A:Agregado (Protheus 1=Propria, 2=Terceiro, 3=Agregado )

```sql
<chave> AS id, <DePara> AS empresa_id, DA3_COD AS codigo_erp, DA3_ATIVO AS ativo, DA3_DESC AS descricao, DA3_MARVEI AS <veiculo_marca_id>, DA3_ANOFAB AS ano_fabricao, DA3_ANOMOD AS ano_modelo, DA3_PLACA AS placa, DA3_ESTPLA AS <uf_id>, DA3_MUNPLA AS municipio, DA3_CHASSI AS chassis, DA3_RENAVA AS renavam, DA3_CAPACIN AS capacidade, DA3_VOLMAX AS volume, DA3_TARA AS tara, DA3_MOTORI AS <motorista_id>, DA3_TIPVE AS <veiculo_tipo_id>, DA3_FROVEI AS frota, DA3_DTIVSG AS inicio_seguro, DA3_DTFVSG AS final_seguro, DA3_BITMAP AS foto, observacao, dt_inc, dt_alt, status
```







#### ativo_peca

Description: *Peça de Ativo.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: )
- [ ] Rest Web (Rota:  )

| NAME           | TYPE     | SIZE | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE |
| -------------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             |          |      |      | ID              | X    |      |      |      |
| empresa_id     | integer  |      |      | FK Empresa      |      | X    |      |      |
| codigo_erp     | varchar  | 10   |      | Código ERP      |      | X    |      |      |
| descricao      | varchar  | 50   |      | Descrição       |      | X    |      |      |
| saldo          | double   | 10   | 4    | Saldo Atual     |      |      |      |      |
| dt_entrada     | date     |      |      | Data Entrada    |      |      |      |      |
| vlr_entrada_un | double   | 14   | 2    | Vlr. Entrada UN |      |      |      |      |
| obs            | text     |      |      | Observação      |      |      |      |      |
| foto           | text     |      |      | Foto            |      |      |      |      |
| dt_inc         | datetime |      |      | Inclusão        |      |      |      |      |
| dt_alt         | datetime |      |      | Alteração       |      |      |      |      |
| status         | char     | 1    |      | Status          |      |      |      |      |

```sql

```



#### ativo_peca_aplicacao

Description: *Aplicação de Peças.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: )
- [ ] Rest Web (Rota:  )

| NAME       | TYPE     | SIZE | D    | DESCRIPTION   | PK   | NN   | UN   | NOTE |
| ---------- | -------- | ---- | ---- | ------------- | ---- | ---- | ---- | ---- |
| id         |          |      |      | ID            | X    |      |      |      |
| ativo_peca | integer  |      |      | FK Ativo Peca |      | X    |      |      |
| ativo_id   | integer  |      |      | FK Ativo      |      | X    |      |      |
| obs        | text     |      |      | Observação    |      |      |      |      |
| dt_inc     | datetime |      |      | Inclusão      |      |      |      |      |
| dt_alt     | datetime |      |      | Alteração     |      |      |      |      |
| status     | char     | 1    |      | Status        |      |      |      |      |

```sql

```





#### ativo_peca_movimento

Description: *Movimento de Peça.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: SED)
- [ ] Rest Web (Rota: classefinanceira )

| NAME          | TYPE     | SIZE | D    | DESCRIPTION         | PK   | NN   | UN   | NOTE |
| ------------- | -------- | ---- | ---- | ------------------- | ---- | ---- | ---- | ---- |
| id            |          |      |      | ID                  | X    |      |      |      |
| empresa_id    | integer  |      |      | FK Empresa          |      | X    |      |      |
| ativo_peca_id | integer  |      |      | FK Ativo Peca       |      | X    |      |      |
| dt_mvto       | date     |      |      | Data Movimento      |      | X    |      |      |
| qtd           | double   | 10   | 2    | Qtd Movimento       |      | X    |      |      |
| vlr_un        | double   | 14   | 2    | Vlr. Unitario       |      | X    |      |      |
| tipo          | char     | 1    |      | Tipo                |      |      |      |      |
| descricao     | varchar  | 50   |      | Descrição/Documento |      |      |      |      |
| dt_inc        | datetime |      |      | Inclusão            |      |      |      |      |
| dt_alt        | datetime |      |      | Alteração           |      |      |      |      |
| status        | char     | 1    |      | Status              |      |      |      |      |

> Tipo = E:Entrada, S:Saida

```sql

```



#### ativo_manutencao

Description: *Lançamentos Bancario/Caixas.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: SED)
- [ ] Rest Web (Rota: classefinanceira )

| NAME | TYPE | SIZE | D    | DESCRIPTION | PK   | NN   | UN   | NOTE |
| ---- | ---- | ---- | ---- | ----------- | ---- | ---- | ---- | ---- |
| id   |      |      |      | ID          | X    |      |      |      |
|      |      |      |      |             |      |      |      |      |



```sql

```







#### os_tecnico

Description: *Tecnicos.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: )
- [ ] Rest Web (Rota:  )

| NAME          | TYPE     | SIZE | D    | DESCRIPTION   | PK   | NN   | UN   | NOTE |
| ------------- | -------- | ---- | ---- | ------------- | ---- | ---- | ---- | ---- |
| id            |          |      |      | ID            | X    |      |      |      |
| empresa_id    | integer  |      |      | FK Empresa    |      |      |      |      |
| codigo_erp    | varchar  | 10   |      | Código        |      | X    |      |      |
| nome          | varchar  | 50   |      | Nome          |      | X    |      |      |
| ativo         | char     | 1    |      | Ativo         |      | X    |      |      |
| fornecedor_id | integer  |      |      | FK Fornecedor |      |      |      |      |
| telefone      | varchar  | 15   |      | Telefone      |      |      |      |      |
| foto          | text     |      |      | Foto          |      |      |      |      |
| obs           | text     |      |      | Observação    |      |      |      |      |
| dt_inc        | datetime |      |      | Inclusão      |      |      |      |      |
| dt_alt        | datetime |      |      | Alteração     |      |      |      |      |
| status        | char     | 1    |      | Status        |      |      |      |      |

> Ativo = S:Sim, N:Não

```sql

```





#### os

Description: *Lançamentos Ordem de Serviço.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: )
- [ ] Rest Web (Rota:  )

| NAME           | TYPE     | SIZE | D    | DESCRIPTION                   | PK   | NN   | UN   | NOTE |
| -------------- | -------- | ---- | ---- | ----------------------------- | ---- | ---- | ---- | ---- |
| id             |          |      |      | ID                            | X    |      |      |      |
| empresa_id     | integer  |      |      | FK Empresa                    |      | X    |      |      |
| numero_erp     | varchar  | 10   |      | Número OS                     |      | X    |      |      |
| dt_abertura    | date     |      |      | Data de Abertura              |      | X    |      |      |
| dt_prevista    | date     |      |      | Data Prevista                 |      |      |      |      |
| fornecedor_id  | integer  |      |      | FK Fornecedor                 |      |      |      |      |
| ativo_id       | integer  |      |      | FK Ativo                      |      | X    |      |      |
| funcionario_id | integer  |      |      | FK Funcionario (Requisitante) |      |      |      |      |
| tecnico_id     | integer  |      |      | FK Funcionário (Técnico)      |      |      |      |      |
| problema       | text     |      |      | Problema                      |      |      |      |      |
| diagnostico    | text     |      |      | Diagnóstico                   |      |      |      |      |
| solucao        | text     |      |      | Solução                       |      |      |      |      |
| foto_antes     | text     |      |      | Foto Antes                    |      |      |      |      |
| foto_depois    | text     |      |      | Foto Depois                   |      |      |      |      |
| dt_inc         | datetime |      |      | Inclusão                      |      |      |      |      |
| dt_alt         | datetime |      |      | Alteração                     |      |      |      |      |
| status         | char     | 1    |      | Status                        |      |      |      |      |

> 

```sql

```





#### os_servico

Description: *Lançamentos Serviços na Ordem de Serviço.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: )
- [ ] Rest Web (Rota:  )

| NAME         | TYPE     | SIZE | D    | DESCRIPTION    | PK   | NN   | UN   | NOTE |
| ------------ | -------- | ---- | ---- | -------------- | ---- | ---- | ---- | ---- |
| id           |          |      |      | ID             | X    |      |      |      |
| os_id        | integer  |      |      | FK OS          |      | X    |      |      |
| dt_servico   | date     |      |      | Data           |      | X    |      |      |
| descricao    | varchar  | 100  |      | Descrição      |      | X    |      |      |
| vlr          | double   | 14   | 2    | Valor          |      |      |      |      |
| vlr_estimado | double   | 14   | 2    | Valor Estimado |      |      |      |      |
| tecnico_id   | integer  |      |      | FK Tecnico     |      |      |      |      |
| dt_inc       | datetime |      |      | Inclusão       |      |      |      |      |
| dt_alt       | datetime |      |      | Alteração      |      |      |      |      |
| status       | char     | 1    |      | Status         |      |      |      |      |

> 

```sql

```





#### os_peca

Description: *Lançamentos Peças na Ordem de Serviço.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC
- [ ] Report
- [ ] Rest ERP (Tabela: )
- [ ] Rest Web (Rota:  )

| NAME            | TYPE     | SIZE | D    | DESCRIPTION       | PK   | NN   | UN   | NOTE |
| --------------- | -------- | ---- | ---- | ----------------- | ---- | ---- | ---- | ---- |
| id              |          |      |      | ID                | X    |      |      |      |
| os_id           | integer  |      |      | FK OS             |      | X    |      |      |
| ativo_peca_id   | integer  |      |      | FK Peca           |      |      |      |      |
| peca_avulsa     | varchar  | 50   |      | Peca Avulsa       |      |      |      |      |
| dt_mvto         | date     |      |      | Data              |      | X    |      |      |
| qtd             | double   | 10   | 2    | Qtd               |      |      |      |      |
| vlr_un          | double   | 14   | 2    | Valor UN          |      |      |      |      |
| vlr_un_estimado | double   | 14   | 2    | Valor UN Estimado |      |      |      |      |
| dt_inc          | datetime |      |      | Inclusão          |      |      |      |      |
| dt_alt          | datetime |      |      | Alteração         |      |      |      |      |
| status          | char     | 1    |      | Status            |      |      |      |      |

> 

```sql

```



 

#### cfop (X5_13)

Description: *Tipo de Entrada e Saida.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| id             | I    |      |      | ID              | X    |      |      |           |
| cofigo         | v    | 6    |      | Código          |      |      |      | X5_CHAVE  |
| descricao      | v    | 200  |      | Descrição       |      |      |      | X5_DESCRI |
| aplicacao      | m    |      |      | Aplicacao       |      |      |      |           |
| data_inclusao  | t    |      |      |                 |      |      |      |           |
| data_alteracao | t    |      |      |                 |      |      |      |           |
| status         | c    | 1    |      | Status Registro |      |      |      |           |

>   

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 





 

#### orcamento_venda (SCJ)

Description: *Movimento de Pedidos de Vendas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                   | T    | S    | D    | DESCRIPTION              | PK   | NN   | UN   | NOTE       |
| ---------------------- | ---- | ---- | ---- | ------------------------ | ---- | ---- | ---- | ---------- |
| id                     | i    |      |      | ID                       | X    |      |      |            |
| numero                 | v    | 06   |      | Numero                   |      | X    |      | CJ_NUM     |
| clientes_id            | i    |      |      | FK Cliente               |      | X    |      | CJ_CLIENTE |
| tipo_cliente           | c    | 01   |      | Tipo Cliente (R, S, F)   |      | X    |      | CJ_TIPOCLI |
| mensagem               | v    | 100  |      | Mensagem                 |      |      |      |            |
| vendedores_id_1        | i    |      |      | FK Vendedor 1            |      |      |      |            |
| comissao1              | n    | 05   | 02   | % Comissao 1             |      |      |      |            |
| vendedores_id_2        | i    |      |      | FK Vendedor 2            |      |      |      |            |
| comissao2              | n    | 05   | 02   | % Comissao 2             |      |      |      |            |
| vendedores_id_3        | i    |      |      | FK Vendedor 3            |      |      |      |            |
| comissao3              | n    | 05   | 02   | % Comissao 3             |      |      |      |            |
| condicoes_pagamento_id | i    |      |      | FK Condição de Pagamento |      |      |      | CJ_CONDPAG |
| tabela_precos_id       | i    |      |      | FK Tabela de Preço       |      |      |      | CJ_TABELA  |
| data_emissao           | d    |      |      | Data de Emissao          |      |      |      | CJ_EMISSAO |
| data_entrega           | d    |      |      | Data de Entrega          |      |      |      |            |
| data_validade          | d    |      |      | Data de Validade         |      |      |      | CJ_VALIDA  |
| transportadoras_id     | i    |      |      | FK Transpotadora         |      |      |      |            |
| frete                  | c    | 01   |      | Tipo Frete (C,F,T,R,D,S) |      |      |      |            |
| importado              | c    | 01   |      | Importado (1=Sim, 2=Nao) |      |      |      |            |
| importado_data         | d    |      |      | Data de Importação       |      |      |      |            |
| importado_hora         | t    |      |      | Hora de Importação       |      |      |      |            |
| status_orcamento       | c    | 1    |      | Status do Orçamento      |      |      |      | CJ_STATUS  |
| pedido_venda_id        | i    |      |      | Pedido de Venda          |      |      |      |            |
| vlr_frete              | n    | 14   | 2    | Valor de Frete           |      |      |      | CJ_FRETE   |
| vlr_seguro             | n    | 14   | 2    | Valor de Seguro          |      |      |      | CJ_SEGURO  |
| vlr_despesa            | n    | 14   | 2    | Despesa Acessoria        |      |      |      | CJ_DESPESA |
| desconto               | n    | 05   | 02   | % Desconto Financeiro    |      |      |      | CJ_PDESCAB |
| vlr_desconto           | n    | 14   | 2    | Valor de Desconto        |      |      |      | CJ_DESCONT |
| vlr_total_orcamento    | n    | 14   | 2    | Total do Pedido          |      |      |      |            |
| data_inclusao          | t    |      |      |                          |      |      |      |            |
| data_alteracao         | t    |      |      |                          |      |      |      |            |
| status                 | c    | 1    |      | Status Registro          |      |      |      |            |

>   status_orcamento = A:Aberto, B:Aprovado, C:Cancelado
>
>   tipo_cliente = (R-Revendedor, F-Consumidor Final)
>
>   frete = (C-CIF, F-FOB, T-Por conta de Terceiros, R-Por conta Remetente,
>   D-Por conta Destinatario, S-Sem Frete)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### orcamento_venda_item (SCK)

Description: *Itens do movimento de Pedido de Vendas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                | T    | S    | D    | DESCRIPTION           | PK   | NN   | UN   | NOTE       |
| ------------------- | ---- | ---- | ---- | --------------------- | ---- | ---- | ---- | ---------- |
| id                  | i    |      |      | ID                    | X    |      |      |            |
| orcamento_venda__id | i    |      |      | FK Pedido             |      |      |      |            |
| item                | v    | 3    |      | Sequencia             |      |      |      | CK_ITEM    |
| produtos_id         | i    |      |      | FK Produto            |      |      |      | CK_PRODUTO |
| vlr_venda_un        | n    | 14   | 5    | Preco de Venda UN     |      |      |      | CK_PRCVEN  |
| quantidade          | n    | 9    | 2    | Quantidade            |      |      |      | CK_QTDVEN  |
| vlr_total           | n    | 14   | 2    | Valor                 |      |      |      | CK_VALOR   |
| tributacao_id       | i    |      |      | FK TES                |      |      |      | CK_TES     |
| armazens_id         | i    |      |      | FK Armazem            |      |      |      | CK_LOCAL   |
| desconto            | n    | 08   | 06   | % Desconto            |      |      |      | CK_DESCONT |
| vlr_desconto        | n    | 14   | 05   | Valor de Desconto     |      |      |      | CK_VALDESC |
| comissao1           | n    | 05   | 02   | % Comissao Vendedor 1 |      |      |      |            |
| comissao2           | n    | 05   | 02   | % Comissao Vendedor 2 |      |      |      |            |
| comissao3           | n    | 05   | 02   | % Comissao Vendedor 3 |      |      |      |            |
| vlr_preco_tabela    | n    | 12   | 02   | Preço Venda (Tabela)  |      |      |      |            |
| data_inclusao       | d    |      |      | Data Alteração        |      |      |      |            |
| data_alteracao      | t    |      |      | Hora Alteração        |      |      |      |            |
| status              | c    | 01   |      | Status Registro       |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 





#### pedido_venda (SC5)

Description: *Movimento de Pedidos de Vendas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                     | T    | S    | D    | DESCRIPTION              | PK   | NN   | UN   | NOTE       |
| ------------------------ | ---- | ---- | ---- | ------------------------ | ---- | ---- | ---- | ---------- |
| id                       | i    |      |      | ID                       | X    |      |      |            |
| numero                   | v    | 6    |      | Numero                   |      | X    |      | C5_NUM     |
| clientes_id              | i    |      |      | FK Cliente               |      | X    |      | C5_CLIENTE |
| tipo_cliente             | c    | 1    |      | Tipo Cliente (R, S, F)   |      | X    |      | C5_TIPOCLI |
| mensagem                 | v    | 100  |      | Mensagem                 |      |      |      | C5_MENNOTA |
| vendedores_id_1          | i    |      |      | FK Vendedor 1            |      |      |      | C5_VEND1   |
| comissao1                | n    | 5    | 2    | % Comissao 1             |      |      |      | C5_COMIS1  |
| vendedores_id_2          | i    |      |      | FK Vendedor 2            |      |      |      | C5_VEND2   |
| comissao2                | n    | 5    | 2    | % Comissao 2             |      |      |      | C5_COMIS2  |
| vendedores_id_3          | i    |      |      | FK Vendedor 3            |      |      |      | C5_VEND3   |
| comissao3                | n    | 5    | 2    | % Comissao 3             |      |      |      | C5_COMIS3  |
| condicoes_pagamento_id   | i    |      |      | FK Condição de Pagamento |      |      |      | C5_CONDPAG |
| tabela_precos_id         | i    |      |      | FK Tabela de Preço       |      |      |      | C5_TABELA  |
| data_emissao             | d    |      |      | Data de Emissao          |      |      |      | C5_EMISSAO |
| data_saida               | d    |      |      | Data de Saida            |      |      |      | C5_FECENT  |
| hora_saida               | t    |      |      | Hora de Saida            |      |      |      | C5_HORA    |
| transportadora_id        | i    |      |      | FK Transpotadora         |      |      |      | C5_TRANSP  |
| veiculo__id              | i    |      |      | FK Veiculo               |      |      |      | C5_VEICULO |
| frete                    | c    | 1    |      | Tipo Frete (C,F,T,R,D,S) |      |      |      | C5_TPFRETE |
| especie1                 | v    | 10   |      | Especie 1                |      |      |      | C5_ESPECI1 |
| volume1                  | n    | 5    |      | Volume na Especie 1      |      |      |      | C5_VOLUME1 |
| especie2                 | v    | 10   |      | Especie 2                |      |      |      | C5_ESPECI2 |
| volume2                  | n    | 5    |      | Volume na Especie 2      |      |      |      | C5_VOLUME2 |
| importado                | c    | 1    |      | Importado (1=Sim, 2=Nao) |      |      |      | C5_IMP     |
| importado_data           | d    |      |      | Data de Importação       |      |      |      | C5_DTTR    |
| importado_hora           | t    |      |      | Hora de Importação       |      |      |      | C5_HRTR    |
| tipo_pedido              | v    | 3    |      | Tipo de Venda            |      |      |      | C5_TPVNJFS |
| faturamento_id           | i    |      |      | FK Faturamento           |      |      |      | C5_NOTA    |
| desconto                 | n    | 5    | 2    | % Desconto Financeiro    |      |      |      | C5_DESCFI  |
| vlr_desconto             | n    | 14   | 2    | Valor de Desconto        |      |      |      | C5_DESCONT |
| vlr_acrescimo_financeiro | n    | 14   | 2    | Acrescimo Financeiro     |      |      |      | C5_ACRSFIN |
| vlr_seguro               | n    | 14   | 2    |                          |      |      |      |            |
| vlr_total_pedido         | n    | 14   | 2    | Total do Pedido          |      |      |      | TOTAL      |
| data_inclusao            | t    |      |      | Data Alteração           |      |      |      |            |
| data_alteracao           | t    |      |      | Hora Alteração           |      |      |      |            |
| status                   | c    | 1    |      | Status Registro          |      |      |      |            |

>   tipo_pedido = (001=Venda, 002=Bonificação, 003=Troca/Devolução)

>   tipo_cliente = (R-Revendedor, F-Consumidor Final)

>   frete = (C-CIF, F-FOB, T-Por conta de Terceiros, R-Por conta Remetente,
>   D-Por conta Destinatario, S-Sem Frete)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### pedido_venda_item (SC6)

Description: *Itens do movimento de Pedido de Vendas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME              | T    | S    | D    | DESCRIPTION           | PK   | NN   | UN   | NOTE       |
| ----------------- | ---- | ---- | ---- | --------------------- | ---- | ---- | ---- | ---------- |
| id                | i    |      |      | ID                    | X    |      |      |            |
| pedidos_venda__id | i    |      |      | FK Pedido             |      |      |      |            |
| item              | v    | 3    |      | Sequencia             |      |      |      | C6_ITEM    |
| produtos_id       | i    |      |      | FK Produto            |      |      |      | C6_PRODUTO |
| vlr_venda_un      | n    | 14   | 5    | Preco de Venda UN     |      |      |      | C6_PRCVEN  |
| quantidade        | n    | 9    | 2    | Quantidade            |      |      |      | C6_QTDVEN  |
| vlr_total         | n    | 14   | 2    | Valor                 |      |      |      | C6_VALOR   |
| tributacao_id     | i    |      |      | FK TES                |      |      |      | C6_TES     |
| armazens_id       | i    |      |      | FK Armazem            |      |      |      | C6_LOCAL   |
| desconto          | n    | 8    | 6    | % Desconto            |      |      |      | C6_DESCONT |
| vlr_desconto      | n    | 14   | 5    | Valor de Desconto     |      |      |      | C6_VALDESC |
| comissao1         | n    | 5    | 2    | % Comissao Vendedor 1 |      |      |      | C6_COMISS1 |
| comissao2         | n    | 5    | 2    | % Comissao Vendedor 2 |      |      |      | C6_COMISS2 |
| comissao3         | n    | 5    | 2    | % Comissao Vendedor 3 |      |      |      | C6_COMISS3 |
| vlr_preco_tabela  | n    | 12   | 2    | Preço Venda (Tabela)  |      |      |      | C6_PRUNIT  |
| data_inclusao     | y    |      |      | Data Alteração        |      |      |      |            |
| data_alteracao    | y    |      |      | Hora Alteração        |      |      |      |            |
| status            | c    | 1    |      | Status Registro       |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### faturamento ( SF2 )

Description: *Movimento de Faturamento.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                  | T    | S    | D    | DESCRIPTION              | PK   | NN   | UN   | NOTE       |
| --------------------- | ---- | ---- | ---- | ------------------------ | ---- | ---- | ---- | ---------- |
| id                    | i    |      |      |                          | X    |      |      |            |
| documento             | v    | 9    |      | Documento                |      |      |      | F2_DOC     |
| serie                 | v    | 3    |      | Serie                    |      |      |      | F2_SERIE   |
| clientie_id           | i    |      |      | FK Cliente               |      |      |      | F2_CLIENTE |
| mensagem              | v    | 100  |      | Mensagem da Nota         |      |      |      | F2_MENNOTA |
| vendedore_id_1        | i    |      |      | FK Vendedor 1            |      |      |      | F2_VEND1   |
| vendedore_id_2        | i    |      |      | FK Vendedor 2            |      |      |      | F2_VEND2   |
| vendedore_id_3        | i    |      |      | FK Vendedor 3            |      |      |      | F2_VEND3   |
| condicao_pagamento_id | i    |      |      | FK Condição de Pagamento |      |      |      | F2_COND    |
| data_emissao          | d    |      |      | Data de Emissao          |      |      |      | F2_EMISSAO |
| data_saida            | d    |      |      | Data de Saida            |      |      |      | F2_DTENTR  |
| transportadora_id     | i    |      |      | FK Transportadores       |      |      |      | F2_TRANSP  |
| veiculo_id            | i    | 1    |      | FK Veiculo               |      |      |      | F2_VEICUL1 |
| vlr_frete             | n    | 14   | 2    | Valor do Frete           |      |      |      | F2_FRETE   |
| vlr_seguro            | n    | 14   | 2    | Valor do Seguro          |      |      |      | F2_SEGURO  |
| vlr_icms_frete        | n    | 14   | 2    | ICMS de Frete            |      |      |      | F2_ICMFRET |
| vlr_bruto             | n    | 14   | 2    | Valor Bruto              |      |      |      | F2_VALBRUT |
| vlr_icms              | n    | 14   | 2    | Valor ICMS               |      |      |      | F2_VALICM  |
| vlr_ipi               | n    | 14   | 2    | Valor IPI                |      |      |      | F2_VALIPI  |
| vlr_mercadoria        | n    | 14   | 2    | Valor Mercadoria         |      |      |      | F2_VALMERC |
| vlr_desconto          | n    | 14   | 2    | Desconto                 |      |      |      | F2_DESCONT |
| vlr_icms_st           | n    | 14   | 2    | ICMS-ST                  |      |      |      | F2_ICMRET  |
| pedidos_venda_id      | i    |      |      | FK Pedido                |      |      |      |            |
| chave_nfe             | v    | 44   |      | Chave NFE                |      |      |      | F2_CHVNFE  |
| data_inclusao         | d    |      |      | Data Alteração           |      |      |      |            |
| data_alteracao        | t    |      |      | Hora Alteração           |      |      |      |            |
| status                | c    | 1    |      | Status Registro          |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### faturamento_item ( SD2 )

Description: *Itens do Movimento de Faturamento.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE       |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| ID             | i    |      |      | ID              | X    |      |      |            |
| faturamento_id | i    |      |      | FK Faturamento  |      |      |      |            |
| item           | v    | 3    |      | Item            |      |      |      | D2_ITEM    |
| produto_id     | i    |      |      | FK Produto      |      |      |      | D2_COD     |
| quantidade     | n    | 11   | 2    | Quantidade      |      |      |      | D2_QUANT   |
| vlr_un         | n    | 14   | 2    | Vlr. UIN        |      |      |      | D2_PRCVEN  |
| vlr_total      | n    | 14   | 2    | Total           |      |      |      | D2_TOTAL   |
| tributacao_id  | i    |      |      | TES             |      |      |      | D2_TES     |
| armazem_id     | i    |      |      | Armazem         |      |      |      | D2_LOCAL   |
| desconto       | n    | 5    | 2    | % Desconto      |      |      |      | D2_DESC    |
| vlr_ipi        | n    | 14   | 2    | Valor IPI       |      |      |      | D2_VALIPI  |
| vlr_icms       | n    | 14   | 2    | Valor ICMS      |      |      |      | D2_VALICM  |
| vlr_icms_st    | n    | 14   | 2    | Valor ST        |      |      |      | D2_ICMSRET |
| vlr_acrescimo  | n    | 14   | 2    | Valor Acrescimo |      |      |      | D2_VALACRS |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |            |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |            |
| status         | c    | 1    |      | Status Registro |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### banco

Description: *Cadastro de Bancos/Agências.*

- [ ] DataBase Desing 
- [ ] SQL Script
- [ ] Model
- [ ] CRUD/MVC (Revisado 01/06/2021)
- [ ] Report
- [ ] Rest ERP (Tabela: SA6)
- [ ] Rest Web (Rota: banco)

| NAME          | TYPE     | SIZE | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE                  |
| ------------- | -------- | ---- | ---- | --------------- | ---- | ---- | ---- | --------------------- |
| id            | integer  |      |      | ID              | X    |      |      |                       |
| empresa_id    | integer  |      |      | FK Empresa      |      |      |      |                       |
| codigo_erp    | varchar  | 10   |      | Banco           |      | X    |      | A6_COD                |
| agencia       | varchar  | 10   |      | Nro. Agencia    |      |      |      | A6_AGENCIA / A6_DVAGE |
| conta         | varchar  | 15   |      | Número da Conta |      |      |      | A6_NUMCON / A6_DVCTA  |
| nome          | varchar  | 100  |      | Nome            |      | X    |      | A6_NOME               |
| nome_reduzido | varchar  | 50   |      | Nome Reduzido   |      |      |      | A6_NREDUZ             |
| ativo         | char     | 1    |      | Ativo           |      |      |      | A6_BLOKED             |
| endereco      | varchar  | 100  |      | Endereço        |      |      |      | A6_END                |
| bairro        | varchar  | 50   |      | Bairro          |      |      |      | A6_BAIRRO             |
| municipio     | varchar  | 50   |      | Municipio       |      |      |      | A6_MUN                |
| uf_id         | integer  |      |      | FK UF           |      |      |      | A6_EST                |
| telefone      | varchar  | 15   |      | Telefone        |      |      |      | A6_TEL                |
| contato       | varchar  | 50   |      | Contato         |      |      |      | A6_CONTATO            |
| dt_inc        | datetime |      |      | Inclusão        |      |      |      |                       |
| dt_alt        | datetime |      |      | Alteração       |      |      |      |                       |
| status        | char     | 01   |      | Status Registro |      |      |      |                       |

> ativo = S:Sim, N:Não (Protheus: Bloqueado 1=Sim, 2=Não)

```sql
<chave> AS id, <DePara> AS empresa_id, A6_COD AS codigo_erp, A6_AGENCIA + A6_DVAG, A6_NUMCON + A6_DVCTA AS , A6_NOME AS nome, A6_NREDUZ AS nome_reduzido, A6_BLOKED AS ativo, A6_END AS endereco, A6_BAIRRO AS bairro, A6_MUN AS municipio, A6_EST AS uf_id, A6_TEL AS telefone, A6_CONTATO AS contato, dt_inc, dt_alt, status
```

 

#### tipo_titulo ( SX5 = 05 )

Description: *Tabelas Genéricas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE      |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | --------- |
| ID             | I    |      |      | ID              | X    |      |      |           |
| codigo         | V    | 06   |      | Chave           |      | X    |      | X5_CHAVE  |
| descricao      | V    | 100  |      | Descrição       |      | X    |      | X5_DESCRI |
| data_inclusao  | D    |      |      | Data Alteração  |      |      |      |           |
| data_alteracao | T    |      |      | Hora Alteração  |      |      |      |           |
| status         | C    | 01   |      | Status Registro |      |      |      |           |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### titulo_recebe ( SE1 )

Description: *Movimento de Titulos a Receber.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                     | T    | S    | D    | DESCRIPTION             | PK   | NN   | UN   | NOTE       |
| ------------------------ | ---- | ---- | ---- | ----------------------- | ---- | ---- | ---- | ---------- |
| id                       | i    |      |      | ID                      | X    |      |      |            |
| prefixo                  | v    | 3    |      | Prefixo                 |      |      |      | E1_PREFIXO |
| titulo                   | v    | 10   |      | Titulo                  |      | X    |      | E1_NUM     |
| parcela                  | v    | 3    |      | Parcela                 |      |      |      | E1_PARCELA |
| tipo_titulo_id           | I    |      |      | FK Tipo Titulo          |      | X    |      | E1_TIPO    |
| cliente_id               | I    |      |      | FK Cliente              |      | X    |      | E1_CLIENTE |
| emissao                  | d    |      |      | Data de Emissão         |      | X    |      | E1_EMISSAO |
| vencimento               | d    |      |      | Data de Vencimento Real |      | X    |      | E1_VENCREA |
| vlr_titulo               | n    | 18   | 2    | Valor do Titulo         |      | X    |      | E1_VALOR   |
| vlr_saldo                | n    | 18   | 2    | Saldo do Titulo         |      |      |      | E1_SALDO   |
| historico                | v    | 100  |      | Historico               |      |      |      | E1_HIST    |
| pedido_venda_id          | i    |      |      | FK Pedido               |      |      |      | E1_PEDIDO  |
| vendedor_id_1            | i    |      |      | FK Vendedor 1           |      |      |      | E1_VEND1   |
| comissao1                | n    | 5    | 2    | % Comissao 1            |      |      |      | E1_COMISS1 |
| vendedor_id_2            | i    |      |      | FK Vendedor 2           |      |      |      | E1_VEND2   |
| comissao2                | n    | 5    | 2    | % Comissao 2            |      |      |      | E1_COMISS2 |
| vendedor_id_3            | i    |      |      | FK Vendedor 3           |      |      |      | E1_VEND3   |
| comissao3                | n    | 5    | 2    | % Comissao 3            |      |      |      | E1_COMISS3 |
| banco_id                 | I    |      |      | FK Banco/Portador       |      |      |      | E1_PORTADO |
| fluxo_caixa              | c    | 1    |      | Fluxo de Caixa          |      |      |      | E1_FLUXO   |
| contabil_conta_id        | i    |      |      | FK Conta Contabil       |      |      |      | E1_CONTA   |
| contabil_centro_custo_id | i    |      |      | FK Centro de Custo      |      |      |      | E1_CCUSTO  |
| data_inclusao            | t    |      |      | Data Alteração          |      |      |      |            |
| data_alteracao           | t    |      |      | Hora Alteração          |      |      |      |            |
| status                   | c    | 1    |      | Status Registro         |      |      |      |            |

> fluxo_caixa = S:Sim, N:Não

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### titulo_receber_classe ( )

Description: *Tabelas Genéricas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                 | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE       |
| -------------------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | ---------- |
| id                   | I    |      |      | ID                   | X    |      |      |            |
| titulo_receber_id    | i    |      |      |                      |      |      |      |            |
| classe_financeira_id | i    |      |      | FK Classe Financeira |      |      |      | E1_NATUREZ |
| valor                | n    | 18   | 2    | Valor                |      |      |      |            |
| data_inclusao        | D    |      |      | Data Alteração       |      |      |      |            |
| data_alteracao       | T    |      |      | Hora Alteração       |      |      |      |            |
| status               | C    | 01   |      | Status Registro      |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~





#### titulo_pagar ( SE2 )

Description: *Movimento de Titulos a Pagar.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                     | T    | S    | D    | DESCRIPTION                 | PK   | NN   | UN   | NOTE       |
| ------------------------ | ---- | ---- | ---- | --------------------------- | ---- | ---- | ---- | ---------- |
| id                       | I    |      |      |                             | X    |      |      |            |
| prefixo                  | v    | 3    |      | Prefixo                     |      |      |      | E2_PREFIXO |
| titulo                   | v    | 10   |      | Numero                      |      | X    |      | E2_NUM     |
| parcela                  | v    | 3    |      | Parcela                     |      |      |      | E2_PARCELA |
| tipos_titulos_id         | i    |      |      | FK Tipo Titulo              |      |      |      | E2_TIPO    |
| fornecedores_id          | i    |      |      | FK Fornecedor               |      | X    |      | E2_FORNECE |
| emissao                  | d    |      |      | Data de Emissão             |      | X    |      | E2_EMISSAO |
| vencimento               | d    |      |      | Data de Vencimento Real     |      | X    |      | E2_VENCREA |
| vlr_titulo               | n    | 18   | 2    | Valor do Titulo             |      | X    |      | E2_VALOR   |
| vlr_saldo                | n    | 18   | 2    | Saldo do Titulo             |      |      |      | E2_SALDO   |
| historico                | v    | 100  |      | Histórico                   |      |      |      | E2_HIST    |
| fluxo_caixa              | c    | 1    |      | Fluxo de Caixa              |      |      |      | E2_FLUXO   |
| contabil_conta_id        | i    |      |      | FK Conta Contabil - Debito  |      |      |      | E2_CONTAD  |
| contabil_centro_custo_id | i    |      |      | FK Centro de Custo - Debito |      |      |      | E2_CCD     |
| pedido_compra_id         | i    |      |      | FK Pedido de Compra         |      |      |      |            |
| data_inclusao            | t    |      |      | Data Alteração              |      |      |      |            |
| data_alteracao           | t    |      |      | Hora Alteração              |      |      |      |            |
| status                   | c    | 1    |      | Status Registro             |      |      |      |            |

> fluxo_caixa = S:Sim, N:Não

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### titulo_pagar_classe (  )

Description: *Tabelas Genéricas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                 | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE       |
| -------------------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | ---------- |
| id                   | I    |      |      | ID                   | X    |      |      |            |
| titulo_pagar_id      | i    |      |      |                      |      |      |      |            |
| classe_financeira_id | i    |      |      | FK Classe Financeira |      |      |      | E2_NATUREZ |
| valor                | n    | 18   | 2    | Valor                |      |      |      |            |
| data_inclusao        | D    |      |      | Data Alteração       |      |      |      |            |
| data_alteracao       | T    |      |      | Hora Alteração       |      |      |      |            |
| status               | C    | 01   |      | Status Registro      |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~





#### movimento_bancario ( SE5 )

Description: *Lançamentos Bancario/Caixas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                             | T    | S    | D    | DESCRIPTION                 | PK   | NN   | UN   | NOTE       |
| -------------------------------- | ---- | ---- | ---- | --------------------------- | ---- | ---- | ---- | ---------- |
| ID                               | i    |      |      |                             | X    |      |      |            |
| data_mvto                        | d    |      |      | Data                        |      | X    |      | E5_DATA    |
| banco_id                         | i    |      |      | FK Banco                    |      | X    |      | E5_BANCO   |
| valor                            | n    | 18   | 2    | Valor                       |      | X    |      | E5_VALOR   |
| vlr_juros                        | n    | 14   | 2    | Valor de Juros              |      |      |      | E5_VLJUROS |
| vlr_multa                        | n    | 14   | 2    | Valor de Multa              |      |      |      | E5_VLMULTA |
| vlr_correcao                     | n    | 14   | 2    | Valor de Correcao Monetaria |      |      |      | E5_CORRE   |
| vlr_desconto                     | n    | 14   | 2    | Valor de Desconto           |      |      |      | E5_DESCO   |
| tipo                             | c    | 1    |      | Tipo (D,C,X)                |      | X    |      | E5_TIPOLAN |
| cheque                           | v    | 15   |      | Nro. Cheque                 |      |      |      | E5_NUMCHEQ |
| documento                        | v    | 50   |      | Documento                   |      |      |      | E5_DOCUMEN |
| historico                        | v    | 100  |      | Histórico                   |      |      |      | E5_HISTOR  |
| prefixo                          | v    | 3    |      | Prefixo                     |      |      |      | E5_PREFIXO |
| titulo                           | v    | 10   |      | Titulo                      |      |      |      | E5_NUMERO  |
| parcela                          | v    | 3    |      | Parcela                     |      |      |      | E5_PARCELA |
| cliente_id                       | i    |      |      | Cliente                     |      |      |      | E5_CLIFOR  |
| fornecedor_id                    | i    |      |      | Fornecedor                  |      |      |      | E5_CLIFOR  |
| contabil_conta_id_credito        | i    |      |      | FK Conta Contabil           |      |      |      | E5_CREDITO |
| contabil_conta_id_debito         | i    |      |      | FK Conta Contabil           |      |      |      | E5_DEBITO  |
| contabil_centro_custo_id_credito | i    |      |      | FK Centro de Custo          |      |      |      | E5_CCC     |
| contabil_centro_custo_id_debito  | i    |      |      | FK Centro de Custo          |      |      |      | E5_CCD     |
| dt                               | t    |      |      | Data Alteração              |      |      |      |            |
| hr                               | t    |      |      | Hora Alteração              |      |      |      |            |
| status                           | c    | 1    |      | Status Registro             |      |      |      |            |

>   tipo = (D=Débito, C=Crédito, X=Partida Dobrada)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### movimento_bancario_classe (  )

Description: *Tabelas Genéricas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                  | T    | S    | D    | DESCRIPTION          | PK   | NN   | UN   | NOTE       |
| --------------------- | ---- | ---- | ---- | -------------------- | ---- | ---- | ---- | ---------- |
| id                    | I    |      |      | ID                   | X    |      |      |            |
| movimento_bancario_id | i    |      |      |                      |      |      |      |            |
| classe_financeira_id  | i    |      |      | FK Classe Financeira |      |      |      | E5_NATUREZ |
| valor                 | n    | 18   | 2    | Valor                |      |      |      |            |
| data_inclusao         | D    |      |      | Data Alteração       |      |      |      |            |
| data_alteracao        | T    |      |      | Hora Alteração       |      |      |      |            |
| status                | C    | 01   |      | Status Registro      |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~





#### banco_saldo ( SE8 )

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME                   | T    | S    | D    | DESCRIPTION         | PK   | NN   | IN   | NOTE       |
| ---------------------- | ---- | ---- | ---- | ------------------- | ---- | ---- | ---- | ---------- |
| id                     | I    |      |      |                     | X    |      |      |            |
| banco_id               | i    |      |      | Banco               |      |      |      | E8_BANCO   |
| data_saldo_atual       | d    |      |      | Data Saldo Atual    |      |      |      | E8_DTSALAT |
| vlr_saldo_atual        | n    | 18   | 2    | Saldo Atual         |      |      |      | E8_SALATUA |
| data_saldo_anterior    | d    |      |      | Data Saldo Anterior |      |      |      | E8_DTSALAN |
| vlr_saldo_anterior     | n    | 18   | 2    | Saldo Anterior      |      |      |      | E8_SALANT  |
| vlr_saldo_reconciliado | n    | 18   | 2    | Saldo Reconciliado  |      |      |      | E8_SALRECO |
| data_inclusao          | t    |      |      | Data Alteração      |      |      |      |            |
| data_alteracao         | t    |      |      | Hora Alteração      |      |      |      |            |
| status                 | c    | 1    |      | Status Registro     |      |      |      |            |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### compra_tabela_preco ( AIA )

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### compra_tabela_preco_item ( AIB )

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_solicitante ( SAI )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



 **compra_comprador ( SY1 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_aprovador ( SAK )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_permissao ( REG )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



**compra_perfil ( DHL )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



**compra_solicitacao ( SC1 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



**compra_cotacao (  )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_cotacao_item (  )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



**compra_pedido ( SC7 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_pedido_item ( SC7 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_pre_nota ( SD1 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_pre_nota_item ( REG )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



**compra_entrada ( SD1 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

**compra_entrada_item ( SD1 )**

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | IN   | NOTE |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---- |
| id             | I    |      |      |                 | X    |      |      |      |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |      |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |      |
| status         | c    | 1    |      | Status Registro |      |      |      |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 





#### verba (SRV)

Description: *Cadastro de Verbas.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME        | T | S  | D | DESCRIPTION     | PK | NN | UN | NOTE       |
|-------------|---|----|---|-----------------|----|----|----|------------|
| id          | I |    |   | ID              | X  |    |    |            |
| registro    | I |    |   | Registro ERP    |    |    |    |            |
| empresas_id | I |    |   | FK Empresa      |    |    |    | RV_FILIAL  |
| codigo      | V | 03 |   | Código          |    |    | X  | RV_COD     |
| descricao   | V | 50 |   | Descrição       |    |    | X  | RV_DESC    |
| tipo        | C | 01 |   | Tipo            |    |    | X  | RV_TIPOCOD |
| dt          | D |    |   | Data Alteração  |    |    |    |            |
| hr          | T |    |   | Hora Alteração  |    |    |    |            |
| status      | C | 01 |   | Status Registro |    |    |    |            |
| md5         | C | 32 |   | Chave MD5       |    |    |    |            |

>   tipo = (1=Provento, 2=Desconto)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
<chave> AS id, <regsitro> AS registro, <DePara> AS empresas_id, RV_COD AS codigo, RV_DESC AS descricao, RV_TIPOCOD AS tipo, dt, hr, status, md5
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### RH_MOV_FUN

Description: *Movimento de Holerite.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME    | T | S  | D | DESCRIPTION     | PK | NN | UN | NOTE |
|---------|---|----|---|-----------------|----|----|----|------|
| ID      |   |    |   |                 | X  |    |    |      |
| COD_FUN | V | 06 |   | Funcionário     |    |    | X  |      |
| MES     | N | 02 |   | Mes             |    |    | X  |      |
| ANO     | N | 04 |   | Ano             |    |    | X  |      |
| DT      | D |    |   | Data Alteração  |    |    |    |      |
| HR      | T |    |   | Hora Alteração  |    |    |    |      |
| STATUS  | C | 01 |   | Status Registro |    |    |    |      |
| MD5     | C | 32 |   | Chave MD5       |    |    |    |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`DP_MVTO` (`ID`, `COD_FUN`, `MES`, `ANO`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### DP_MVTO_ITENS

Description: *Movimento do Holerite.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME    | T | S  | D  | DESCRIPTION     | PK | NN | IN | NOTE |
|---------|---|----|----|-----------------|----|----|----|------|
| ID      | I |    |    | ID              | X  |    |    |      |
| COD_FUN | V | 06 |    | Funcionário     |    | X  |    |      |
| MES     | N | 02 |    | Mes             |    | X  |    |      |
| ANO     | N | 04 |    | Ano             |    | X  |    |      |
| VERB_ID | V | 03 |    | Verba           |    | X  |    |      |
| TIPO    | C | 01 |    | Tipo            |    | X  |    |      |
| DT_LCTO | D |    |    | Data            |    | X  |    |      |
| QTD     | N | 09 | 02 | Quantidade      |    |    |    |      |
| VLR     | N | 14 | 02 | Valor           |    |    |    |      |
| DT      | D |    |    | Data Alteração  |    |    |    |      |
| HR      | T |    |    | Hora Alteração  |    |    |    |      |
| STATUS  | C | 01 |    | Status Registro |    |    |    |      |
| MD5     | C | 32 |    | Chave MD5       |    |    |    |      |

>   TIPO = (H=Hora, V=Valor, D=Dias)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`DP_MVTO_ITENS` (`DP_MVTO_ID`, `COD_FUN`, `MES`, `ANO`, `VERB_ID`, `TIPO`, `DT_LCTO`, `QTD`, `VLR`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### frota_abastecimento

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME            | T | S  | D  | DESCRIPTION     | PK | NN | IN | NOTE |
|-----------------|---|----|----|-----------------|----|----|----|------|
| ID              | I |    |    | ID              | X  |    |    |      |
| registros       | I |    |    | Registro ERP    |    |    |    |      |
| empresas_id     | I |    |    | FK Empresa      |    |    |    |      |
| fornecedores_id | I |    |    | FK Fornecedor   |    | X  |    |      |
| motoristas_id   | I |    |    | FK Motorista    |    | X  |    |      |
| veiculos_id     | V | 10 |    | FK Veiculo      |    | X  |    |      |
| data_mvto       | D |    |    | Data            |    | X  |    |      |
| documento       | V | 15 |    | Documento       |    |    |    |      |
| kms             | N | 06 |    | KM              |    | X  |    |      |
| litros          | N | 06 | 02 | Qtd. Litros     |    | X  |    |      |
| vlr_total       | N | 14 | 02 | Valor Total     |    | X  |    |      |
| tipo            | C | 01 |    | Tipo            |    | X  |    |      |
| dt              | D |    |    | Data Alteração  |    |    |    |      |
| hr              | T |    |    | Hora Alteração  |    |    |    |      |
| status          | C | 01 |    | Status Registro |    |    |    |      |
| md5             | C | 32 |    | Chave MD5       |    |    |    |      |

>   tipo = 1-Gasolina, 2-Alcool, 3-Diesel, 5-Outro

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
id, registros, empressas_id, fornecedores_id, motoristas_id, veiculos_id, data_mvto, documento, kms, litros, vlr_total, tipo, dt, hr, status, md5
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### frota_manutencao

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME            | T | S  | D  | DESCRIPTION       | PK | NN | IN | NOTE |
|-----------------|---|----|----|-------------------|----|----|----|------|
| id              | I |    |    | ID                | X  |    |    |      |
| registro        | I |    |    | Registro ERP      |    |    |    |      |
| empresas_id     | I |    |    | FK Empresa        |    | X  |    |      |
| fornecedores_id | I |    |    | FK Fornecedor     |    |    |    |      |
| motoristas_id   | I |    |    | FK Motorista      |    |    |    |      |
| veiculos_id     | I |    |    | FK Veiculo        |    | X  |    |      |
| data_mvto       | D |    |    | Data              |    | X  |    |      |
| documento       | V | 15 |    | Documento         |    |    |    |      |
| kms             | N | 06 |    | KM                |    | X  |    |      |
| interno         | C | 01 |    | Movimento Interno |    | X  |    |      |
| vlr_total       | N | 14 | 02 | Valor Total       |    |    |    |      |
| tipo            | C | 01 |    | Tipo              |    |    |    |      |
| observacao      | M |    |    | Observação        |    |    |    |      |
| dt              | D |    |    | Data Alteração    |    |    |    |      |
| hr              | T |    |    | Hora Alteração    |    |    |    |      |
| status          | C | 01 |    | Status Registro   |    |    |    |      |
| md5             | C | 32 |    | Chave MD5         |    |    |    |      |

>   tipo = 1-Pecas, 2-Servicos, 3-Outros

>   interno = S-Sim, N-Não

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
id, registro, emrpesas_id, fornecedores_id, motoristas_id, veiculos_id, data_mvto, documento, kms, interno, vlr_total, tipo, observacao, dt, hr, status, md5
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### motorista_ajudante (DAU)

Description: *Cadastro de Motoristas.*

-   [ ] DataBase Desing
-   [ ] Model
-   [ ] SQL Script
-   [ ] CRUD/MVC
-   [ ] Rest Web
-   [ ] Rest ERP
-   [ ] Report

| NAME           | T    | S    | D    | DESCRIPTION     | PK   | NN   | UN   | NOTE       |
| -------------- | ---- | ---- | ---- | --------------- | ---- | ---- | ---- | ---------- |
| id             | i    |      |      | ID              | x    |      |      |            |
| codigo         | v    | 10   |      | Código          |      | x    |      | DAU_COD    |
| ativo          | c    | 1    |      | Ativo           |      | x    |      |            |
| nome           | v    | 100  |      | Nome            |      | x    |      | DAU_NOME   |
| nome_social    | v    | 50   |      | Apelido         |      |      |      | DAU_NREDUZ |
| endereco       | v    | 100  |      | Endereço        |      |      |      | DAU_END    |
| endereco_nro   | v    | 10   |      | Numero          |      |      |      |            |
| complemento    | v    | 30   |      | Complemento     |      |      |      |            |
| bairro         | v    | 30   |      | Bairro          |      |      |      | DAU_BAIRRO |
| uf_id          | i    |      |      | UF              |      |      |      | DAU_EST    |
| municipios_id  | i    |      |      | Municipio       |      |      |      | DAU_MUN    |
| cep            | v    | 10   |      | CEP             |      |      |      | DAU_CEP    |
| telefone       | v    | 15   |      | Telefone        |      |      |      | DAU_TEL    |
| cpf            | v    | 20   |      | CPF             |      | X    |      | DAU_CGC    |
| foto           | b    |      |      | Foto            |      |      |      |            |
| observacao     | m    |      |      | Obsevação       |      |      |      |            |
| data_inclusao  | t    |      |      | Data Alteração  |      |      |      |            |
| data_alteracao | t    |      |      | Hora Alteração  |      |      |      |            |
| status         | c    | 1    |      | Status Registro |      |      |      |            |

>   ativo = S:Sim (1), N:Não (2)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 





#### BEM_GRP

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME      | T | S  | D | DESCRIPTION     | PK | NN | UN | NOTE |
|-----------|---|----|---|-----------------|----|----|----|------|
| BG_ID     | I |    |   |                 | X  |    |    |      |
| BG_FILIAL | V | 09 |   | Empresa         |    |    | X  |      |
| BG_COD    | V | 03 |   | Codigo          |    |    | X  |      |
| BG_DESC   | V | 50 |   | Descricao       |    |    |    |      |
| DT        | D |    |   | Data Alteração  |    |    |    |      |
| HR        | T |    |   | Time Alteração  |    |    |    |      |
| STATUS    | C | 01 |   | Status Registro |    |    |    |      |
| MD5       | C | 32 |   | Chave MD5       |    |    |    |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`BEM_GRP` (`BG_ID`, `BG_FILIAL`, `BG_COD`, `BG_DESC`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### BEM

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME         | T   | S   | D | DESCRIPTION            | PK | NN | UN | NOTE |
|--------------|-----|-----|---|------------------------|----|----|----|------|
| BEM_ID       | I   |     |   | ID                     | X  |    |    |      |
| BEM_FILIAL   | V   | 09  |   | Empresa                |    |    | X  |      |
| BEM_COD      | V   | 06  |   | Código                 |    |    | X  |      |
| BEM_DESC     | V   | 100 |   | Descrição              |    | X  |    |      |
| BEM_GRP      | V   | 03  |   | Grupo                  |    |    |    |      |
| BEM_PLAQUETA | V   | 10  |   | Plaqueta               |    |    |    |      |
| BEM_ATIVO    | C   | 01  |   | Ativo (S-Sim, N=Não)   |    |    |    |      |
| BEM_AQUIS    | D   |     |   | Data de Aquisição      |    |    |    |      |
| BEM_FORN     | V\` | 06  |   | Fornecedor             |    |    |    |      |
| BEM_NF       | V   | 10  |   | NF de Aquisição        |    |    |    |      |
| BEM_GARANTIA | D   |     |   | Data final de Garantia |    |    |    |      |
| BEM_BAIXA    | D   |     |   | Data da Baixa          |    |    |    |      |
| BEM_MOTIVO   | C   | 01  |   | Motivo da Baixa        |    |    |    |      |
| DT           | D   |     |   | Data Alteração         |    |    |    |      |
| HR           | T   |     |   | Hora Alteração         |    |    |    |      |
| STATUS       | C   | 01  |   | Status Registro        |    |    |    |      |
| MD5          | C   | 32  |   | Chave MD5              |    |    |    |      |

>   BEM_MOTIVO = V=Venda, T=Troca, P=Perda, E=Extravio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`BEM` (`BEM_ID`, `BEM_FILIAL`, `BEM_COD`, `BEM_DESC`, `BEM_GRP`, `BEM_PLAQUETA`, `BEM_ATIVO`, `BEM_AQUIS`, `BEM_FORN`, `BEM_NF`, `BEM_GARANTIA`, `BEM_BAIXA`, `BEM_MOTIVO`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### BEM_MVTO

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME        | T | S   | D  | DESCRIPTION     | PK | NN | IN | NOTE |
|-------------|---|-----|----|-----------------|----|----|----|------|
| BEMV_ID     | I |     |    | ID              | X  |    |    |      |
| BEMV_FILIAL | V | 09  |    | Empresa         |    | X  |    |      |
| BEMV_COD    | V | 06  |    | Código          |    | X  |    |      |
| BEMV_REG    | N |     |    | Registro        |    |    |    |      |
| BEMV_DT     | D |     |    | Data            |    |    |    |      |
| BEMV_TIPO   | C | 01  |    | Tipo            |    |    |    |      |
| BEMV_DESC   | V | 100 |    | Descrição       |    |    |    |      |
| BEMV_QTD    | N | 09  | 2  | Quantidade      |    |    |    |      |
| BEMV_VLR    | N | 14  | 02 | Valor           |    |    |    |      |
| BEMV_OBS    | M |     |    | Observação      |    |    |    |      |
| DT          | D |     |    | Data Alteração  |    |    |    |      |
| HR          | T |     |    | Hora Alteração  |    |    |    |      |
| STATUS      | C | 01  |    | Status Registro |    |    |    |      |
| MD5         | C | 32  |    | Chave MD5       |    |    |    |      |

>   BEMV_TIPO = P=Peca, S=Servico, R=Regulagem

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`BEM_MVTO` (`BEM_ID`, `BEMV_FILIAL`, `BEMV_COD`, `BEMV_REG`, `BEMV_DT`, `BEMV_TIPO`, `BEMV_DESC`, `BEMV_QTD`, `BEMV_VLR`, `BEMV_OBS`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 

#### SG1 (ESTRUTURA)

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME      | T | S  | D  | DESCRIPTION             | PK | NN | IN | NOTE |
|-----------|---|----|----|-------------------------|----|----|----|------|
| ID_SG1    | I |    |    | ID                      | X  |    |    |      |
| G1_FILIAL | V | 09 |    | Empresa                 |    |    |    |      |
| G1_COD    | V | 30 |    | Produto                 |    |    |    |      |
| G1_COMP   | V | 30 |    | Componente              |    |    |    |      |
| G1_TRT    | V | 03 |    | Sequencia               |    |    |    |      |
| G1_QUANT  | N | 12 | 6  | Quantidade              |    |    |    |      |
| G1_PERDA  | N | 05 | 02 | % Perda                 |    |    |    |      |
| G1_OBSERV | V | 50 |    | Observação              |    |    |    |      |
| G1_FIXVAR | C | 01 |    | V=Variavel, F=Fixa      |    |    |    |      |
| G1_NIV    | C | 02 |    | Nivel                   |    |    |    |      |
| G1_LOCCON | C | 02 |    | Armazem Consumo         |    |    |    |      |
| G1_FANTAS | C | 01 |    | Fantasma (S/N)          |    |    |    |      |
| G1_USAALT | C | 01 |    | Usa Alternativo ( S/N ) |    |    |    |      |
| DT        | D |    |    | Data Alteração          |    |    |    |      |
| HR        | T |    |    | Hora Alteração          |    |    |    |      |
| STATUS    | C | 01 |    | Status Registro         |    |    |    |      |
| MD5       | C | 32 |    | Chave MD5               |    |    |    |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`SG1` (`ID_SG1`, `G1_FILIAL`, `G1_COD`, `G1_COMP`, `G1_TRT`, `G1_QUANT`, `G1_PERDA`, `G1_OBSERV`, `G1_FIXVAR`, `G1_NIV`, `G1_LOCCON`, `G1_FANTAS`, `G1_USAALT`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



// PARA ANALISAR AINDA



#### CARGAS (ZJ)

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME   | T | S  | D | DESCRIPTION     | PK | NN | IN | NOTE |
|--------|---|----|---|-----------------|----|----|----|------|
|        |   |    |   |                 |    |    |    |      |
|        |   |    |   |                 |    |    |    |      |
| HORA   | T |    |   | Hora Alteração  |    |    |    |      |
| DATA   | D |    |   | Data Alteração  |    |    |    |      |
| STATUS | C | 01 |   | Status Registro |    |    |    |      |
| MD5    | C | 32 |   | Chave MD5       |    |    |    |      |

 

#### CARGAS_ITENS (ZL)

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME   | T | S  | D | DESCRIPTION     | PK | NN | IN | NOTE |
|--------|---|----|---|-----------------|----|----|----|------|
|        |   |    |   |                 |    |    |    |      |
|        |   |    |   |                 |    |    |    |      |
| HORA   | T |    |   | Hora Alteração  |    |    |    |      |
| DATA   | D |    |   | Data Alteração  |    |    |    |      |
| STATUS | C | 01 |   | Status Registro |    |    |    |      |
| MD5    | C | 32 |   | Chave MD5       |    |    |    |      |

 

#### COMODATO (ZZ7)

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME   | T | S  | D | DESCRIPTION     | PK | NN | IN | NOTE |
|--------|---|----|---|-----------------|----|----|----|------|
|        |   |    |   |                 |    |    |    |      |
|        |   |    |   |                 |    |    |    |      |
| HORA   | T |    |   | Hora Alteração  |    |    |    |      |
| DATA   | D |    |   | Data Alteração  |    |    |    |      |
| STATUS | C | 01 |   | Status Registro |    |    |    |      |
| MD5    | C | 32 |   | Chave MD5       |    |    |    |      |



#### COMODATO_ITENS (ZZ8)

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME   | T | S  | D | DESCRIPTION     | PK | NN | IN | NOTE |
|--------|---|----|---|-----------------|----|----|----|------|
|        |   |    |   |                 |    |    |    |      |
|        |   |    |   |                 |    |    |    |      |
| HORA   | T |    |   | Hora Alteração  |    |    |    |      |
| DATA   | D |    |   | Data Alteração  |    |    |    |      |
| STATUS | C | 01 |   | Status Registro |    |    |    |      |
| MD5    | C | 32 |   | Chave MD5       |    |    |    |      |



#### COMODATO_EQUIPAMENTOS (ZZ9)

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME   | T | S  | D | DESCRIPTION     | PK | NN | IN | NOTE |
|--------|---|----|---|-----------------|----|----|----|------|
|        |   |    |   |                 |    |    |    |      |
|        |   |    |   |                 |    |    |    |      |
| HORA   | T |    |   | Hora Alteração  |    |    |    |      |
| DATA   | D |    |   | Data Alteração  |    |    |    |      |
| STATUS | C | 01 |   | Status Registro |    |    |    |      |
| MD5    | C | 32 |   | Chave MD5       |    |    |    |      |

 

#### AC8 ( CLIENTES X CONTATOS )

Description: *Relação de Clientes X Contatos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME       | T | S  | D | DESCRIPTION          | PK | NN | UN | NOTE |
|------------|---|----|---|----------------------|----|----|----|------|
| ID         | I |    |   | ID                   | X  |    |    |      |
| AC8_FILIAL | V | 09 |   | ID Empresa           |    | X  | X  |      |
| AC8_CODCON | V | 06 |   | ID Contato           |    | X  | X  |      |
| AC8_ATIVO  | C | 01 |   | Ativo (1=Sim, 2=Não) |    |    |    |      |
| DT         | D |    |   | Data Alteração       |    |    |    |      |
| HR         | T |    |   | Hora Alteração       |    |    |    |      |
| STATUS     | C | 01 |   | Status Registro      |    |    |    |      |
| MD5        | C | 32 |   | Chave MD5            |    |    |    |      |

 

#### SU5 ( CONTATOS )

Description: *Cadastro de Contatos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME      | T | S   | D | DESCRIPTION                | PK | NN | UN | NOTE |
|-----------|---|-----|---|----------------------------|----|----|----|------|
| ID        | I |     |   | ID                         | X  |    |    |      |
| U5_FILIAL | V | 09  |   | ID Empresa                 |    | X  | X  |      |
| U5_CODCON | V | 06  |   | ID Contato                 |    | X  | X  |      |
| U5_CONTAT | V | 100 |   | Nome                       |    | X  |    |      |
| U5_FCOM1  | V | 15  |   | Telefone 1                 |    |    |    |      |
| U5_FCOM2  | V | 15  |   | Telefone 2                 |    |    |    |      |
| U5_EMAIL  | V | 100 |   | EMail                      |    |    |    |      |
| U5_URL    | V | 100 |   | URL                        |    |    |    |      |
| U5_STATUS | C | 01  |   | Status                     |    |    |    |      |
| U5_MSBLQL | C | 01  |   | Ativo (1=Inativo, 2=Ativo) |    |    |    |      |
| DT        | D |     |   | Data Alteração             |    |    |    |      |
| HR        | T |     |   | Hora Alteração             |    |    |    |      |
| STATUS    | C | 01  |   | Status Registro            |    |    |    |      |
| MD5       | C | 32  |   | Chave MD5                  |    |    |    |      |

>   STA = (1=Desatualizado, 2=Atualizado, 3=Em Desenvolvimento)

 

#### SB2 (SALDOS FISICOS ESTOQUES)

Description: *Saldo de Produtos.*

-   [ ] DataBase Desing
-   [ ] SQL Script
-   [ ] Model
-   [ ] CRUD/MVC
-   [ ] Report
-   [ ] Rest ERP
-   [ ] Rest Web

| NAME      | T | S  | D  | DESCRIPTION     | PK | NN | UN | NOTE |
|-----------|---|----|----|-----------------|----|----|----|------|
| ID_SB2    | I |    |    | ID              | X  |    |    |      |
| B2_FILIAL | V | 09 |    | Empresa         |    |    |    |      |
| B2_COD    | V | 30 |    | Produto         |    |    |    |      |
| B2_QATU   | N | 14 | 02 | Quantidade      |    |    |    |      |
| B2_LOCAL  | V | 03 |    | Armazem         |    |    |    |      |
| DT        | D |    |    | Data Alteração  |    |    |    |      |
| HR        | T |    |    | Hora Alteração  |    |    |    |      |
| STATUS    | C | 01 |    | Status Registro |    |    |    |      |
| MD5       | C | 32 |    | Chave MD5       |    |    |    |      |

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ sql
INSERT INTO `PP`.`SB2` (`ID_SB2`, `B2_FILIAL`, `B2_COD`, `B2_QATU`, `B2_LOCAL`, `DT`, `HR`, `STATUS`, `MD5`) VALUES (NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 



 
